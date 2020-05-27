# traefik-k3s

A kubectl YAML to deploy a Traefik on Kubernetes

## Post-Installation

You can tune the prod or dev Kustomize Overlay with :
- traefik-persistentvolumeclaim.yaml : to match your storage driver for exemple,
- traefik-ingressroute.yaml : to match your FQDN (for Traefik Dashboard).
- traefik-secret.yaml : to change the login and the password for the dashboard.
- traefik-configmap.yaml : to tune the configuration of the traefik dashboard.

Note : the dev configuration use letsencrypt-staging, you must keep this configuration and add manually the root CA of the LE Staging Server in your browser.

The insecure entrypoint (HTTP) is automatically redirected to the secure entrypoint (HTTPS).

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