# Operations Playbook

## Deployment

### Kubernetes
Deployment manifests are located in `/deploy/k8s`. 

```bash
kubectl apply -f deploy/k8s/namespace.yaml
kubectl apply -f deploy/k8s/redis.yaml
kubectl apply -f deploy/k8s/postgres.yaml
kubectl apply -f deploy/k8s/api-deployment.yaml
```

## Monitoring

NEXUS exports metrics in Prometheus format at `/metrics`.

### Key Metrics to Watch:
- `nexus_agent_execution_time_seconds`: Latency per agent task.
- `nexus_llm_token_usage_total`: Total cost tracking per project.
- `nexus_task_failure_rate`: Percentage of tasks requiring retries.

## Scaling

- **Vertical Scaling**: Increase RAM for the Vector DB to handle larger embedding indexes.
- **Horizontal Scaling**: Increase the number of `nexus-worker` replicas to handle concurrent tasks.