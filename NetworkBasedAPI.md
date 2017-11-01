# Network based API via HTTPS in local network

This document summarizes how HTTPS local in local network can mitigate the security risk on Network based API.

## Network based API
Network based API is a type of API(Application Programing Interface) which is provided via the network interface of 'localhost' server on a device. A web application can communicate with the device and its peripherals via Networked based APIs instead of JavaScript APIs natively supported by browsers.
For example, React VR uses a Network based API to communicate with Oculus Rift connected to PC or Mac  [[1]](https://facebook.github.io/react-vr/docs/getting-started.html).
W3C(World Wide Web Consortium) has been publishing the standards of JavaScript APIs. Recently, some of groups in W3C work on the standardization of Network based API instead of JavaScript APIs. For example, the Automotive Working Group discusses on Vehicle Information API Specification [[2]](https://www.w3.org/TR/vehicle-information-api/).

## Plugins and extensions
In past, browser plugins and extensions have been well used as a way to extend features and capabilities of browsers. Because of the security concern on browser plugin as described in the Wiki page [[3]](https://en.wikipedia.org/wiki/Browser_security#Plugins_and_extensions), nowadays, major browser vendors let users to install browser plugin only thru their marketplaces, though users can still install a third-party extension on their risks.

> Plugins and extensions:
Although not part of the browser per se, browser plugins and extensions extend the attack surface, exposing vulnerabilities in Adobe Flash Player, Adobe (Acrobat) Reader, Java plugin, and ActiveX that are commonly exploited. Malware may also be implemented as a browser extension, such as a browser helper object in the case of Internet Explorer. Browsers like Google Chrome and Mozilla Firefox can block—or warn users of—insecure plugins [[3]](https://en.wikipedia.org/wiki/Browser_security#Plugins_and_extensions)

## Security Concern
Network based API is more safety than plugins and extensions because a malicious 'localhost' server and vulnerabilities of a 'localhost' server can not directly attack on the context of browser and web application. However, the Network based API would be still a security hole of browsers. For example, a user may unintentionally install a malicious native application from a application Market for smartphone and it will attack a web application via Networked API which is provided by the localhost server of the native application. Of course,  some developers can take care of security risks and have application level of authentication and encryption on their Network based API, however it would be useful that any browser supports a standard way to mitigate the security risk.

## HTTPS in local network
If HTTPS can be used for Network based API, browsers can handle a 'localhost' server is trustworthy as well as  secure origins on the web. Browsers can also restrict Network based API if critical security vulnerabilities of the secure origin server has not been fixed.
HTTP Local Network Community Group has been discussed the use case and the requirements to use HTTPS in local network. We hope that a solution which meet the requirements would mitigate the security risk of Network Based API. Also, Networked based API will become more extensible by hosting a server not only on 'localhost' interface but also on local network. It should be noted that application-level authentication for access control still works over HTTPS.

## References
[1] [https://facebook.github.io/react-vr/docs/getting-started.html](https://facebook.github.io/react-vr/docs/getting-started.html)  
[2] [https://www.w3.org/TR/vehicle-information-api/](https://www.w3.org/TR/vehicle-information-api/)  
[3]
[https://en.wikipedia.org/wiki/Browser_security#Plugins_and_extensions](https://en.wikipedia.org/wiki/Browser_security#Plugins_and_extensions)
