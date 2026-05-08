# User Service

The Stellarus User Service handles all user authentication 
and profile management for the platform.

## Architecture

This service runs on AKS in the `user-service` namespace,
isolated via Kubernetes NetworkPolicies.

## API Endpoints

- `POST /users` - Create new user
- `GET /users/:id` - Get user by ID  
- `PUT /users/:id` - Update user
- `DELETE /users/:id` - Delete user

## Deployment

Deployed via GitOps using Argo CD. All changes flow
through pull requests — no direct kubectl access.

## Runbook

### Health Check
```bash
kubectl get pods -n user-service
```

### View Logs
```bash
kubectl logs -f deployment/user-service -n user-service
```
