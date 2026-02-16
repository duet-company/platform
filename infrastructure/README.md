# Infrastructure Configuration

Kubernetes manifests and Terraform configurations for AI Data Labs.

## 📁 Structure

```
infrastructure/
├── kubernetes/      # Kubernetes manifests
│   ├── deployments/
│   ├── services/
│   └── configmaps/
└── terraform/       # Terraform configurations
    ├── main.tf
    ├── variables.tf
    └── modules/
```

## 🚀 Deployment

### Kubernetes

```bash
# Apply all manifests
kubectl apply -f kubernetes/

# Apply specific service
kubectl apply -f kubernetes/deployments/backend.yaml

# Check status
kubectl get pods -n ai-data-labs
```

### Terraform

```bash
# Initialize
cd terraform
terraform init

# Plan changes
terraform plan

# Apply changes
terraform apply

# Destroy
terraform destroy
```

## 🔗 Links

- **Infrastructure Docs:** https://github.com/duet-company/infrastructure
- **Platform:** https://github.com/duet-company/platform
- **Backend:** https://github.com/duet-company/backend
- **Frontend:** https://github.com/duet-company/frontend
