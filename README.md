# keycloak

## Kubernetes deployment

### Prerequisites

- Kubernetes cluster with kubectl access
- A database named "keycloak"

Store admin credentials as a Secret:

```
kubectl create secret generic keycloak-secret --from-literal=username=admin --from-literal=password=<YOUR PASSWORD>
```

Create Service and Deployment:

```
kubectl apply -f deployment.yaml
```

## Configuration

Login as admin and create the `how2die` realm.

### Realm settings

Enable `User registration` under `Login`.

Select `How2die` as `Login Theme`.

### Client settings

Create a client named `website` using openid-connect and Root url `https://how2die.com`

### Authentication

Under `Registration`, disable `Profile Validation` to not require first name, last name and email.

Enable "Remember Me" under Login; increase token lifespan under Tokens.
