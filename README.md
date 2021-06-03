# LogCLI - Helm Chart

[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/logcli)](https://artifacthub.io/packages/search?repo=logcli)

This chart deploys a single [LogCLI](https://grafana.com/docs/loki/latest/getting-started/logcli/) container tool to interact with [Loki](https://grafana.com/oss/loki/).

## Installing the Chart

To install the chart with the release name `logcli` run:

```bash
helm repo add logcli https://raw.githubusercontent.com/hansehe/logcli-helm/master/helm/charts
helm repo update
helm install logcli --set loki.addressOverride=<loki_url> ./logcli
```

Execute LogCLI statement with:
```bash
kubectl get pods | grep logcli
kubectl exec -it <logcli_pod> -- logcli help
kubectl exec -it <logcli_pod> -- logcli query '{cluster=\"CLUSTER_NAME\"} |= \"error\"'
```