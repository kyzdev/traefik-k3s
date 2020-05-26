# traefik-k3s

A kubectl YAML to deploy a Traefik on Kubernetes

## Post-Installation

You can tune the prod or dev Kustomize Overlay with :
- traefik-persistentvolumeclaim.yaml : to match your storage driver for exemple,
- traefik-ingressroute.yaml : to match your FQDN (for Traefik Dashboard).

## Installation

The namespace used for this deployment is "kube-system". The TLSOption must stay in "default" namespace.

```bash
# <env> must match your environment overlay
git clone https://github.com/kyzdev/traefik-k3s.git
cd traefik-k3s
kubectl apply -k overlays/<env>
```
## Uninstallation

```bash
# <env> must match your environment overlay
kubectl delete -k overlays/<env>
```

## Credits

https://www.grottedubarbu.fr/traefik-2-k3s/