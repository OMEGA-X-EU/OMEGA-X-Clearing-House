# Notary Service
This directory contains kubernetes manifests for deployment of Omega-X Notary Service, based on [gx-notary registrationNumber](https://gitlab.com/gaia-x/lab/compliance/gaia-x-notary-registrationnumber). 

## Environment Variables
* `NOTARY_PRIVATE_KEY`: Value of private key (base64 encoded)
* `NOTARY_X509`:  Value of public key certificate in a standard format X.509 (base64 encoded)
* `CA_ROOT_CERT`:  Value of Notary service´s root certificate (base64 encoded)
* `IMAGETAG_NOTARY`: Stable Notary service version (for example, development)
* `PUBLIC_NODE_DOMAIN`: FQDN

## Deployment

```bash
# For testing
cat notarization/*.yaml | envsubst | kubectl apply --dry-run=client -f -
# For deploying
cat notarization/*.yaml | envsubst | kubectl apply -f -
```