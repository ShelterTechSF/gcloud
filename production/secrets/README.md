# Secrets
There are a handful of secrets defined in the k8s yaml files. This is record of what they are and how they were generated.

## Ingress SSL Certificate
This is the SSL certificate used to TLS handshake for ingress.
```
kubectl create secret tls origin-cert-secret --key /tmp/askdarcel-production-secrets/origin-cert.key --cert /tmp/askdarcel-production-secrets/origin-cert.pem
```
## Algolia
These are secrets related to a search indexing external service, both the web and api containers use these
```
kubectl create secret generic algolia --from-file /tmp/askdarcel-production-secrets/algolia-application-id --from-file /tmp/askdarcel-production-secrets/algolia-read-only-api-key --from-file /tmp/askdarcel-production-secrets/algolia-api-key
```
## Google API
This is the API key for sending requests for the maps and geolocation APIs
```
kubectl create secret generic google --from-file /tmp/askdarcel-production-secrets/frontend-google-api-key --from-file /tmp/askdarcel-production-secrets/backend-google-api-key
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
## Airtable API Key
Data things, ask Max
```
kubectl create secret generic airtable --from-file /tmp/askdarcel-production-secrets/airtable-api-key
```