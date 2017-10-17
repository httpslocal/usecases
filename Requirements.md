# Requirements for HTTPS/WSS in Local Network

This section outlines functional and non-functional requirements of HTTPS/WSS usage in local network represented in [UseCases.md](UseCases.md).

Functional requirements consist of device discovery, device authentication, certificate issuance, and certificate management and lifecycle.

Non-functional requirements address user experience and security aspects of HTTPS/WSS usage in local network.

## <a name=“functional-requirements”></a>Functional Requirements

### <a name=“terminology”></a>Terminology

A device is in the same local network as the user agent (UA), capable of HTTPS/WSS server,  compliant with [certificate grant and issuance](#certificate-grant-and-issuance) and [certificate management](#certificate-management), and notifies the UA of the capability during [device discovery](#device-discovery).

A device delegate is in the public IP address network, has the certificate issued for the device, and relays messages between the UA and the device. Device discovery through the device delegate is out of scope.

### <a name=“device-discovery”></a>Device Discovery

- The UA shall be able to discover the presence of devices in the same local network.
- The UA shall be able to obtain the endpoint URL of the device which has the scheme `https:` or `wss:` and its compliance with [certificate grant and issuance](#certificate-grant-and-issuance) and [certificate management](#certificate-management).

### <a name=“device-authenticaion”></a>Device Authentication

- The UA shall authenticate one of the [discovered](#device-discovery) device selected by the user.
- The UA shall authenticate one of the devices registered in the device delegate selected on the web application.
- The UA shall ask the user to input information such as PIN code or passphrase when the device requests to do so, and notify the device of the information, so that the UA and the device or the device delegate can properly authenticate with each other.
- The UA shall only expose the interface to the authenticated device to web applications.
- The UA shall initiate [certificate grant and issuance](#certificate-grant-and-issuance) procedure when the device or the device delegate is authenticated successfully.
- The UA shall be able to authenticate the device or the device delegate automatically without the user’s grant when it has been authenticated once and its certificate has not been expired or revoked yet.

### <a name=“certificate-grant-and-issuance”></a>Certificate Grant and Issuance

#### <a name=“local-network-certificate”></a>Certificate for Local Network

- The device shall be able to have at least one of the following types of TLS server certificates so that an origin of the connection with the device becomes [potentially trustworthy](https://w3c.github.io/webappsec-secure-contexts/#potentially-trustworthy-origin) in a certain period:
	- a self-signed certificate explicitly granted by the user (*TODO: consider whether this item is appropriate or not in terms of security*)
	- a self-signed certificate granted on the web application’s origin explicitly by the user
	- a certificate issued by a private certificate authority for devices (device CA) explicitly granted by the user
- The device shall be able to verify whether or not the certificate is either granted by the user or properly issued by the device CA.
- The web server shall be able to provide the UA with a hint about the certificates to be granted on the web application’s origin.
- The device CA shall automatically issue a certificate for the device when the user grants and the device requests.
- The device CA shall verify certificate issuing request from both the device and the UA before issuing a certificate to the device.
- The certificate shall have a reasonably short expiration period.

#### <a name=“certificate-for-delegate”></a>Certificate for Device Delegate

- The device delegate shall be able to have a TLS server certificate issued by the publicly trusted certificate authority (public CA) through an automated procedure so that an origin of the connection with the device becomes [potentially trustworthy](https://w3c.github.io/webappsec-secure-contexts/#potentially-trustworthy-origin).
- The public CA shall automatically issue a certificate for the device delegate when the user grants and the device behind the device delegate requests.
- The certificate shall have a reasonably short expiration period.

### <a name=“certificate-management”></a>Certificate Management

- The UA shall ask the user if the user grants the renewal of the certificate when the certificate is expired during [device authentication](#device-authentication), [certificate grant and issuance](#certificate-grant-and-issuance), or communication with the device.
- The UA shall be able to revoke the certificate when the user decides to do so.
- The certificate issued by the device CA shall be able to be revoked by the device CA when necessary. (Note that the root CA can revoke the ceritficate issued by it through OCSP.)

## <a name=“non-funcational-requirements”>Non-Functional Requirements

### <a name=“privacy-and-security></a>Privacy and Security

- [Device authentication](#device-authentication) and [certificate grant and issuance](#certificate-grant-and-issuance) should prevent passive network eavesdroppers from learning messages related to authentication or certificate passed between the UA and the device.
- [Device authentication](#device-authentication) and [certificate grant and issuance](#certificate-grant-and-issuance) should prevent active network attackers from impersonating a device and observing or altering data intended for the UA.

### <a name=“user-experience”></a>User Experience

- The UA should minimize user’s interaction for authentication as much as possible.
- The procedure of [certificate grant and issuance](#certificate-grant-and-issuance) should be automated as much as possible so that the user’s interaction can be minimized.