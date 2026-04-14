---
title: >
    A Proposal for Long-Term Expansion of the North American
               Numbering Plan (NANP) to 11 Digits
abbrev: NANP Expansion
docname: draft-robinson-nanp-expansion-00
category: info
date: 2026-04-14
wg: Network Working Group

ipr: trust200902
keyword: Internet-Draft
area: General
submissiontype: independent
workgroup: Network Working Group

stand_alone: true
pi:
   toc: yes
   tocdepth: 3
   sortrefs: yes
   symrefs: yes

author:
  - ins: P. Robinson
    name: Paul Robinson
    org: Independent
    email: comments@11digitdialing.com

normative:
  RFC2119:
  RFC8174:
  ITU:
   author:
     - org: International Telecommunications Union
   title: "The international public telecommunication numbering plan Recommendation ITU-T E.164"
   date: November 2010
   format:
      PDF: https://www.itu.int/rec/dologin_pub.asp?lang=e&id=T-REC-E.164-201011-I!!PDF-E&type=items

informative:
   RFC1394:
 
--- abstract 

The North American Numbering Plan (NANP) is projected to exhaust 
available telephone numbering resources within the coming decades under
current allocation and utilization trends. Existing mitigation 
strategies, including area code overlays and number pooling, extend the
usable life of the NANP but introduce increasing operational complexity 
and user confusion.

This document proposes a long-term, uniform expansion of NANP telephone 
numbers from 10 to 11 digits through extension of the area code or 
Numbering Plan Area (NPA) from 3 to 4 digits. The  proposal emphasizes 
backward compatibility, fixed-length numbering, and a multi-phase 
transition strategy designed to minimize disruption.  This document is 
intended to stimulate discussion and does not represent the position of
any standards body or regulatory authority.

--- middle

# Introduction

The NANP currently utilizes a fixed-length 10-digit numbering format
(NPA-NXX-XXXX). Growth in telecommunications services, device 
proliferation, and number portability has steadily increased demand for
numbering resources.

Mitigation strategies such as overlays and thousands-block number 
pooling have delayed exhaustion but introduce increasing complexity in
routing, administration, and user experience.

This document explores a uniform expansion of NANP numbers to 11 digits
as a long-term solution.

# Requirements Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED",
"MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they
appear in all capitals, as shown here.

# Definitions

CP
: Cellular Provider, the provider of service for a caller using 
cellular telephony.

IXC
: Inter-eXchange Carrier - the organization that carries a call between
the caller's service provider and the called party's service provider 
where the caller's service provider does not serve the area of the 
called party.

LEC
: Local Exchange Carrier, or provider of service for a caller using a
land line or VOIP service, the organization that provides dial tone and
carries a call to the called party where they are within the service 
area of the LEC, or transfers the call to an IXC where they are not.

N versus X
: In the context of a telephone number, N is used to indicate a digit
that is restricted to values of 2 through 9, while X indicates an 
unrestricted digit with the values 0 through 9.

NPA
: The area code, or first three digits of the 10-digit telephone number. 

NPAX
: The new area code, or first four digits of the new 11-digit telephone
number. This proposal recommends expansion of the NPA field by 1 digit 
and provides an expansion of the entire phone number to 11 digits.

NXX
: The prefix, or digits four through six of the 10-digit telephone 
number, or first three digits of the subscriber number. This field is 
to remain unchanged, but is moved to digits five through seven of the 
new 11-digit telephone number.

SIT tone
: A Special Information Tone (SIT) is a standardized, three-beep audio
signal (typically 950/1400/1800 Hz) played before a recorded 
announcement to indicate a telephone call has failed.

Subscriber number
: The portion of the telephone number following the NPA or as this 
proposal recommends, NPAX.

VOIP
: Voice Over IP, or telephone service where the call initiates from or
terminates via the Internet.

XXXX
: The last four digits of the subscriber number, or line number, digits
seven through ten of the 10-digit telephone number. This field is also 
to remain unchanged, but is moved to digits eight through eleven of the 
new 11-digit telephone number.

# Problem Statement

The current NANP faces several challenges:

- Finite NPA capacity under existing numbering rules
- Fragmentation of numbering resources due to allocation practices
- Growing operational complexity in routing and database systems
- Long lead times required for major numbering plan changes

A long-term solution should address these challenges while minimizing 
disruption to existing systems and users.

All feasible approaches to expanding NANP numbering capacity introduce
some degree of disruption. The proposed expansion of the NPA is 
considered the least disruptive option, as it preserves the existing 
hierarchical structure of the numbering plan and minimizes changes to 
subscriber numbering and routing semantics.

# Design Goals

The proposed solution is guided by the following goals:

- Maintain fixed-length numbering
- Minimize changes to existing routing logic
- Preserve compatibility with existing numbering structures
 
# Non-Goals

The following approaches are explicitly not considered desirable:

- Variable-length telephone numbers
- Region-specific numbering formats
- Frequent or repeated structural changes to the numbering plan
- Solutions requiring rapid or "flash cut" transitions

# Proposed Expansion Model

This document proposes expanding NANP numbers from 10 to 11 digits by
extending the NPA from three digits to four digits.

Existing numbers:

      NPA-NXX-XXXX

Expanded format:

      NPAX-NXX-XXXX

During initial deployment, the fourth digit added to the NPA to form 
the NPAX MUST be selected such that it does not conflict with existing
digit patterns used to identify the first digit of NXX codes. Under
current NANP rules, the first digit of an NXX is restricted to values
2 through 9.

By selecting 0 or 1 for the additional NPA digit, the boundary between
the expanded NPAX and the following NXX remains unambiguous. This 
allowsexisting digit analysis algorithms to distinguish between legacy
10-digit and expanded 11-digit numbers using a simple examination of
the fourth digit, without requiring variable-length parsing or 
timing-based disambiguation.

A single value (0 or 1) SHALL be used consistently across all NPAs 
during the initial deployment phase to ensure uniform behavior across
networks.

Example:

      213-555-1234  (legacy)

      2130-555-1234 (expanded)

Or:

      303-555-1234  (legacy)

      3031-555-1234 (expanded)

This proposal preserves the semantic structure of the number

- NPAX is still geographic.
- NXX is still used as the routing block.
- XXXX is still the subscriber line number.

The widespread adoption of overlay area codes has fundamentally 
altered the NANP environment. A return to strictly geographic, 
non-overlapping area codes is no longer practical. The proposed 
approach assumes the continued existence of overlays and does not 
attempt to reverse this trend.

The designation of 988 as a nationwide service code required the 
elimination of 7-digit dialing in affected areas, accelerating the 
transition to uniform 10-digit dialing across the NANP. As a result, 
this proposal does not impact legacy 7-digit dialing, as that 
capability has already been largely eliminated.

This approach ensures that numbering expansion occurs at the highest
level of the NANP hierarchy, avoiding disruption to lower-level 
components such as routing prefixes and subscriber numbers.

# Routing Considerations

Existing routing systems rely on fixed field positions within the NANP
number. The proposed expansion preserves the relative position of the 
NXX and subscriber line number fields, allowing for minimal 
modification to routing logic.

Systems that perform digit analysis MUST be updated to recognize the 
NPAX format. This includes SS7-based switching systems, SIP routing 
platforms, and number portability databases.

# Transition Strategy

A phased transition is recommended:

## Phase 0: Infrastructure Readiness

Networks and systems are updated to support 11-digit numbers without 
public announcement. Switching systems MUST be updated to recognize and
correctly route NPAX-based numbers during Phase 0.

## Phase 1: Dual-Format Acceptance

Both 10-digit and 11-digit dialing are accepted. 

## Phase 2: User Notification
 
Phase 2 is implemented as two segments. 

### Segment 1

In Segment 1 of Phase 2, LECs, CPs, IXCs, and regulatory authorities 
MUST publicize the implementation of the expansion of the NPA to an 
NPAX, where the area code is expanded to four digits, and the 
telephone number to eleven digits. An important highlight of the 
announcement SHOULD emphasize that there will be no change to the 
subscriber number. It SHOULD also state the date Segment 2 will begin
and the date that phase 3 will begin.

### Segment 2

In Segment 2 of Phase 2, Intercept messages SHALL be imposed on callers
dialing a 10-digit phone number, and such message SHALL inform callers 
dialing telephone numbers using the current 10-digit format of upcoming
requirements. The call SHALL still complete. The message SHOULD state 
the date when dialing the new 11 digit number will be required.

## Phase 3: Mandatory Expansion

11-digit dialing becomes required. Callers dialing the old format 
10-digit number SHALL be presented with an intercept message beginning
with a SIT tone and an announcement that they must dial the new 4-digit
area code. The message MAY announce the additional digit that MUST be 
dialed. The call SHALL NOT complete, and SHALL be treated equivalently 
to dialing an invalid number.

## Phase 4: Full Expansion

The fourth digit of the NPA is opened to all valid values, increasing 
numbering capacity.

# Alternatives Considered

The following alternatives were evaluated:

- Further subdivision of number pooling blocks
- Expansion using only reserved NPA ranges (e.g., N9X)
- Variable-length numbering schemes

These approaches either provide limited long-term benefit or introduce
undesirable complexity.

# Operational Considerations

The proposed expansion is designed to minimize impact on:

- Call routing systems
- Number portability databases
- Inter-carrier signaling

However, significant updates would be required in:

- Customer-facing systems
- Validation logic
- Legacy equipment and embedded systems

# Economic Considerations

Incremental approaches distribute cost over time but increase long-term
complexity.  A planned expansion incurs higher initial cost but may 
reduce cumulative cost and operational burden.

Early planning enables gradual transition and reduces the risk of 
emergency implementation.

# Security Considerations

Changes to numbering formats may impact fraud detection systems, call 
validation mechanisms, and authentication processes. These impacts 
SHOULD be evaluated during implementation planning.

# International Considerations

The proposed 11-digit format remains compatible with the E.164 {{ITU}}
maximum length of 15 digits.  Coordination with international 
carriers and regulatory bodies would be required.

#  IANA Considerations

This document has no IANA actions.

#  Conclusion

Expansion of the NANP to 11 digits represents a viable long-term 
solution to numbering exhaustion.  Early evaluation and planning are 
recommended to enable a controlled and gradual transition.

# Access to this document

In addition to the IETF datatracker, https://datatracker.ietf.org/doc/recent, 
copies of all versions of this document are available from the author's Github 
repository, at https://github.com/electric-socket/11digitdialing.
