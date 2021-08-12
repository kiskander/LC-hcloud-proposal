# Istio exercises

In the following exercises, you will use Istio to control traffic routing and responses.

## Istio Policies
Your `myhero` app is up and running, so now you will use Istio to manage your traffic and services.

Before you begin, you need to modify your manifest as before with the `ingressgateway` IP address.

The manifest files are stored in the `Istio_Policies_Templates` folder, which can be found in the `containers-code` repository.

```bash
cd ~/containers-code/module08/Istio_DNE_Manifiests/myhero_Templates
```

This time the manifest files that you need to modify are:

* `0-ui_initial_status.template`
* `1-ui_all_to_v1.template`
* `2-ui_inject_delay.template`
* `3-app_HTTP_abort.template`
* `4-ui_50_to_v3.template`
* `5-ui_v1_mirror_to_v2.template`

**Note**: Don't forget to SAVE all your updated manifest files with the `.yml` extension.

## Exercise 1: Traffic Routing
In this exercise you will use Istio to route all requests to your V1 pod only. To apply this policy issue the following command.

```bash
kubectl -n myhero apply -f 1-ui_all_to_v1.yml
```

If you review the manifest you will notice it includes a **VirtualService** that defines a rule to route all traffic going to `myhero-ui` service, so that it reaches exclusively pods labelled with `v1`. It also includes a **DestinationRule** that defines the different available versions (subsets).

Please review the applied route (you may use this in all subsequent use cases examples):

```bash
kubectl -n myhero describe virtualservice myhero-ui
kubectl -n myhero describe destinationrule myhero-ui-destinationrule
```

Refresh your browser several times while pointing to `myhero-ui` public IP and you will notice that now you only get the `v1` header: _Make ONE voice heard!!!_.

This way Istio enables you to deploy several different pods in the same service, and choose which one to use as default for your users.
This is useful for Canary Testing a new version of your app.


## Exercise 2: Delay Injection

Now inject a delay to test the resiliency of your application. For each request from your browser to `myhero-ui` you will inject a 5 seconds delay.

```bash
kubectl -n myhero apply -f 2-ui_inject_delay.yml
```

Refresh your browser and you will experience a slower response time. That way you can test how your application microservices handle unexpected response time delays. If you review the manifest you will notice that you can define what specific traffic will be affected by this rule. In your case you are using 100% of traffic to simplify the example.

Maybe you are wondering why the total delay experienced by the end user is much higher than 5 seconds and more like in the 20-25 seconds range. Well, let's dig in a little bit. In your web browser press `Ctrl+Shift+I` or `Alt+Cmd+I` to enter the web developer tools. Go to the Network tab and refresh your browser. You will be able to see the 5 seconds delay for each request, and the accumulated total explains why users get a much slower response time.

Remove the injected delay:

```bash
kubectl -n myhero apply -f 1-ui_all_to_v1.yml
```

## Exercise 3: HTTP Abort Injection

In this case you will inject a fault where `myhero-app` responds with HTTP abort (HTTP status 500):

```bash
kubectl -n myhero apply -f 3-app_HTTP_abort.yml
```

Refresh your browser and you will notice now the list of available superheroes is not there anymore. This list was provided by the `myhero-app` microservice, so now that it is aborting its connections, your application cannot show the list anymore.

This way Istio enables you to insert artificial faults in your microservices, and test how those faults reflect in the overall application.

Remove the artificially injected fault:
```bash
kubectl -n myhero apply -f istio_myhero_app_rule.yml
```

## Exercise 4: Gradual Migration to a new version

Istio enables you to migrate to new service versions in a gradual way. Let's suppose your `myhero-ui` versions (`v1`, `v2`, `v3`) are sequential ones with new features or bug fixes.

Your initial service is set so that that all traffic goes to `v1`. For this exercise, you will migrate 50% of the traffic to the newest, `v3`.

```bash
kubectl -n myhero apply -f 4-ui_50_to_v3.yml
```

Refresh your browser multiple times and you will see how 50% of the times you get `myhero-ui` `v1` header (_Make ONE voice heard!!!_) and the other 50% of time you get `myhero-ui` _v3_ header (_Make THREE voices heard!!!_).

This demonstrates how you can smoothly migrate traffic from one service version to another. You can define how much traffic you want directed to each service, regardless of the size of the deployment.

Once _v3_ is completely stable, you can easily migrate 100% of your traffic to the new version:

```bash
kubectl -n myhero apply -f 4-ui_all_to_v3.yml
```

## Exercise 5: Mirroring Traffic

Istio also enables you to mirror traffic, such as from a live service to a newer one out of production, so you can test how that new one behaves when it gets real traffic.

For this exercise, direct all traffic back to `myhero-ui` `v1`.

```bash
kubectl -n myhero apply -f 1-ui_all_to_v1.yml
```

Now open a second terminal window and leave it monitoring logs for pods belonging to the `v1` version:

```bash
export UI_V1_POD=$(kubectl -n myhero get pod -l app=myhero,version=v1 -o jsonpath={.items..metadata.name})
kubectl -n myhero logs -f $UI_V1_POD -c myhero-ui
```

You will see that every time you refresh your browser the logging reflects that activity.

Open a third terminal window and leave it monitoring logs for pods belonging to the _v2_ version:

```bash
export UI_V2_POD=$(kubectl -n myhero get pod -l app=myhero,version=v2 -o jsonpath={.items..metadata.name})
kubectl -n myhero logs -f $UI_V2_POD -c myhero-ui
```

Here you will notice that refreshing your browser does not generate any kind of logs for the v2 window.

Now let's mirror all traffic going to v1, so that it sends a copy to all pods belonging to v2:

```bash
kubectl -n myhero apply -f 5-ui_v1_mirror_to_v2.yml
```

If you refresh your browser again, you will notice in your logging terminal windows that now, not only `v1` receives traffic, but also _v2_. Both logging terminal windows will show the same events.

**YOU ARE DONE MY FRIEND!** Well done :)

## Uninstalling Istio

Once you are done you with your testing you might want to stop using Istio. If so, this is how you do it.
Remove the namespace label and stop associated pods, so they are automatically recreated without the sidecar proxies:

```bash
kubectl label namespace myhero istio-injection-
kubectl -n myhero delete pod ...
```

```bash
kubectl delete -f install/kubernetes/istio-demo.yaml
```
**Congratulations! You have finished Introduction to Istio and service mesh**
