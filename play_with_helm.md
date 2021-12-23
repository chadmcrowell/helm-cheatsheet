## _Play with Helm_
### A quick and easy way to play with helm without installing anything on your computer. 
Everything is installed inside of a docker container (must have Docker installed).
- [Install Docker on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- [Install Docker on RHEL](https://docs.docker.com/engine/install/rhel/)
- [Install Docker on Windows](https://docs.docker.com/desktop/windows/install/)
- [Install Docker on Mac](https://docs.docker.com/desktop/mac/install/)

## Create a single node Kubernetes cluster using Kind
- [kind docs](https://kind.sigs.k8s.io/docs/user/quick-start/)

```bash
kind create cluster --name virt --image kindest/node:v1.23.0
```

## Create a container to work with Helm
```bash
docker run -it --rm -v ${HOME}:/root/ -v ${PWD}:/workdir -w /$ --net host alpine sh
```

## Install kubectl inside the container
```bash
wget https://dl.k8s.io/release/v1.23.0/bin/linux/amd64/kubectl
install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client
kubectl get no
```

## Install helm inside the container
```bash
wget https://get.helm.sh/helm-v3.7.2-linux-amd64.tar.gz
tar -xvf helm-v3.7.2-linux-amd64.tar.gz
rm helm-v3.7.2-linux-amd64.tar.gz
mv ./linux-amd64/helm /usr/local/bin/helm
chmod +x /usr/local/bin/helm
```