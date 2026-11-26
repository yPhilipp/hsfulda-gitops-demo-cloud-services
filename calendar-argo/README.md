# Calendar App ArgoCD application

## Installation

1. [Create a new Repository using this template (optional)](https://github.com/DRSchlaubi/hsfulda-argocd-demo/generate)
2. Create a new ArgoCD Application
- Application Name: `argocd-demo`
- Project name: `default`
- Sync Policy: Auto
- Auto create namespace: On
- Source:
    - Url: <your repo from step 1> or https://github.com/DRSchlaubi/hsfulda-gitops-demo.git
    - Path: `calendar-argo`
Alternatively you can use the [ArgoCD CLI](https://argo-cd.readthedocs.io/en/stable/cli_installation/):
```shell
# Set the namespace for the cli to look for the argocd details
kubectl config set-context --current --namespace=argocd
argocd app create argocd-example \ 
  --core \
  --repo <your repo from step 1> or https://github.com/DRSchlaubi/hsfulda-gitops-demo.git \
  --path calendar-argo \
  --dest-namespace argocd \
  --dest-server https://kubernetes.default.svc \
  --sync-policy automated \
  --sync-option CreateNamespace=true
```
