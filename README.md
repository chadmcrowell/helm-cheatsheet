# Helm Cheat Sheet

<img src="https://helm.sh/img/helm.svg" width="100">

## Links

- [helm.sh](https://helm.sh/)
- [quickstart](https://helm.sh/docs/intro/quickstart/)
- [install helm](https://helm.sh/docs/intro/install/)
- [three big helm concepts](https://helm.sh/docs/intro/using_helm/#three-big-concepts)
- [chart file structure](https://helm.sh/docs/topics/charts/#the-chart-file-structure)

---

## Table of Contents

- [Links](#links)
- [Install Apps](#install-apps)

---

## Play with Helm

- [Install Helm on a Kind cluster in a container](play_with_helm.md)

---

## Install Apps

```bash
# list all helm charts installed and their releases
helm list

# create a new helm chart named app1
helm create app1

# install a local helm chart, where 'app1' is the name of the chart and 'app1' is the folder where the chart exists
helm install app1 app1

# install an app named 'mongodb' using the chart 'bitnami/mongodb' with values passed in using file values1.yml
helm install mongodb --values values1.yml bitnami/mongodb

# dry-run for our app named 'mongodb' passing in the values from values2.yml
# '-f' is the same as '--values'
helm template -f values2.yml mongodb

# dry run for the name of the chart 'app1' and the name of the folder where our chart exits (also called 'app1') 
# uses the default values.yaml file (created with the chart)
helm template app1 app1

# lint the manifests for the app named 'mongodb', passing in values2.yml
helm lint -f values2.yml mongodb

# upgrade the chart after changing the values.yaml
helm upgrade app1 app1 -f ./app1/values.yaml

# upgrade by setting the values manually instead of using the values file
helm upgrade app1 app1 --set deployment.tag=1.24.4
```

---

## Create Charts

```bash
# create a new chart template named dev-app (contains `chart.yml`, `values.yml`, charts and templates directory)
helm create dev-app


```

---

## Manage Repositories

```bash
# add a chart named 'bitnami' at the public address https://charts.bitnami.com/bitnami
helm repo add bitnami https://charts.bitnami.com/bitnami


```
