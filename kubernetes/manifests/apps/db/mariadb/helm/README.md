# Mariadb Deployment using stable helm chart

```
curl -O https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/helm/values.yaml
helm install \
  --name db \
  -f values.yaml \
  stable/mariadb
rm -f values.yaml
```
