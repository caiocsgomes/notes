# Kubernetes commands cheat sheet

```bash
kubectl create -f YML_FILE

kubectl get pods
kubectl get pod POD_NAME
kubectl describe pod POD_NAME

kubectl get replicaset
kubectl delete replicaset REPLICASET_NAME
kubectl replace -f replicaset-definition.yml
kubectl scale --replicas=6 -f replicaset-definition.yml ## does not update the yml file
kubectl edit replicaset REPLICASET_NAME

```
