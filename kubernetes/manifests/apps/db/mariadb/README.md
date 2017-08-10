
```
#export MARIADB_ROOT_PASSWORD=$(openssl rand -base64 15 | base64 | tr -d '\n' )
#export MARIADB_PASSWORD=$(openssl rand -base64 15 | base64 | tr -d '\n' )
#kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/secrets.yaml

# without templating, it's easier to create secrets from commandline
# may switch to service accounts in the future
kubectl create secret generic \
    mariadb \
    --from-literal=mariadb-root-password=$(openssl rand -base64 15 ) \
    --from-literal=mariadb-password=$(openssl rand -base64 15 )

# Configmap
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/mariadb-configmap.yaml

# Persistent Volume Claim
# Note this is dynamically filled and the PV isn't guaranteed to be on the same node
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/pvc.yaml

# Create Service for Cluster DNS and to automatically create endpoints for ingress routing
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/svc.yaml

# 
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/.yaml

kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/db/mariadb/.yaml

```

