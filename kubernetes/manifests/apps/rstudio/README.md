# Persistent Volume Claim
# Note this is dynamically filled and the PV isn't guaranteed to be on the same node
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/rstudio/rstudio-volumes.yaml

# Create Service for Cluster DNS and to automatically create endpoints for ingress routing
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/rstudio/rstudio-svc.yaml

# deploy the pod - this is for a single instance
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/rstudio/rstudio-deploy.yaml

# Make it accessible from outside the cluster
kubectl create \
  -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/apps/rstudio/rstudio-ingress.yaml
