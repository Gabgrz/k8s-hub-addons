# Hub Cluster Addons

GitOps-managed Kubernetes addons for hub cluster management using ArgoCD.

## Components

- **ArgoCD** (`argocd/`) - GitOps engine with Application Sets for auto-discovery
- **External Secrets** (`external-secrets/`) - Secure secret management via GCP Secret Manager
- **Config Connector** (`cnrm-system/`) - Manage GCP resources as Kubernetes objects
- **Guestbook** (`guestbook/`) - Sample application with GCP SQL integration

## Quick Start

1. Deploy ArgoCD addon to your cluster
2. Application Set automatically discovers and deploys all other addons
3. Configure GitHub credentials in GCP Secret Manager
4. Verify deployment:
   ```bash
   kubectl get applications -n argocd
   kubectl get pods -n external-secrets
   ```

## Structure

```
hub-cluster-addons/
├── argocd/           # ArgoCD configuration
├── external-secrets/ # Secret management
├── cnrm-system/      # Config Connector
└── guestbook/        # Sample app
```

## Troubleshooting

```bash
# Check ArgoCD status
kubectl get applications -n argocd

# Check External Secrets
kubectl get externalsecrets -A

# Check Config Connector
kubectl get configconnector -n cnrm-system
```

## Contributing

Add new addons as separate directories with `kustomization.yaml` files.
