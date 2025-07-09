# umbrella-chart

This is a Helm umbrella chart that installs:

- kube-prometheus-stack
- Grafana
- Loki

## Installation

```bash
helm dependency update
helm install umbrella-chart . \
  -f values/prometheus-values.yaml \
  -f values/grafana-values.yaml \
  -f values/loki-values.yaml
