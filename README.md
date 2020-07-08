# k8s-opa

# Registry

## Template

```
kubectl apply -f registry/restrict_registry_tmplt.yaml

kubectl describe constrainttemplate restrictregistry
```

## Constraint

```
kubectl apply -f registry/restrict_registry_cnstr.yaml

kubectl describe constraint restrict-registry
```

## Tests

```
kubectl apply -f registry/bad_registry_test.yaml

kubectl get deployments busybox-bad -o yaml
```

```
kubectl apply -f registry/good_registry_test.yaml

kubectl get deployments busybox-good -o yaml
```

## Cleanup

```
kubectl delete deployment busybox-bad

kubectl delete deployment busybox-good

kubectl delete constraint restrict-registry
```
