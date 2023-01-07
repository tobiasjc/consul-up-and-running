BEFORE starting to run the values to upgrade the consul deployment, and the api-gateway manifest, please run the following costumization:

```bash
$ kubectl apply --kustomize "github.com/hashicorp/consul-api-gateway/config/crd?ref=v0.5.0"
```
Which defines a set of CRD for the api-controller.

Then, if you've already installed the consul cluster, you should run the  `upgrade` command, otherwise `install` as below
```
$ kubectl {upgrade or install} -config-file values.yaml
```

source: https://developer.hashicorp.com/consul/tutorials/get-started-kubernetes/kubernetes-gs-ingress#enable-consul-ingress-features