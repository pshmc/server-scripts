# NFS Out-of-tree Provisioner

1. Create ServiceAccount, ClusterRole, ClusterRoleBinding for RBAc:
```
kubectl apply -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/storage/nfs/nfs-rbac.yaml
```
2. Deploy as Daemonset - will only be accesible inside the cluster:
```
kubectl apply -f https://raw.githubusercontent.com/pshmc/server-scripts/master/kubernetes/manifests/storage/nfs/nfs-daemonset.yaml
```

## Notes

- from https://github.com/kubernetes-incubator/external-storage/tree/master/nfs
- blogged http://blog.kubernetes.io/2016/10/dynamic-provisioning-and-storage-in-kubernetes.html
 
