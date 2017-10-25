# Requirements for HTTPS/WSS in Local Network

This section outlines functional and non-functional requirements of HTTPS/WSS usage in local network represented in [UseCases.md](UseCases.md).

Functional requirements consist of device discovery, device identification, certificate issuance, and certificate management and lifecycle.

Non-functional requirements address user experience and security aspects of HTTPS/WSS usage in local network.

*Note that currently this document only describes the requirements for the use cases where the UA and the device communicates within the local network. Additional cases where the UA communicates with the device via a gateway in the public IP address scope is being discussed in [the corresponding GitHub issue](https://github.com/httpslocal/usecases/issues/13).*

## <a name=“functional-requirements”></a>Functional Requirements

### <a name=“terminology”></a>Terminology

A device is in the same local network as the user agent (UA), capable of HTTPS/WSS server,  compliant with [certificate grant and issuance](#certificate-grant-and-issuance) and [certificate management](#certificate-management), and notifies the UA of the capability during [device discovery](#device-discovery).

A pre-installed certificate is a self-signed server certificate statically installed in the device.

A device CA is a certificate authority, and issues a short-term self-signed server certificate to a device authenticated by the UA.

### <a name=“device-discovery”></a>Device Discovery

- The UA shall be able to discover the presence of devices in the same local network.
- The UA shall be able to obtain the endpoint URL of the device which has the scheme `https:` or `wss:` and its compliance with [certificate grant and issuance](#certificate-grant-and-issuance) and [certificate management](#certificate-management).

### <a name=“device-identification”></a>Device Identification

- To identify the device as the [discovered](#device-discovery) one explicitly selected by the user, the UA shall authenticate it before granting or issuing a certificate for the device.
- The UA shall ask the user to input information to identify the device when the device requests to do so, and notify the device of the information, so that the UA and the device can properly authenticate with each other.
	- Information to identify may be one of the following forms: PIN code or passphrase displayed or labeled on the device, NFC tag, etc.
- The UA shall only expose the interface to the authenticated device to web applications.
- The UA shall initiate [certificate grant and issuance](#certificate-grant-and-issuance) procedure when the device is identified properly.

### <a name=“certificate-grant-and-issuance”></a>Certificate Grant and Issuance

- The device shall be able to have at least one of the following types of TLS server certificates so that an origin of the connection with the device becomes [potentially trustworthy](https://w3c.github.io/webappsec-secure-contexts/#potentially-trustworthy-origin) in a certain period:
	- a pre-installed certificate granted on the web application’s origin
	- a certificate issued by the device CA
- If the web server allows the UA to grant the pre-installed certificate of the device in its web application’s origin, the web server shall be able to provide the UA with a hint about the certificate to be granted.
- If the device requires a certificate issued by the device CA, the device shall request the device CA to issue a certificate for the device when the user grants.
- The device CA shall verify certificate issuing request from both the device and the UA before issuing a certificate to the device.
- The certificate shall have a reasonably short expiration period.

### <a name=“certificate-management”></a>Certificate Management

- The UA shall ask the user if the user grants the renewal of the certificate when the certificate is expired during [device identification](#device-identification), [certificate grant and issuance](#certificate-grant-and-issuance), or communication with the device.
- The UA shall be able to revoke the certificate when the user decides to do so.
- The certificate issued by the device CA shall be able to be revoked by the device CA when necessary.

## <a name=“non-funcational-requirements”>Non-Functional Requirements

### <a name=“privacy-and-security></a>Privacy and Security

- [Device identification](#device-identification) and [certificate grant and issuance](#certificate-grant-and-issuance) should prevent passive network eavesdroppers from learning messages related to identification or certificate passed between the UA and the device.
- [Device identification](#device-identification) and [certificate grant and issuance](#certificate-grant-and-issuance) should prevent active network attackers from impersonating a device and observing or altering data intended for the UA.

### <a name=“user-experience”></a>User Experience

- The UA should minimize user’s interaction for [device identification](#device-identification) as much as possible.
- The procedure of [certificate grant and issuance](#certificate-grant-and-issuance) should be automated as much as possible so that the user’s interaction can be minimized.