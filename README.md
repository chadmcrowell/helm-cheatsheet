# Helm Cheat Sheet

<img src="https://helm.sh/img/helm.svg" width="100">

## Links

- [helm.sh](https://helm.sh/)
- [quickstart](https://helm.sh/docs/intro/quickstart/)
- [install helm](https://helm.sh/docs/intro/install/)
- [three big helm concepts](https://helm.sh/docs/intro/using_helm/#three-big-concepts)

---

## Table of Contents

- [Links](#links)
- [Install Apps](#install-apps)

---

## Install Apps

```bash
# install an app named 'mongodb' using the chart 'bitnami/mongodb' with values passed in using file values1.yml
helm install mongodb --values values1.yml bitnami/mongodb

# dry-run for our app named 'mongodb' passing in the values from values2.yml
helm template -f values2.yml mongodb

# lint the manifests for the app named 'mongodb', passing in values2.yml
helm lint -f values2.yml mongodb
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