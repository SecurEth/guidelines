# Audit Prep Report

## What is a Audit Prep Report?

An Audit Entry Report is the summary report of the package presented to the auditor from the development team.  It is written just before the audit and is designed to assist the auditor with specific information he should know for the audit.

## Why do a Audit Prep Report?

This report summarizes all the important information the auditor needs to start his audit that is not documented elsewhere.

## What is in a Audit Prep Report?

### Audit Goals

These are the specific goals for this particular audit.  It can outline exactly what is to be audited. Any elements that should be ignored can be indicated here.

### Development Environment Information

Location of the GitHub.  Location of the scripts to run the application and the tests.  Normally it would reference the Github README.md. The README must include exactly how to build a local version of your contracts.  


Remember to clean up your GitHub and organize the folders with clear names.  If needed explain the folder structure.

### Tool and Code Review Results

If you have run lint, solium, solcheck or other tools on your code, this section should point to the results and the scripts and options used when the tools were run.  

### Test Results

This section gives the location in the github for the test results.  It should include a README that defines exactly how to run the test suite. This will include the results of code coverage, or lists of dead code.  


Any explanations the developer wishes to give to the auditor \(of tests that do not pass, for example\) should be listed or referenced here.

### Bug Bounty Plan

Bug Bounties are a popular process for improving code after the audit but before full deployment.  Describe and bug bounty plans for your application and when they will take place.

### Deployment Plan

You should allow the auditors to comment on your deployment plan.  It is an area where their experience could add significant value. Do you plan a limited test network release?  Discuss the top level plan. Do you plan a limited main net deployment? The limitations may impact your code. Describe the order you plan to deploy your contracts and the specific options with each deployment.

