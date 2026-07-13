# homelab-app-charts

Helm charts for self-hosted applications on Homelab Kubernetes cluster.

## Structure

```
charts/
├── homarr/                 → homarr (8.22.0, app v1.70.0) (umbrella chart)
└── calibre-web-automated/  → calibre-web-automated (1.0.0) (custom chart)
```

Some charts are umbrella chart with a single upstream dependency. 

Run the following before deploying for them:
```bash
# Add upstream Helm repo
helm repo add <component-name> <helm-chart-url>

# Download sub-chart dependencies
helm dependency build charts/<name>
```

## References

- Homarr : [Chart](https://artifacthub.io/packages/helm/homarr-labs/homarr), [Docs](https://homarr.dev/docs/getting-started/installation/helm/), [Source Code](https://github.com/homarr-labs/charts)

- Calibre-Web-Automated : [Source Code](https://github.com/crocodilestick/Calibre-Web-Automated#)

## Companion Repo

Continuous deployment (CD) is Handled by ArgoCD, refer to the GitOps repo here : [homelab-gitops](https://github.com/utkarsh-homelab/homelab-gitops)