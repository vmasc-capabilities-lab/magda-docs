# Kubernetes Usage

In Helm, Kubernetes resources are distributed as charts: a collection of templated Kubernetes resources in YAML or JSON format. The charts can be deployed from an external Helm repository, a chart archive file, or a local chart directory. Each chart has their own set of variables that can be used for customizing the deployment

## CapLab Helm Chart Info
* Release Name: magda
* Path to chart: ./chart

## Update Chart Dependency 

Before any deployment, you must save all files and rebuild the helm chart.

Command to update chart:

```bash
helm dep up {PATH_TO_CHART}
```

## Deployment 

There are two ways to install Helm charts using the Helm CLI: helm install and helm upgrade --install. The install sub-command always installs a brand new chart, while the upgrade sub-command can upgrade an existing chart and install a new one, if the chart hasn’t been installed before

For deployments, we will use help upgrade --install as that is the most recommended method.

Command to deploy:
```bash 
helm upgrade --install --timeout 9999s --debug {RELEASE_NAME} {PATH_TO_CHART}
```

## Rollback a deployment

Command to rollback:

```bash 
helm rollback {RELEASE_NAME} {REVISION_NUMBER}
```

To identify the revision number run the following command : 

```bash 
helm history {RELEASE_NAME}
```
## Stuff to know

Located in the ./chart folder you will find a couple of things

- /charts
  - A directory containing any charts upon which this chart depends. 
- chart.lock
  - Assuming this is just like package-lock.json
- Chart.yaml
  - A YAML file containing information about the chart
- values.yaml
  - The default configuration values for this chart

## Resources
* https://helm.sh/docs/helm/helm_dependency_update/
* https://polarsquad.com/blog/check-your-helm-deployments
* https://www.tutorialworks.com/helm-cheatsheet/
* https://helm.sh/docs/intro/using_helm/
* https://codefresh.io/docs/docs/new-helm/helm-best-practices/