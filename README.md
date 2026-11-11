# Opentelemetry observability stack

## Setup

Apply the [app-of-apps](https://argo-cd.readthedocs.io/en/latest/operator-manual/cluster-bootstrapping/).

```bash
kubectl apply -f app_of_apps.yaml
```

Grafana needs a secret with the admin account details in it.

```bash
kubectl create ns otelo11y-grafana
kubectl -n otelo11y-grafana create secret generic admin --from-literal=admin-user=<youruser> --from-literal=admin-password=<yourpass>
```

Why is this way of secret creation suboptimal? What would be a better whay?