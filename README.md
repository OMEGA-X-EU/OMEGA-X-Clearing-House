# OMEGA-X Clearing House

OMEGA-X project sets up its own version of a Gaia-X Digital Clearing House (GXDCH) to be verified against the Gaia-X rules. 

The Clearing House consists of three core components: 

* Registry service (based off [Gaia-X Registry](https://gitlab.com/gaia-x/lab/compliance/gx-registry)) - made to verify the validity of signed claims (e.g., Self Descriptions) by checking the provided certificates against the list of Gaia-X endorsed Trust Anchor certificates.
* Notary service (based off [Gaia-X Notary](https://gitlab.com/gaia-x/lab/compliance/gaia-x-notary-registrationnumber)) - designed to support the issuance of Legal Registration number Verifiable Credential.
* Compliance service (based off [Gaia-X Compliance](https://gitlab.com/gaia-x/lab/compliance/gx-compliance)) - validates the shape, content and credentials of Self Descriptions and issues a Verifiable Credential attesting of the result.

This repository contains Kubernetes manifests used in Omega-X Project to deploy Gaia-X Digital Clearing House in the Kubernetes cluster.

