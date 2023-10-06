# mobb-poc-ops

### GitOps is performed using ArgoCD with Kustomize resources

```
.
└── apps
    └── mobb-poc-frontend
        ├── base
        │   ├── deployment.yaml
        │   ├── kustomization.yaml
        │   ├── route.yaml
        │   └── service.yaml
        └── overlays
            ├── development
            │   └── kustomization.yaml
            ├── production
            │   └── kustomization.yaml
            └── useracceptance
                └── kustomization.yaml
```
