# Oklavier Helm Charts

Official Helm charts for [Oklavier](https://oklavier.com) — Virtual Workspace Platform on Kubernetes.

## Usage

```bash
helm repo add oklavier https://oklavier.github.io/oklavier-helm
helm repo update
```

### Install Control Plane

```bash
helm install oklavier oklavier/oklavier \
  --namespace oklavier --create-namespace \
  --set jwtSecret="your-secret" \
  --set admin.email="admin@example.com" \
  --set admin.password="changeme"
```

### Install Agent

```bash
helm install oklavier-agent oklavier/oklavier-agent \
  --namespace oklavier-agent --create-namespace \
  --set agent.name="my-agent" \
  --set agent.token="agent-token-from-admin" \
  --set agent.controlPlane="https://oklavier-api.example.com"
```

## Charts

| Chart | Description | Version |
|-------|-------------|---------|
| `oklavier` | Control Plane (API + Frontend + DB + Valkey) | 1.0.2 |
| `oklavier-agent` | Agent (workspace provisioner + guacd) | 1.0.2 |

## Documentation

[docs.oklavier.com](https://docs.oklavier.com)
