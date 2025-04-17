---
title: "Registration Protocol for Encrypted PDMv2 (PDMv2-REG)"
abbrev: "draft-elkins-ippm-pdmv2-reg"
category: std

docname: draft-elkins-ippm-pdmv2-reg-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 0
area: "Transport"
workgroup: "IP Performance Measurement"
keyword:

 - Extension Headers
 - IPv6
 - PDMv2
 - Performance
 - Diagnostic
venue:
  group: "IP Performance Measurement"
  type: "Working Group"
  mail: "ippm@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/ippm/"
  github: "ameyand/PDMv2-Registration"
  latest: "https://ameyand.github.io/PDMv2-Registration/draft-elkins-ippm-pdmv2-reg.html"

author:
-

    fullname: Nalini Elkins
    country: United States
    organization: Inside Products, Inc.
    email: "nalini.elkins@insidethestack.com"

 -
    fullname: Michael Ackermann
    country: United States
    organization: BCBS Michigan
    email: "mackermann@bcbsm.com"

 -
    fullname: Ameya Deshpande
    country: India
    organization: NITK Surathkal/Google
    email: "ameyanrd@gmail.com"

 -
    fullname: Tommaso Pecorella
    country: Italy
    organization: University of Florence
    email: "tommaso.pecorella@unifi.it"

normative:

informative:


--- abstract

This document defines a lightweight registration protocol used by
endpoints wishing to participate in the encrypted Performance and
Diagnostic Metrics Version 2 (PDMv2) exchange. This protocol
establishes authenticated identities and shared cryptographic secrets
to enable encryption, integrity, and authentication for subsequent
PDMv2 traffic. The protocol is designed to minimize overhead while
ensuring robust security through the use of Hybrid Public Key
Encryption (HPKE).

--- middle

# Introduction

RFC 8250 defines the Performance and Diagnostic Metrics (PDM) Destination
Option for IPv6. PDMv2 enhances this functionality by introducing
confidentiality, integrity, and authentication via encryption. This document
specifies a registration protocol that enables secure and authenticated key
establishment for encrypted PDMv2 communication.

The purpose of the Registration Phase is to create shared cryptographic
contexts (secrets) among the communicating entities. This phase is entirely
independent of the Data Transfer Phase. Once registration is complete,
encrypted PDMv2 data can be transmitted. PDMv2 also allows operation in an
unencrypted mode, which may be used in trusted user domains where encryption
is unnecessary.

In large enterprise environments, where multiple clients and servers exist
across various locations, key management complexity can become a significant
challenge. This document introduces the Primary Client and Master Server
model as an optimization to simplify key distribution, making key management
lightweight and reducing the overall overhead in complex networks.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Terminology

{:req1: style="empty"}

{: req1}
- Client: The endpoint initiating the PDMv2 communication.
- Server: The endpoint responding to the Client.
- Authentication Server: An optional entity that manages certificates and
identities.
- Master Key: A long-lived key shared only between the client and server.
- SessionTemporaryKey: A key derived per session via a Key Derivation
Function (KDF).
- HPKE: Hybrid Public Key Encryption (RFC 9180).

# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
