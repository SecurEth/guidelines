# Audit Prep Report

## What is an Audit Prep Report?

An Audit Prep Report is the summary report of the package presented to the auditor from the development team.  It is written just before the audit and is designed to assist the auditor with specific information they should know for the audit.

## Why do an Audit Prep Report?

This report summarizes all the important information the auditor needs to start their audit that is not documented elsewhere.

## What inside an Audit Prep Report?

### Audit Goals

These are the specific goals or scope for this particular audit. It can outline exactly what is to be audited. Any elements that should be ignored can be indicated here.  Indicate if the audit result will be public or private to the development team.

You should also include a discussion on the level of risk your application will experience. This is an estimate of the amount and value of any assets your application will contain and the time period it will contain those assets for. This will aid the auditor in understanding your risk level.

Also include any specific security properties which are a priority to verify. For example, with a token sale: “tokens cannot be obtained for less than the stated price.”

### Development Environment Information

This section should note the location of the scripts used to compile the application and run any tests. You must also include all version information of the compiler and any tools used, preferrably in files that can be used to install them directly.

Complete details are important.  In addition to compiler version\(s\), include things like packages, ethereum node details and everything relevant for the auditor to build the package on their own without your help.  You should also include the location of the repository, if it is public. Normally this information would be referenced in the project README.

Remember to clean up your repository and organize the folders with clear names. If needed explain the folder structure.

### Tool and Code Review Results

For the [testing tools](../tools/existing-tools.md) that were run on your code, this section points to the results of those tools, as well as the scripts and options used when the tools were run. You should also provide commentary on your interpretation of these results and a discussion of any false positives you encountered in a [tool report](../tools/tool-reports.md) specific to each tool that was run.

### Test Results

This section gives the location in the repository for your [test results](test-results.md). It should include a README that defines exactly how to run the test suite. This will include the results of [code coverage](), and any explanations that are needed to explain the existence of any dead code. Any explanations the developer wishes to give to the auditor about any of the test failures should be listed or referenced here.

### Bug Bounty

Bug Bounties are a popular process for improving code after the audit but before full deployment.  Describe any bug bounty plans for your application and when they will take place.

### Deployment Plan

You should allow the auditors to comment on your [deployment plan](../network-release/deployment-plan.md). It is an area where their experience could add significant value. Do you plan a limited test network release? Discuss the top level plan. Do you plan a limited main net deployment? The limitations may impact your code. Describe the order you plan to deploy your contracts and the specific options with each deployment.

