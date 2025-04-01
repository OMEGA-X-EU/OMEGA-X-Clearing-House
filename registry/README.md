# Registry
Based on [gx-registry](https://gitlab.com/gaia-x/lab/compliance/gx-registry) image, this component is part of the OMEGA-X Clearing House. This repo contains the kubernetes manifests to deploy this service into the Kubernetes cluster.

## Environment Variables
* `REGISTRY_MONGO_USERNAME`: Mongo username (base64 encoded)
* `REGISTRY_MONGO_PASSWORD`: Mongo password (base64 encoded)
* `PUBLIC_NODE_DOMAIN`: FQDN
* `IMAGETAG_REGISTRY_MONGO`: Mongo image tag
* `REGISTRY_REVOCATION_LIST_URL`: Revocation list url (base64 encoded)
* `REGISTRY_TRUSTED_ISSUERS_URL`: Trusted issuers url (base64 encoded)
* `REGISTRY_X509_CERTIFICATE`: X509 certificate public key (base64 encoded)
* `REGISTRY_PRIVATE_KEY`: X509 certificate private key (base64 encoded)
``
## Deployment

```bash
# For testing
cat registry/*.yaml | envsubst | kubectl apply --dry-run=client -f -
# For deploying
cat registry/*.yaml | envsubst | kubectl apply -f -
```