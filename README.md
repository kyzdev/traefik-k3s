# traefik-k3s

A kubectl YAML to deploy a Traefik on Kubernetes

## Post-Installation

You can tune the prod or dev Kustomize Overlay with :
- traefik-deployment.yaml : to match your storage driver (in my example I use a NFS driver),
- traefik-ingressroute.yaml : to match your FQDN.

## Installation

The namespace used for this deployment is "kube-system". The TLSOption must stay in "default" namespace.

```bash
git clone https://github.com/kyzdev/traefik-k3s.git
cd traefik-k3s
kubectl apply -k overlays/prod
```
## Uninstallation

```bash
kubectl delete -k overlays/prod
```