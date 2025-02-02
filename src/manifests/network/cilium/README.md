# Update instructions

Refs: https://docs.cilium.io/en/v1.11/gettingstarted/k8s-install-default/

## Add cilium helm repo

```bash
helm repo add cilium https://helm.cilium.io/
helm repo update
```

## Generate manifests

```bash
export CILIUM_NAMESPACE=kube-system

helm template cilium cilium/cilium --version 1.11.2 \
   --namespace $CILIUM_NAMESPACE \
   --set hubble.relay.enabled=true \
   --set hubble.ui.enabled=true > cilium.yaml
```
