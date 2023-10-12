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

# Some things you'll need to configure in OpenShift

```
# Create ocp projects
oc new-project development
oc new-project useracceptance
oc new-project production
oc new-project pipelines

# Allow the pipelines service account to edit resources in the namespace where the resources should be deployed
oc policy add-role-to-user edit system:serviceaccount:pipelines:pipeline --namespace=development
oc policy add-role-to-user edit system:serviceaccount:pipelines:pipeline --namespace=useracceptance
oc policy add-role-to-user edit system:serviceaccount:pipelines:pipeline --namespace=production
```