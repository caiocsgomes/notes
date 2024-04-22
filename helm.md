## Get helm code from an existing chart
```bash
helm fetch repo/chart-name --untar

# example
helm repo add stable https://charts.helm.sh/stable
helm fetch stable/nginx-ingress --untar
```
