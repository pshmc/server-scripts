# Status

| Controller | Status |
| ---------- | ------ |
| nginx | successful |
| haproxy | failed |
| traefik | failed |

## Summary

- All scripts are copied/modded from other repo's (usually the kubernetes repo)
- WIP - all use general serviceAccount: ingress-controller instead of deployment specific one
- TODO - setup tls

## Pre-Work

1. Create ClusterRole, ClusterRoleBinding, ServiceAccount:
```
kubectl apply -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/ingress/ingress-controller-rbac.yaml
```
2. Create default backend
```
kubectl apply -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/ingress/ingress-default-backend.yaml
```


## Nginx

TODO: Enter Scripts

## Haproxy

TODO: Enter Scripts

## Traefik

TODO: Enter Scripts
