# Existing Specifications relevant to HTTPS/WSS in Local Network (14-Feb-2018)

This document enumerates existing specifications and drafts relevant to
in local network via HTTP and/or WebSocket over TLS, for the purpose of
exploring a secure and flexible use of TLS in local network.

For details and further discussion, please refer to
[the corresponding issue in GitHub](https://github.com/httpslocal/usecases/issues/7).
Any proposals for addition, clarification and improvement are absolutely welcome.

[RelevantIETFDocuments.md], a list of potentially relevant standards and drafts discussed in IETF, could provide ideas, hints, and potential solutions for you, as well.

## General Topics of Home Network Devices

- IETF
  - [Use Cases for Authentication and Authorization in Constrained Environments](https://tools.ietf.org/html/rfc7744):
  introduces several CoAP-based use cases of devices in constrained environments.

## Security Infrastructure

- W3C Web Application Security WG
  - [Secure Contexts](https://w3c.github.io/webappsec-secure-contexts/):
    defines “secure contexts”, which user agent implementers and specification authors
    to allow minimum features of which authentication and confidentiality are met.
  - [Mixed Context](https://w3c.github.io/webappsec-mixed-content/):
    describes how a user agent should handle fetching of content over unencrypted or
    unauthenticated connections in the context of an encrypted and authenticated document.
- WHATWG Living Standards
  - [Fetch Living Standard](https://fetch.spec.whatwg.org):
    describes [Cross-Origin Resource Sharing (CORS)](https://fetch.spec.whatwg.org/#http-cors-protocol)
    specification integrated into fetch algorithms.

## Service Discovery

- W3C Second Screen CG
  - [mDNS](https://github.com/webscreens/openscreenprotocol/blob/gh-pages/mdns.md)
    and
    [SSDP](https://github.com/webscreens/openscreenprotocol/blob/gh-pages/ssdp.md)
    in Open Screen Control Protocol: describe deployment of service discovery
    for Open Screen Protocol and their security considerations.
- BBC
  - [Discovery and Pairing Literature Review for MediaScape](https://github.com/bbc/device-discovery-pairing/blob/master/document.md):
    describes a variety of service discovery and device paring mechanisms which
    are widely collected.

## Certificates and PKI

- IETF
  - [Automatic Certificate Management Environment (ACME)](https://tools.ietf.org/html/draft-ietf-acme-acme-07):
    introduces an automation framework of issuing Domain Validated (DV) server certificates,
    developed by [IETF ACME WG](https://datatracker.ietf.org/wg/acme/).
    [Let's Encrypt](https://letsencrypt.org) is widely known as its implementation.
  - [CAA Record Extensions for Account URI and ACME Method Binding](https://tools.ietf.org/html/draft-ietf-acme-caa-03):
    proposes extensions to CAA records; a parameter "account-uri" to identify a specific CA
    account, and a parameter "validation-methods" to specify a challenge method.
  - [Use of Short-Term Automatically Renewed (STAR) Certificates to Delegate Authority over Web Sites](https://tools.ietf.org/html/draft-ietf-acme-star-00):
    extends ACME to servers behind intermediate nodes such as load balancers, edge servers, etc.
  - [Bootstrapping Remote Secure Key Infrastructures (BRSKI)](https://tools.ietf.org/html/draft-ietf-anima-bootstrapping-keyinfra-10):
    introduces automated bootstrapping of a remote secure key infrastructure (BRSKI) for
    devices in Low-powered and Lossy Networks (LLNs).

## Local Network Architecture and Domain Name Issues

- IETF
  - [Special Use Domain 'home.arpa.'](https://datatracker.ietf.org/doc/draft-ietf-homenet-dot/)
    discusses use of a domain name '.home.arpa' specified to home networks

## Authentication and Authorization

- W3C Web Authentication WG
  - [Web Authentication: An API for accessing Public Key Credentials Level 1](https://w3c.github.io/webauthn/):
    defines an API enabling the creation and use of strong, attested, scoped,
    public key-based credentials by web applications, for the purpose of strongly
    authenticating users.
- IETF
  - [The OAuth 2.0 Authorization Framework](https://tools.ietf.org/html/rfc6749):
    defines procedures for how to enable a third-party application to obtain
    limited access to an HTTP service.
  - [OAuth 2.0 Device Flow for Browserless and Input Constrained Devices](https://tools.ietf.org/html/draft-ietf-oauth-device-flow-06):
    proposes an authorization flow for browserless and input constrained devices
    like smart TV, media console, picture frame, printer, etc.
  - [J-PAKE: Password-Authenticated Key Exchange by Juggling](https://tools.ietf.org/html/rfc8236):
    introduces password-authenticated key change technique without relying a PKI.
    W3C [Second Screen Community Group](https://github.com/webscreens/) is trying to incorporate
    J-PAKE into [Open Screen Protocol](https://github.com/webscreens/openscreenprotocol).

## Others

TBA