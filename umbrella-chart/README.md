# umbrella-chart

This is a Helm umbrella chart that installs:

- kube-prometheus-stack
- Grafana
- promtail

## Installation
1. Clone the repository
2. Inside promtail-values.yaml update the username and password locally. 
3. Run the helm install command:
```bash
helm dependency update
helm install umbrella-chart . -n monitoring \
  -f values/prometheus-values.yaml \
  -f values/grafana-values.yaml \
  -f values/loki-values.yaml 
```
## Upgrade Chart
Before running this command, change the username and password in promtail-values.yaml file
```bash
helm upgrade --install umbrella-chart . -n monitoring \
  -f values/prometheus-values.yaml \
  -f values/grafana-values.yaml \
  -f values/promtail-values.yaml
```
## Installing Loki
1. Download loki's values file
2. Run this command:
```bash
helm upgrade --install loki grafana/loki -f ./loki-values.yaml --version 6.32.0 -n monitoring
```
Loki Guide I used to install on AKS:
https://grafana.com/docs/loki/latest/setup/install/helm/deployment-guides/azure/

