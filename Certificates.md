# What type of TLS server certificates should we adopt for HTTPS/WSS in local network ?

To realize HTTPS/WSS communication in local network, especially between UAs and devices, we have to consider the types of TLS server certificates issued to the devices and go through the pros and cons of each type.

## Index
- Public CA Certificate
- Self-signed Certificate
- Private CA Certificate
 
## Public CA Certificate

### Public CA Certificate for the devices accessible globally.

- How to issue
    1. The method of [Things Gateway by Mozilla](http://iot.mozilla.org/gateway/) ([Let's Encrypt](https://letsencrypt.org/) with [PageKite](https://pagekite.net/)).
    1. etc.
- Pros
    - There is no need to extend the UA implementation to regard the certificates as trusted ones.
- Cons
    - A UA cannot get acccess to the device when the upstream internet connection is down.
    - The domain name of the device is disclosed globally because it must be registered in public DNS servers.
    - The device is put in danger of DoS/DDoS because the device is reachable from everywhere in the internet.
    - (Some manual operations or intermediate nodes are needed to make the device public.)

### Public CA Certificate for the devices accessible only in local network.

- How to issue
    1. The method of [PLEX](https://blog.filippo.io/how-plex-is-doing-https-for-all-its-users/).
    1. A kind of delegation method inspired on [Delegated Credentials](https://tools.ietf.org/html/draft-rescorla-tls-subcerts-00) or [STAR Certificates](https://tools.ietf.org/html/draft-ietf-acme-star-01)
        - (TODO: develop the system to issue this type of certificates and confirm the feasibility.)
    1. etc.
- Pros
    - There is no need to extend the UA implementation to regard the certificates as trusted ones.
- Cons
    - A UA cannot get acccess to the device when the upstream internet connection is down.
    - The domain name of the device is disclosed globally because it must be registered in public DNS servers.

## Self-signed Certificate (for the devices accessible only in local network)

(TODO: consider whether the certificate can be acceptable in terms of security.)

- How to issue
    1. Granted by user only
        - (TODO: explain the system in detail.)
    1. Granted by user on a specific web application's origin and Guaranteed by UA and device with [CORS-preflight request + Access-Control-{Request,Allow}-External](https://wicg.github.io/cors-rfc1918/#headers) proposed in [CORS and RFC1918](https://wicg.github.io/cors-rfc1918/)
        - (TODO: explain the system in detail.)
    1. etc.
- Pros
    - A UA can get acccess to the device even if the upstream internet connection is down.
    - The domain name of the device is not disclosed globally. There is no such privacy concerns.
- Cons
    - UA implementation has to be extented to regard the certificates as trusted ones.

### Private CA Certificate (for the devices accessible only in local network)

- How to issue
    1. Issued by a private certificate authority for devices (device CA) explicitly granted by the user.
        - (TODO: develop the system to issue this type of certificates and confirm the feasibility.)
    1. etc.
- Pros
    - A UA can get acccess to the device even if the upstream internet connection is down.
    - The domain name of the device is not disclosed globally. There is no such privacy concerns.
- Cons
    - UA implementation has to be extented to regard the certificates as trusted ones.

## References

- [Things Gateway by Mozilla](http://iot.mozilla.org/gateway/)
- [Let's Encrypt](https://letsencrypt.org/)
- [PageKite](https://pagekite.net/)
- [How Plex is doing HTTPS for all its users](https://blog.filippo.io/how-plex-is-doing-https-for-all-its-users/)
- [Delegated Credentials for TLS](https://tools.ietf.org/html/draft-rescorla-tls-subcerts-00)
- [Use of Short-Term, Automatically-Renewed (STAR) Certificates to Delegate Authority over Web Sites](https://tools.ietf.org/html/draft-ietf-acme-star-00)
- [CORS and RFC1918](https://wicg.github.io/cors-rfc1918/)
