# LogCLI Chart

This chart deploys a single [LogCLI](https://grafana.com/docs/loki/latest/getting-started/logcli/) container tool to interact with [Loki](https://grafana.com/oss/loki/).

Original source code is here:
- https://github.com/hansehe/logcli-helm

## Installing the Chart

To install the chart with the release name `logcli` run:

```bash
helm repo add logcli https://raw.githubusercontent.com/hansehe/logcli-helm/master/helm/charts
helm repo update
helm install logcli --set loki.addressOverride=<loki_url> logcli/logcli
```

Execute LogCLI statement with:
```bash
kubectl get pods | grep logcli
kubectl exec -it <logcli_pod> -- logcli help
kubectl exec -it <logcli_pod> -- logcli query '{cluster=\"CLUSTER_NAME\"} |= \"error\"'
```

## Configuration

Find all possible configuration values here:
- https://github.com/hansehe/logcli-helm/blob/master/helm/logcli/values.yaml

