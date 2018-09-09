# Secrets
There are a handful of secrets defined in the k8s yaml files. This is record of what they are and how they were generated.

## Ingress SSL Certificate
This is the SSL certificate used to TLS handshake for ingress.
```
kubectl create secret tls origin-cert-secret --key /tmp/askdarcel-production-secrets/origin-cert.key --cert /tmp/askdarcel-production-secrets/origin-cert.pem
```
## CloudSQL Sidecar Service Account
This is a secret that allows the api service to talk to the Cloud SQL instance of Postgres that is outside the K8s cluster.
```
kubectl create secret generic cloudsql-instance-credentials --from-file=/tmp/askdarcel-production-secrets/credentials.json=askdarcel-184805-2100b0182a7a.json
```
## Algolia
These are secrets related to a search indexing external service, both the web and api containers use these
```
kubectl create secret generic algolia --from-file /tmp/askdarcel-production-secrets/algolia-application-id --from-file /tmp/askdarcel-production-secrets/algolia-read-only-api-key --from-file /tmp/askdarcel-production-secrets/algolia-api-key
```
## Google API
This is the API key for sending requests for the maps and geolocation APIs
```
kubectl create secret generic google --from-file /tmp/askdarcel-production-secrets/google-api-key
```
## Database Credentials
Database credentials for Postgres
```
kubectl create secret generic database --from-file /tmp/askdarcel-production-secrets/database-username --from-file /tmp/askdarcel-production-secrets/database-password 
```
## Secret Key Base
Not sure what this is for
```
kubectl create secret generic secret-key --from-file /tmp/askdarcel-production-secrets/secret-key-base
```