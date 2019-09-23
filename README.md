# Use Cases and Requirements on HTTPS-enabled Local Network Servers

This repository is used to solicit use cases where browsers communicate with HTTPS servers in local network,
for the purpose of clarifying network and security requirements.

Collected use cases and related requirements are sorted out and published as a Commnity Group Report,
[Use Cases and Requirementson HTTPS-enabled Local Network Servers](https://httpslocal.github.io/usecases).

## Generating `index.html`

The final output `index.html` is created from `index.bs` file with Bikeshed. To do so:

- [Install Bikeshed](https://tabatkins.github.io/bikeshed/#installing)
    - Note that Bikeshed needs Python 2 (as of the time writing this document).
- run `bikeshed spec`

## Contributing

If you find another use case, please submit a Pull Request to add it to [UseCases.md](UseCases.md), or add your comment to relevant GitHub issues.

The following are the documents derived from the discussions on the use cases. Please also submit a Pull Request, or add your comment.

* [Requiremens.md](Requirements.md) - functional and non-functional requirements of HTTPS/WSS in local network
* [RelevantSpecs.md](RelevantSpecs.md) - existing specifications and drafts relevant to HTTPS/WSS in local network
* [Certificates.md](Certificates.md) - types of server certificate used for HTTPS/WSS in local network
* [NetworkBasedAPI.md](NetworkBasedAPI.md) - how HTTPS in local network can mitigate the security risk on Network based API
* [RelevantIETFDocuments.md](RelevantIETFDocuments.md) - existing IETF documents relevant to
in local network via HTTP and/or WebSocket over TLS

Please note that, to have your changes get into the final output `index.html`, you need to edit the `index.bs` file too.

Also, please check [the contribution guide](CONTRIBUTING.md) before making a contribution.
