# What type of TLS server certificates should we adopt for HTTPS/WSS in local network ?

To realize HTTPS/WSS communication in local network, especially between UAs and devices, we have to consider the types of TLS server certificates issued to the devices and go through the pros and cons of each type.

## Index

- [Terminology](#terminology)
- [Public CA Certificate](#public-ca-certificate)
- [Private CA Certificate](#private-ca-certificate)
- [Self-signed Certificate](#self-signed-certificate)

## Terminology

- UA (User Agent): Web browser.
- Device: HTTPS/WSS server-capable device in local network.
- Public CA: CA (Certificate Authority) which issues server certificates to the devices. The certificates (hereafter, Public CA certificates) can chain up to root CAs which are regarded as the trusted ones by the UA.
- Private CA: CA (Certificate Authority) which issues server certificates to the devices. The certificates (hereafter, Private CA certificates) can not chain up to the root CAs. Ideally, the CA issues a PSK or a certificate for the device's bootstrapping to the device manufacturer in advance and issues the certificates by verifying the pre-issued credential.
- Web application: Web apprication wich gets access to the device via its frontend running on the UA in local network. There is a case that it takes the CA role mentioned above.

## Public CA Certificate

### Public CA Certificate for the devices accessible globally.

- How to issue
    1. The method of [Things Gateway by Mozilla](http://iot.mozilla.org/gateway/) ([Let's Encrypt](https://letsencrypt.org/) with [PageKite](https://pagekite.net/)).
    1. etc.
- Pros
    - There is no need to extend the UA implementation to regard the certificates as trusted ones.
    - The device can get the certificate in a standardized way. (ACME)
- Cons
    - A UA cannot get access to the device when the upstream internet connection is down.
    - The domain name of the device is disclosed globally because it must be registered in public DNS servers.
    - The device is put in danger of DoS/DDoS because the device is reachable from everywhere in the internet.

### Public CA Certificate for the devices accessible only in local network.

- How to issue
    1. A kind of delegation method inspired on [Delegated Credentials](https://tools.ietf.org/html/draft-rescorla-tls-subcerts-00) or [STAR Certificates](https://tools.ietf.org/html/draft-ietf-acme-star-01)
        - (TODO: develop the system to issue this type of certificates and confirm the feasibility.)
    1. The method of [PLEX](https://blog.filippo.io/how-plex-is-doing-https-for-all-its-users/).
    1. etc.
- Pros
    - There is no need to extend the UA implementation to regard the certificates as trusted ones.
- Cons
    - A UA cannot get access to the device when the upstream internet connection is down.
    - The domain name of the device is disclosed globally because it must be registered in public DNS servers.

## Private CA Certificate

- How to issue
    1. Issued by a private certificate authority for devices (device CA) explicitly granted by the user.
        - An example of this solution was proposed in a breakout session held in TPAC 2016 ([".local" Server Certificate for HTTPS migration on local network](https://www.w3.org/wiki/images/3/37/2016.w3c.breakout_session.dot-local-server-cert.p.pdf)).
        - (TODO: develop the system to issue this type of certificates and confirm the feasibility.)
    1. etc.
- Pros
    - A UA can get access to the device even if the upstream internet connection is down.
    - The domain name of the device is not disclosed globally. There is no such privacy concerns.
- Cons
    - UA implementation has to be extended to regard the certificates as trusted ones.
        - For now, there is no consensus about whether this sort of certificate can be acceptable for UA.

## Self-signed Certificate

(TODO: consider whether the certificate can be acceptable in terms of security.)

- How to issue
    1. Granted by user only
        - (TODO: explain the system in detail.)
    1. Granted by user on a specific web application's origin and Guaranteed by UA and device with [CORS-preflight request + Access-Control-{Request,Allow}-External](https://wicg.github.io/cors-rfc1918/#headers) proposed in [CORS and RFC1918](https://wicg.github.io/cors-rfc1918/)
        - (TODO: explain the system in detail.)
    1. etc.
- Pros
    - A UA can get access to the device even if the upstream internet connection is down.
    - The domain name of the device is not disclosed globally. There is no such privacy concerns.
- Cons
    - UA implementation has to be extended to regard the certificates as trusted ones.

## References

- [Things Gateway by Mozilla](http://iot.mozilla.org/gateway/)
- [Let's Encrypt](https://letsencrypt.org/)
- [PageKite](https://pagekite.net/)
- [How Plex is doing HTTPS for all its users](https://blog.filippo.io/how-plex-is-doing-https-for-all-its-users/)
- [Delegated Credentials for TLS](https://tools.ietf.org/html/draft-rescorla-tls-subcerts-00)
- [Use of Short-Term, Automatically-Renewed (STAR) Certificates to Delegate Authority over Web Sites](https://tools.ietf.org/html/draft-ietf-acme-star-00)
- [".local" Server Certificate for HTTPS migration on local network](https://www.w3.org/wiki/images/3/37/2016.w3c.breakout_session.dot-local-server-cert.p.pdf)
- [CORS and RFC1918](https://wicg.github.io/cors-rfc1918/)

