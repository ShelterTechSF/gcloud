# Secrets
There are a handful of secrets defined in the k8s yaml files. This is record of what they are and how they were generated.

## Keel Slack Integration
Not sure what this is for
```
kubectl create secret generic keel-slack --from-literal=slack-token='TOKEN_VALUE' --namespace keel
```