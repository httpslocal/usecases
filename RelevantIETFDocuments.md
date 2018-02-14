# Existing IETF Standards and Drafts relevant to HTTPS/WSS in Local Network (02-Nov-2017)

## [Applications and Real-Time Area (ART)](https://datatracker.ietf.org/group/art/about/)

###  [Expect-CT Extension for HTTP](https://datatracker.ietf.org/doc/draft-ietf-httpbis-expect-ct/)

- **WG**: [HTTPBIS](https://datatracker.ietf.org/wg/httpbis/about/)
- **Category**: Certificate Transparency (CT)

#### Abstract

This document defines a new HTTP header, named Expect-CT, that allows
web host operators to instruct user agents to expect valid Signed
Certificate Timestamps (SCTs) to be served on connections to these
hosts.  When configured in enforcement mode, user agents (UAs) will
remember that hosts expect SCTs and will refuse connections that do
not conform to the UA's Certificate Transparency policy.  When
configured in report-only mode, UAs will report the lack of valid
SCTs to a URI configured by the host, but will allow the connection.
By turning on Expect-CT, web host operators can discover
misconfigurations in their Certificate Transparency deployments and
ensure that misissued certificates accepted by UAs are discoverable
in Certificate Transparency logs.

### [Using TLS in Applications (UTA) WG](https://datatracker.ietf.org/wg/uta/about/)

- **WG**: [UTA](https://datatracker.ietf.org/wg/uta/about/)
- **Category**:

## [General Area (GEN)](https://datatracker.ietf.org/group/gen/about/)

## [Internet Area (INT)](https://datatracker.ietf.org/group/int/about/)

### [Device Pairing Using Short Authentication Strings](https://datatracker.ietf.org/doc/draft-ietf-dnssd-pairing/)

- **WG**: [DNSSD](https://datatracker.ietf.org/wg/dnssd/about/)
- **Category**: service discovery, device authentication

#### Abstract

This document proposes a device pairing mechanism that establishes a
relation between two devices by agreeing on a secret and manually
verifying the secret's authenticity using an SAS (short
authentication string).  Pairing has to be performed only once per
pair of devices, as for a re-discovery at any later point in time,
the exchanged secret can be used for mutual authentication.

The proposed pairing method is suited for each application area where
human operated devices need to establish a relation that allows
configurationless and privacy preserving re-discovery at any later
point in time.  Since privacy preserving applications are the main
suitors, we especially care about privacy.

### [Device Pairing Design Issues](https://datatracker.ietf.org/doc/draft-ietf-dnssd-pairing-info/)

- **WG**: [DNSSD](https://datatracker.ietf.org/wg/dnssd/about/)
- **Category**: service discovery, device pairing

#### Abstract

This document discusses issues and problems occuring in the design of
device pairing mechanism.  It presents experience with existing
pairing systems and general user interaction requirements to make the
case for "short authentication strings".  It then reviews the design
of cryptographic algorithms designed to maximise the robustness of
the short authentication string mechanisms, as well as implementation
considerations such as integration with TLS.

### [Special Use Domain 'home.arpa.'](https://datatracker.ietf.org/doc/draft-ietf-homenet-dot/)

- **WG**: [HOMENET](https://datatracker.ietf.org/wg/homenet/about/)
- **Category**: localnet top level domain name

#### Abstract

This document specifies the behavior that is expected from the Domain
Name System with regard to DNS queries for names ending with
'.home.arpa.', and designates this domain as a special-use domain
name. 'home.arpa.' is designated for non-unique use in residential
home networks.  Home Networking Control Protocol (HNCP) is updated to
use the 'home.arpa.' domain instead of '.home'.

### [Simple Homenet Naming and Service Discovery Architecture](https://datatracker.ietf.org/doc/draft-tldm-simple-homenet-naming/)

- **WG**: [HOMENET](https://datatracker.ietf.org/wg/homenet/about/)
- **Category**: service discovery, localnet name resolution

#### Abstract

This document describes a simple name resolution and service
discovery architecture for homenets.  This architecture covers local
publication of names, as well as name resolution for local and global
names.

### [Light-Weight Implementation Guidance WG](https://datatracker.ietf.org/wg/lwig/about/)

- **WG**: [LWIG](https://datatracker.ietf.org/wg/lwig/about/)
- **Category**:

## [Operations and Management Area (OPS)](https://datatracker.ietf.org/group/ops/about/)

### [Bootstrapping Remote Secure Key Infrastructures](https://datatracker.ietf.org/doc/draft-ietf-anima-bootstrapping-keyinfra/)

- **WG**: [ANIMA](https://datatracker.ietf.org/wg/anima/about/)
- **Category**: localnet pki bootstrap

#### Abstract

This document specifies automated bootstrapping of a remote secure
key infrastructure (BRSKI) using vendor installed X.509 certificate,
in combination with a vendor's authorizing service, both online and
offline.  Bootstrapping a new device can occur using a routable
address and a cloud service, or using only link-local connectivity,
or on limited/disconnected networks.  Support for lower security
models, including devices with minimal identity, is described for
legacy reasons but not encouraged.  Bootstrapping is complete when
the cryptographic identity of the new key infrastructure is
successfully deployed to the device but the established secure
connection can be used to deploy a locally issued certificate to the
device as well.

### [Let 'localhost' be localhost.](https://datatracker.ietf.org/doc/draft-ietf-dnsop-let-localhost-be-localhost/)

- **WG**: [DNSOP](https://datatracker.ietf.org/wg/dnsop/about/)
- **Category**: localnet top level domain name

#### Abstract

This document updates RFC6761 with the goal of ensuring that
"localhost" can be safely relied upon as a name for the local host's
loopback interface.  To that end, stub resolvers are required to
resolve localhost names to loopback addresses.  Recursive DNS servers
are required to return "NXDOMAIN" when queried for localhost names,
making non-conformant stub resolvers more likely to fail and produce
problem reports that result in updates.

Together, these requirements would allow applications and
specifications to join regular users in drawing the common-sense
conclusions that "localhost" means "localhost", and doesn't resolve
to somewhere else on the network.

## [Routing Area (RTG)](https://datatracker.ietf.org/group/rtg/about/)

## [Security Area (SEC)](https://datatracker.ietf.org/group/sec/about/)

### [Use Cases for Authentication and Authorization in Constrained Environments](https://datatracker.ietf.org/doc/rfc7744/)

- **WG**: [ACE](https://datatracker.ietf.org/wg/ace/about/)
- **Category**: device authentication, device authorization

#### Abstract

Constrained devices are nodes with limited processing power, storage
space, and transmission capacities.  In many cases, these devices do
not provide user interfaces, and they are often intended to interact
without human intervention.

This document includes a collection of representative use cases for
authentication and authorization in constrained environments.  These
use cases aim at identifying authorization problems that arise during
the life cycle of a constrained device and are intended to provide a
guideline for developing a comprehensive authentication and
authorization solution for this class of scenarios.

Where specific details are relevant, it is assumed that the devices
use the Constrained Application Protocol (CoAP) as a communication
protocol.  However, most conclusions apply generally.

### [Automatic Certificate Management Environment](https://datatracker.ietf.org/doc/draft-ietf-acme-acme/)

- **WG**: [ACME](https://datatracker.ietf.org/wg/acme/about/)
- **Category**: certificate issuance mechanism

#### Abstract

Certificates in PKI using X.509 (PKIX) are used for a number of
purposes, the most significant of which is the authentication of
domain names.  Thus, certificate authorities in the Web PKI are
trusted to verify that an applicant for a certificate legitimately
represents the domain name(s) in the certificate.  Today, this
verification is done through a collection of ad hoc mechanisms.  This
document describes a protocol that a certification authority (CA) and
an applicant can use to automate the process of verification and
certificate issuance.  The protocol also provides facilities for
other certificate management functions, such as certificate
revocation.

### [CAA Record Extensions for Account URI and ACME Method Binding](https://datatracker.ietf.org/doc/draft-ietf-acme-caa/)

- **WG**: [ACME](https://datatracker.ietf.org/wg/acme/about/)
- **Category**: certificate issuance mechanism

#### Abstract

The CAA DNS record allows a domain to communicate issuance policy to
CAs, but only allows a domain to define policy with CA-level
granularity.  However, the CAA specification also provides facilities
for extension to admit more granular, CA-specific policy.  This
specification defines two such parameters, one allowing specific
accounts of a CA to be identified by URI and one allowing specific
methods of domain control validation as defined by the ACME protocol
to be required.

### [Use of Short-Term, Automatically-Renewed (STAR) Certificates to Delegate Authority over Web Sites](https://datatracker.ietf.org/doc/draft-ietf-acme-star/)

- **WG**: [ACME](https://datatracker.ietf.org/wg/acme/about/)
- **Category**: short-term certificate, localnet

#### Abstract

This memo proposes an ACME extension to enable the issuance of short-
term and automatically renewed certificates.  This allows a domain
name owner to delegate the use of certificates to another party,
while retaining the capability to cancel this delegation at any time
with no need to rely on certificate revocation mechanisms.

### [Generating Certificate Requests for Short-Term, Automatically-Renewed (STAR) Certificates](https://datatracker.ietf.org/doc/draft-sheffer-acme-star-request/)

- **WG**: [ACME](https://datatracker.ietf.org/wg/acme/about/)
- **Category**: short-term certificate, localnet

#### Abstract

This memo proposes a protocol that allows a domain name owner to
delegate to a third party (such as a CDN) control over a certificate
that bears one or more names in that domain.  Specifically the third
party creates a Certificate Signing Request for the domain, which can
then be used by the domain owner to request a short term and
automatically renewed (STAR) certificate.

This is a component in a solution where a third-party such as a CDN
can terminate TLS sessions on behalf of a domain name owner (e.g., a
content provider), and the domain owner can cancel this delegation at
any time without having to rely on certificate revocation mechanisms.

### [Web Authorization Protocol WG (OAUTH)](https://datatracker.ietf.org/wg/oauth/documents/)

- **WG**: [OAUTH](https://datatracker.ietf.org/wg/oauth/documents/)
- **Category**:

### [A DANE Record and DNSSEC Authentication Chain Extension for TLS](https://datatracker.ietf.org/doc/draft-ietf-tls-dnssec-chain-extension/)

- **WG**: [TLS](https://datatracker.ietf.org/wg/tls/about/)
- **Category**: certificate verification

#### Abstract

This draft describes a new TLS extension for transport of a DNS
record set serialized with the DNSSEC signatures needed to
authenticate that record set.  The intent of this proposal is to
allow TLS clients to perform DANE authentication of a TLS server
without needing to perform additional DNS record lookups.  It will
typically not be used for general DNSSEC validation of TLS endpoint
names.

### [Exported Authenticators in TLS](https://datatracker.ietf.org/doc/draft-ietf-tls-exported-authenticator/)

- **WG**: [TLS](https://datatracker.ietf.org/wg/tls/about/)
- **Category**: certificate verification

#### Abstract

This document describes a mechanism in Transport Layer Security (TLS)
to provide an exportable proof of ownership of a certificate that can
be transmitted out of band and verified by the other party.

### [Data Center use of Static Diffie-Hellman in TLS 1.3](https://datatracker.ietf.org/doc/draft-green-tls-static-dh-in-tls13/)

- **WG**: [TLS](https://datatracker.ietf.org/wg/tls/about/)
- **Category**: tls1.3 specification

#### Abstract

Unlike earlier versions of TLS, current drafts of TLS 1.3 have
instead adopted ephemeral-mode Diffie-Hellman and elliptic-curve
Diffie-Hellman as the primary cryptographic key exchange mechanism
used in TLS.  This document describes an optional configuration for
TLS servers that allows for the use of a static Diffie-Hellman
private key for all TLS connections made to the server.  Passive
monitoring of TLS connections can be enabled by installing a
corresponding copy of this key in each monitoring device.

### [Delegated Credentials for TLS](https://datatracker.ietf.org/doc/draft-rescorla-tls-subcerts/) **[expired]**

- **WG**: [TLS](https://datatracker.ietf.org/wg/tls/about/)
- **Category**: tls credential extension

#### Abstract

The organizational separation between the operator of a TLS server
and the certificate authority that provides it credentials can cause
problems, for example when it comes to reducing the lifetime of
certificates or supporting new cryptographic algorithms.  This
document describes a mechanism to allow TLS server operators to
create their own credential delegations without breaking
compatibility with clients that do not support this specification.

## [Transport Area (TSV)](https://datatracker.ietf.org/group/tsv/about/)

### [QUIC WG](https://datatracker.ietf.org/wg/quic/about/)

- **WG**: [QUIC](https://datatracker.ietf.org/wg/quic/about/)
- **Category**:

## [Internet Research Task Force (IRTF)](https://irtf.org)

### [Requirements for Password-Authenticated Key Agreement (PAKE) Schemes](https://datatracker.ietf.org/doc/rfc8125/)

- **RG**: [CFRG](https://datatracker.ietf.org/rg/cfrg/about/)
- **Category**: password authenticated key exchange

#### Abstract

Password-Authenticated Key Agreement (PAKE) schemes are interactive
protocols that allow the participants to authenticate each other and
derive shared cryptographic keys using a (weaker) shared password.
This document reviews different types of PAKE schemes.  Furthermore,
it presents requirements and gives recommendations to designers of
new schemes.  It is a product of the Crypto Forum Research Group
(CFRG).

### [Alternative Network Deployments: Taxonomy, Characterization, Technologies, and Architectures](https://datatracker.ietf.org/doc/rfc7962/)

- **RG**: [GAIA](https://datatracker.ietf.org/rg/gaia/about/)
- **Category**: localnet, taxonomy

#### Abstract

This document presents a taxonomy of a set of "Alternative Network
Deployments" that emerged in the last decade with the aim of bringing
Internet connectivity to people or providing a local communication
infrastructure to serve various complementary needs and objectives.
They employ architectures and topologies different from those of
mainstream networks and rely on alternative governance and business
models.

The document also surveys the technologies deployed in these
networks, and their differing architectural characteristics,
including a set of definitions and shared properties.

The classification considers models such as Community Networks,
Wireless Internet Service Providers (WISPs), networks owned by
individuals but leased out to network operators who use them as a
low-cost medium to reach the underserved population, networks that
provide connectivity by sharing wireless resources of the users, and
rural utility cooperatives.

### [Thing-to-thing RG (T2TRG)](https://datatracker.ietf.org/rg/t2trg/documents/)

- **RG**: [T2TRG](https://datatracker.ietf.org/rg/t2trg/documents/)
- **Category**:

## [Independent Submissions](https://www.rfc-editor.org/about/independent/)

### [J-PAKE: Password-Authenticated Key Exchange by Juggling](https://datatracker.ietf.org/doc/rfc8236/)

- **Category**: password authenticated key exchange

#### Abstract

This document specifies a Password-Authenticated Key Exchange by
Juggling (J-PAKE) protocol.  This protocol allows the establishment
of a secure end-to-end communication channel between two remote
parties over an insecure network solely based on a shared password,
without requiring a Public Key Infrastructure (PKI) or any trusted
third party.
