# Software Requirements

Requirements are small, clear text that describes what the code should do. Requirements here refer only to smart contract code.

## Why write Requirements?

1. Requirements are human readable. They described what the code will do in small formal pieces that are in clear language.
2. Requirements enable traceability. Traceability is at the core of the whole process. It enables reviews, change management.
3. Requirements are testable.  As requirements are clear, succinct and readable, you can write tests to verify the requirements. If you test the requirements and the code is tested then you have verified that the code matches the requirements.

## Writing Requirements

Requirements must be:

* Necessary: cannot remove without compromising goals
* Quantifiable: able to measure and verify
* Attainable: possible to implement
* Atomic: stand by them-self and do not affect any other requirement
* Complete: cover all system properties

## Requirement Reviews

A requirements peer review could be conducted before development and verification begins.

In aerospace, there are three roles in a requirements review. There is the author who wrote the requirements and calls to review. There is the moderator and there is the reviewer\(s\). In a pinch moderator and reviewer roles can be done by the same person. Where personnel are available number of reviewers and their quality must be determined based on the importance of the contract and the experience of the team.

When the author calls the review he declares a set of requirements that will be reviewed. He should also include any required background information, such as a [system description](https://drive.google.com/open?id=19iwgv3oZeB0FYL5VRZvVq9i_PIffnZc0NGEFDV3w1v4).

Before the requirements review meeting, the moderator and the reviewer\(s\) review the requirements individually with respect to the system description. They should have the pertinent requirements checklist at hand. They should make notes on the requirements.

To review meeting the reviewer’s and the moderator go through each observation on the requirements that was found. The author and the team can discuss each observation and determine if it should be noted as an action. The moderator keeps the action list.

After the meeting the author makes his changes in their reviews in order to clear the actions. The actions are cleared by the moderator. The requirement review is declared closed when all the actions have been closed.

## **Requirement Lock Down**

After review is complete, requirements must be “locked down” and given unique IDs. If a requirement is updated it is given a new ID. Since software and tests reference these IDs directly in comments, engineers have to go through and update them in each reference in order to re-establish traceability, forcing them to re-evaluate the applicability of the requirement.

One way to do this is to use the first 2 bytes of the sha256 hash for each requirement text.

## Examples

### CryptoZombies Lesson 5

Check [here ](../../examples.md)for a description of the examples used below.

Here are the five contracts in the original CryptoZombie release with requirements included. The exact format of requirements has not been finalized so consider the example here and in DNS \(which is different\) as indicative.

[ZombieFactory.sol](https://github.com/SecurEth/CryptoZombiesT2/blob/master/Lesson5/contracts/ZombieFactory.sol)

[ZombieFeeding.sol](https://github.com/SecurEth/CryptoZombiesT2/blob/master/Lesson5/contracts/ZombieFeeding.sol)

[ZombieHelper.sol](https://github.com/SecurEth/CryptoZombiesT2/blob/master/Lesson5/contracts/ZombieHelper.sol)

[ZombieAttack.sol](https://github.com/SecurEth/CryptoZombiesT2/blob/master/Lesson5/contracts/ZombieAttack.sol)

[ZombieOwnership.sol](https://github.com/SecurEth/CryptoZombiesT2/blob/master/Lesson5/contracts/ZombieOwnership.sol)

## Example Requirements Checklist

{% embed url="https://ep.jhu.edu/about-us/news-and-media/writing-good-requirements-checklists" caption="" %}

Got a comment?  Check out our [Gitter Channel](https://gitter.im/SecurEth_Guidelines/community#)!

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/)

