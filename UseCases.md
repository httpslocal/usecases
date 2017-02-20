# Use Cases of HTTPS/WSS in Local Network

This document describes use cases where browsers communicate with web-server-capable via HTTP and/or WebSocket over TLS.
These use cases are intended to clarify requirements in terms of network (topology, protocol, etc.) and security
(privacy concern, issuing a certificate, validation, etc.).

## UC-01: Access audio contents in a home storage from a cloud service

Users can store their audio contents in their storace device, or set-top boxes, in their home.
They access online music web services with web browsers, and use a music player implemented as a web application
in the web services to play music stored in their home network.
The music player send metadata of the music to the web service, to recommend another music contents.