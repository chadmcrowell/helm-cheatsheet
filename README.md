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
```

