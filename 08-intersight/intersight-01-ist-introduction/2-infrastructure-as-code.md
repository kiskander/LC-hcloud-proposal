# Infrastructure as Code (IaC)

![](https://github.com/kiskander/LC-hcloud-proposal/blob/main/08-intersight/intersight-01-ist-introduction/assets/images/ist02.png?raw=true)

IaC has evolved to solve the problem of environment drift in the release pipeline. This evolution has led to active management of infrastructure in a declarative model that uses versioning for the source "code". As an example, a model can be the desired end state of an environment. IaC makes Git repositories the "Single Source of Truth", similar to the repositories for application code.

IaC enables continuous integration/continuous delivery (CI/CD) toolchains, similar to toolchains used to manage application software. These workflows automatically build, test, deploy, and track pull requests that make configuration changes to an infrastructure. 

The tools in these pipelines offer organizations flexibility in defining the rigidity of their deployments. You can prevent the merging of changes that do not meet the defined test criteria. These toolchains provide visibility throughout the process and call out any issues that arise.

In IaC, it is always necessary to define deployments by setting the target environment to the same configuration, regardless of the environment’s starting state. This definition enables you to transition from mutable (and unpredictable) workloads to more predictable, immutable workloads.

**Next: Infrastructure as Code**
