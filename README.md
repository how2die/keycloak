# keycloak

Store admin credentials as a Secret:

```
kubectl create secret generic keycloak-secret --from-literal=username=admin --from-literal=password=<YOUR PASSWORD>
```

Create Service and Deployment:

```
kubectl apply -f deployment.yaml
```
