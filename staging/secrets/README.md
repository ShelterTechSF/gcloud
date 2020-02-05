# Secrets
There are a handful of secrets defined in the k8s yaml files. This is record of what they are and how they were generated.

## Ingress SSL Certificate
This is the SSL certificate used to TLS handshake for ingress.
```
kubectl create secret tls origin-cert-secret --key /tmp/askdarcel-staging-secrets/origin-cert.key --cert /tmp/askdarcel-staging-secrets/origin-cert.pem
```
## Algolia
These are secrets related to a search indexing external service, both the web and api containers use these
```
kubectl create secret generic algolia --from-file /tmp/askdarcel-staging-secrets/algolia-application-id --from-file /tmp/askdarcel-staging-secrets/algolia-read-only-api-key --from-file /tmp/askdarcel-staging-secrets/algolia-api-key
```
## Google API
This is the frontend and backend API key for sending requests for the maps and geolocation APIs
```
kubectl create secret generic google --from-file /tmp/askdarcel-staging-secrets/frontend-google-api-key --from-file /tmp/askdarcel-staging-secrets/backend-google-api-key
```
## Database Credentials
Database credentials for Postgres
```
kubectl create secret generic database --from-file /tmp/askdarcel-staging-secrets/database-username --from-file /tmp/askdarcel-staging-secrets/database-password 
```
## Secret Key Base
Not sure what this is for
```
kubectl create secret generic secret-key --from-file /tmp/askdarcel-staging-secrets/secret-key-base
```
## Airtable API Key
Pushes basic updates in our DB to https://airtable.com/appItSYNzRjTx08hN/ , the tool we use to log the progress of vetting our data (i.e. at Datathons). Login to Airtable via the tools@sheltertech.org google account or ask on Slack for details.
```
kubectl create secret generic airtable --from-file /tmp/askdarcel-staging-secrets/airtable-api-key
```
