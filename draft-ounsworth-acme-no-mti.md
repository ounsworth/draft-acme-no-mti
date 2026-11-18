---
title: "ACME No Mandatory-To-Implement JWT Algorithm"
abbrev: "acme-no-mti"
category: info

docname: draft-ounsworth-acme-no-mti-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
updates: 8555
date:
consensus: true
v: 3
area: AREA
workgroup: WG Working Group
keyword:
 - next generation
 - unicorn
 - AI-native
venue:
  group: WG
  type: Working Group
  mail: WG@example.com
  arch: https://example.com/WG
  github: USER/REPO
  latest: https://example.com/LATEST

author:
 -
    fullname: "Mike Ounsworth"
    organization: Your Organization Here
    email: "mike@ounsworth.ca"

normative:

informative:

...

--- abstract

The ACME protocol specified in RFC8555 requires all implementations to support the signature algorithm EDCSA-P256 (ES256) and recommends support for Ed25519. Due to the risk of quantum computers, this mandatory-to-implement algorithm is removed, leaving no MTI algorithms for the JWT layer of ACME and leaving this instead up to deployment configuration.


--- middle

# Update to RFC8555 {#intro}

Due to the impending risks of Cryptographically-Relevant Quantum Computers (CRQCs), {{!RFC8555}} is updated to remove the following sentence from Section 6.2:

> An ACME server MUST implement the "ES256" signature algorithm
   [RFC7518] and SHOULD implement the "EdDSA" signature algorithm using
   the "Ed25519" variant (indicated by "crv") [RFC8037].

It is replaced with nothing, acknowledging that any signature algorithm allowed by {{?RFC7518}} or its updates are allowed in ACME. The ACME Server is ultimately responsible for deciding which signature algorithms it will accept for ACME Client account keys.

# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations {#security}

This document enhances security by removing the requirement for implementations to support soon-to-be-weak algorithms and defers responsibility for algorithm selection to both the JWT specification and ACME Server operators.


# IANA Considerations {#iana}

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
