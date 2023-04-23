# Daemonset

A DaemonSet ensures that all (or some) Nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected. Deleting a DaemonSet will clean up the Pods it created.

```shell
# rs.yaml to ds.yaml and customize
k create -f ds.yaml
k get pod -o wide
```
