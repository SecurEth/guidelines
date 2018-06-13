# Software Requirements

For the purposes of these documents, requirements here refer only to smart contract code.  In fact, requirements can refer to almost anything in a system. However the focus of this document set is a smart contract code exclusively.  


### Why write Requirements?

1. Requirements are human readable.  They described what the code will do in small formal pieces that are in clear language. 
2. Requirements enable traceability.  Traceability is at the core of the whole process. It enables reviews, change management 
3. Requirements are testable.  As requirements are clear, succinct and readable, you can write tests to verify the requirements. If you test the requirements and the code is tested then you have verified that the code matches the requirements.

### What are Requirements?

Requirements are small, clear text that describes what the code should do.

Requirements must be:

* Necessary: cannot be removed without compromising goals
* Quantifiable: able to measure and verify
* Attainable: must be possible to implement
* Atomic: stand by itself and do not affect any other requirement. No overlap or dependency
* Complete: cover all system properties \(?\)

### Writing Requirements

Requirements are based on system description and must satisfy all 5 principles mentioned above. A requirements peer review could be conducted before design and verification begins. Requirements are then “locked down” and given unique IDs. If a requirement is updated it is given a new ID. Since software and tests reference these IDs directly in comments, engineers have to go through and update them in each reference in order to re-establish traceability, forcing them to re-evaluate the applicability of the requirement. One way to do this is to use the first 2 bytes of the sha256 hash for each requirement text.  


### Requirement Reviews

In aerospace, there are three roles in a requirements review. There is the author who wrote the requirements and calls to review. There is the moderator and there is the reviewer\(s\). In a pinch both roles can be done by the same person.  Where personnel are available number of reviewers and their quality must be determined based on the importance of the contract and the experience of the team.  


When the author calls the review he declares a set of requirements that will be reviewed. He should also include any required background information, such as a [system description](https://drive.google.com/open?id=19iwgv3oZeB0FYL5VRZvVq9i_PIffnZc0NGEFDV3w1v4).  


Before the requirements review meeting, the moderator and the reviewer\(s\) review the requirements individually with respect to the system description. They should have the pertinent requirements checklist at hand. They should make notes on the requirements.  


To review meeting the reviewer’s and the moderator go through each observation on the requirements that was found. The author and the team can discuss each observation and determine if it should be noted as an action. The moderator keeps the action list.  


After the meeting the author makes his changes in their reviews in order to clear the actions. The actions are cleared by the moderator. The requirement review is declared closed when all the actions have been closed.

### Example Requirements Checklist

[https://ep.jhu.edu/about-us/news-and-media/writing-good-requirements-checklists](https://ep.jhu.edu/about-us/news-and-media/writing-good-requirements-checklists)

