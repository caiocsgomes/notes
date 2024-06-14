## Get helm code from an existing chart
```bash
helm fetch repo/chart-name --untar

# example
helm repo add stable https://charts.helm.sh/stable
helm fetch stable/nginx-ingress --untar
```

## List charts under a repository
```bash
helm search repo repo-name
```

## List all installed charts
```bash
helm list -A
```
