---
title: "Registration Protocol for Encrypted PDMv2 (PDMv2-REG)"
abbrev: "draft-elkins-ippm-pdmv2-reg"
category: info

docname: draft-elkins-ippm-pdmv2-reg-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: ""
workgroup: "IP Performance Measurement"
keyword:
 - next generation
 - unicorn
 - sparkling distributed ledger
venue:
  group: "IP Performance Measurement"
  type: ""
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
  RFC6733:
  RFC8250:


informative:


--- abstract

This document specifies a registration protocol for use with
Performance and Diagnostic Metrics version 2 (PDMv2). This
registration process enables endpoints to communicate supported
policies and capabilities in advance of measurement sessions,
simplifying setup and enhancing security. The protocol defines a set
of commands, responses, and message formats, and proposes
integration with the Diameter Base Protocol (RFC 6733) as the
transport and authentication mechanism.


--- middle

# Introduction

Performance and Diagnostic Metrics (PDM) defined in [RFC8250] allow
for enhanced diagnostics of packet delay and network behavior.
PDMv2 builds upon this by requiring prior registration of
participating endpoints to negotiate policies, authentication, and
encryption modes.

A robust registration mechanism allows Clients, Servers, and
Analyzers to declare their role, supported cipher suites, and
address ranges. This draft defines such a protocol using Diameter
as the transport, given its extensibility and robust AAA
Capabilities.

# Why Diameter?

Diameter [RFC6733] defines a framework for AAA services, and is
extensible for different applications through extensions. Given
the requirement of PDMv2 registration protocol, the use of a
standard-based AAA system seems to be logical.

RFC6733 defines various entities that can be mapped to the PDMv2
entities (client, server, analyzer, AS). In the Diameter
terminology, the AS could be mapped to a “Proxy Agent”, which can
enforce policy rules, e.g., preventing the clients from requesting
a connection to a server.

All the other entities can be configured as “Peers”, with specific
application TLVs describing their operations.

Note: The use of Diameter in the PDMv2 context will require the
definition of an “application” specific to PDMv2, specific AVP,
and message formats.

The decision to use Diameter will also need to be validated through
a PoC.

# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
