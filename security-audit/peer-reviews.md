# Peer Reviews

## What is a Peer Review?

A Peer Review is where you get a group of people and have them look over what you built to make sure it makes sense. You could get any group of people to do this review for you, the only requirement is that they have a strong background in the tools you employed to build your project. These people can be coworkers, peers, even people you don’t know. You are getting a fresh perspective, someone who doesn’t make the same decisions as you, and having them arrive at the same logical conclusions you did without skepticism.

## Why do a Peer Review?

Doing a peer review is not necessary, but secondary opinions are often very helpful in making your project more robust. It can also be done in preparation for a formal audit, to make sure you are giving the best version of your project to these groups. You can think of a security audit as basically a more advanced and formal peer review. The auditors you should choose should be experts in the languages and toolsets you employ. They will bring their considerable expertise, as well as their tools and analysis techniques to do one final check on your software, but they only have a short amount of time to do it. The more time they spend figuring out very simple issues with your code, the less they spend deeply reasoning about it to discover truly insidious bugs that could affect your project deeply.

## How do I do a Peer Review?

There are many things you can do in a peer review. The point is to bring different perspectives on your code to ensure robust design

### Requirements Traceability Analysis

Assuming the goals match the requirements derived from your system description, you can analyze completeness of your implementation using your requirements [traceability](../development/traceability.md) matrix. This allows you to determine not only is there a 1-to-1 mapping of requirements to code, but that the code completely implements the requirements, and that no additional features have been added without requirements. This means your implementation of the requirements is both sufficient and complete.

### Test Case Traceability Analysis

Obviously you need to finish your test cases first, but validating all test cases match to requirements \(which all map to implementation code\) ensures a solid link between what you attempted to build and what you verified that you built. This is an opportunity to look at your tests as well and ensure that they implement the full set of logical permutations each requirement specifies, in both positive and negative directions.

### Static Analysis and Formal Verification Tools

Automated testing tools are another great way to discover potential vulnerabilities in your code. These tools play a large role in the Auditor’s toolkit, so you can save them time and yourself some money if you run one or two of them prior to an Audit. Analyzing the output of these tools can be tricky as they rely on advanced concepts like symbolic execution and may not be easy to understand, but doing your best at this stage and explaining what may not be a real problem \(labeling false positives in your code\) can only help make your code stronger and is worth the effort during a Peer Review.

### Coding Style Compliance

Adhering to a coding style guide is a great way to ensure consistency and make your auditor’s job easier. We’re not going to tell you what style guide to use, but more consistency in your code is always a good thing and makes it easier to spot inconsistencies that could be bugs. Also, you can use documentation in your code \(through natspec-style comments\) to help generate additional documentation that allows you to verify things like requirements and test traceability.

## Peer Review Template

## Example Peer Review

