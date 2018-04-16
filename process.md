---
layout: page
---

# Process Overview
When developing a new project that will contain a complex set of smart contracts,
it is import to follow a rigid process that creates a traceability between
your architectural requirements and your software implementation and verification.
This traceability ensures that no critical issues develop in your overall design.

A very rigorous approach to this would be to formalize documentation capturing
each step in the design process:
1. Planning
2. Development
3. Verification
4. Quality Assurance
5. Certification
6. Operational Security

## Planning
An understanding of the overall system goals should be formalized through consensus
with all major stakeholders. Any updates to these goals automatically trigger a complete
review of all derived requirements, which further cascades to a review of all affected
implementations, verifications, and certifications. A Preliminary Design Review
can often aid in coming to consensus on the architectural decisions made before
development begins.

## Development
The overall system goals should be derived into a series of requirements organized
by the smart contract implementation that will implement it. These requirements should
be derived further by smart contract methods. For each method, the access control list (ACL)
and input assertions shall be defined and mentioned as a requirements for that method, as
well as the interface that method provides.

It is recommended to use the docstring of your relevant language to track these requirements.
You can parallelize the verification effort at this point (assuming the requirements are locked down)
so a set of test cases can be developed prior to the implementation phase (Test-Driven Development).

A Peer Review of these requirements at this point in the process can catch errors in the derivation
process before implementation begins.

After the derivation process is complete, the series of requirements associated with each smart contract
method will be implemented, keeping the security best practices in mind while implementing them.
*The implementation is determined to be complete if it implements all requirements and passes all
verification items associated with those requirements.*

When the development phase is complete, a Peer Review process is usually required to ensure there were
no mistakes in the implementation of the code that are easily caught.

## Verification
The verification process is a combination of different levels of concerns. During the testing
process, inconsistencies with the derived requirements may be found. It is important to formalize
an impact analysis ensuring modifications to the derived requirements get appropiately tracked by all.

Functional verification maps the derived requirements (which lead to the implementation)
to a series of test cases that tests the proper implementation of that requirement.
It is important to test both the positive and negative logical states of these requirements,
in order to arrive precisely at the logical states described by those requirements.

Coverage testing ensures that the underlying implementation contains no problematic code that
could lead to troublesome states, and that no code is unreachable per the requirements described
(reducing your attack surface and optimizing your gas usage). The Design Assurance Level leads to
the level of coverage testing (statement, conditional, MC/DC) required.

Integration testing proves that the developed smart contract system interacts properly with
the dapp as a whole. This is typically where issues with units and required interfaces are found.
This process should link to the interface requirements so that inconsistencies in the interface
(both missing and unecessary interfaces) are caught and appropiately handled through impact analysis.

When this process is complete, a Peer Review is often necessary to determine that no tests are missing
through traceability analysis, and that all logical conditions are caught and tested.

*NOTE*: It is *very* important that the verification steps taken for a specific development item are
not performed by the same person who design that development item, this ensures a minimal level of
understanding and clarity between multiple parties such that results are more robust overall.

## Quality Assurance
It is important to have an internal process where independant parties monitor the proper
use of design standards (both internal and external) to ensure all code remains consistent and
readable. This is important through the entire process, but especially important at the end to
ensure only quality code makes it to the certification process (reducing impacts from certification).

## Certification
A certification process should be defined prior to release of the code that takes into account
external security audits, and acceptance testing of the dapp the smart contracts are being used for.
These two items can often happen in parallel, as any discovery at this stage in the process will
trigger a comprehensive impact analysis to determine the overall effect on the system.
This process should include methods of defining severity to the issues discovered, and that
impact analysis will lead to a determination of whether to go forward with release.

## Operational Security
After the smart contract system is certified and ready for release, a plan should be developed that
comprehensively and clearly describes the process to monitor and/or react to scenarios as they occur.
It is often useful to ensure that these mechanisms are included into the Development and Verification
processes correct performing of the tooling. Resources should be allocated
for this process that covers the necessary operational periods it will be in effect.
This process should also include a means for alerting the stakeholders, maintaining an orderly and clear
response when issue arise.
