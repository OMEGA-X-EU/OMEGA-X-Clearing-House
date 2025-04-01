# Compliance Service
This directory contains kubernetes manifests for deployment of Omega-X Compliance Service, based on [gx-compliance](https://gitlab.com/gaia-x/lab/compliance/gx-compliance), prototype for a compliance service as defined in [Gaia-X Trust Framework](https://gaia-x.gitlab.io/policy-rules-committee/trust-framework/). 

## Environment Variables
* `COMPLIANCE_PRIVATE_KEY`: Value of private key (base64 encoded)
* `COMPLIANCE_X509_CERTIFICATE`:  Value of public key certificate in a standard format X.509 (base64 encoded)
* `CA_ROOT_CERT`:  Value of Compliance service´s root certificate (base64 encoded)
* `IMAGETAG_MEMGRAPH`: Stable memgraph version (for example, 2.3.0)
* `IMAGETAG_COMPLIANCE`: Stable compliance service version (for example, development)
* `PUBLIC_NODE_DOMAIN`: FQDN
* `EXTRA_CA_CERT`: Extra CA certificate to add to trusted

## Deployment

```bash
# For testing
cat compliance/*.yaml | envsubst | kubectl apply --dry-run=client -f -
# For deploying
cat compliance/*.yaml | envsubst | kubectl apply -f -
```