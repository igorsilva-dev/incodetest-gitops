# incode test - GitOps

A GitOps repository for managing Kubernetes infrastructure and applications on AWS EKS using ArgoCD.

## What's in here?

- **bootstrap/** - ArgoCD configuration and setup for the cluster
- **apps/** - Application deployments (currently running go-htmx-fiber-app)

## Quick Start

The cluster is managed automatically via ArgoCD. Any changes pushed to this repository are automatically synced to the cluster.

### Key Components

- **ArgoCD** - Handles all deployments and keeps everything in sync
- **External Secrets** - Manages secrets from AWS Secrets Manager
- **AWS Load Balancer Controller** - Routes traffic to applications
- **Cluster Autoscaler** - Scales worker nodes based on demand

## Making Changes

1. Modify the YAML files in `bootstrap/` or `apps/` directories
2. Commit and push to main branch
3. ArgoCD automatically applies changes to the cluster

## Project Structure

```
bootstrap/argocd/development/us-east-1/
├── app-of-apps.yaml           # Main app manager
├── aws-load-balancer-controller-app.yaml
├── cluster-autoscaler-app.yaml
└── external-secrets-app.yaml

apps/development/us-east-1/
└── go-htmx-fiber-app.yaml     # Fullstack Web Application
```
