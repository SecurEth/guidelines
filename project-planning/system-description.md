# System Description

## System Description Document {#docs-internal-guid-2dd24c90-fab9-37aa-c3bd-ca661d436fac}

The System Description Document \(SDD\) is a top level informal document that describes what the system will do. It should describe the “System” or “Product” from a users’ perspective. Think of it as the “spirit of the application”, and it could be as short as a single paragraph.

## Why do a System Description Document?

This is the first document that any auditor or contractor would read. From it they should understand what the system does. Before an auditor looks at your smart contracts, this document will give them perspective.

It can include the web aspects in addition to the smart contracts. It should include the business aspects of the project and a description of any tokens, their uses and life cycle. It can include a list of the Goals for the smart contracts.

It can be an excerpt of the white paper but should be an independent document. This is the first document any outside auditor will read because it gives them context.

### Who reads the System Description Document?

Any third party that will be involved in the smart contracts of should read the SDD first. This will include auditors, but could also include new contractors.

## What is Included in the SDD?

### Informal Document

This is an informal document with respect to the guidelines. There are no requirements as to the format. The document does not formally trace to any requirements or tests. This means the document can be in any format. It should be a separate document from the white paper and be updated such that it is current with the smart contract application.

### Description from the Users Point of View

The SDD should describe what the application does from the user’s point of view, what the user does and why. Describe the users business incentives for using the application. Ideally it would have a full users instruction manual but that is not required.

### Tokens

This is the only document where you can describe the uses and lifecycle of a token from a business perspective.It is important for an auditor to know which tokens will hold a high value.

### Diagrams

This is a good place to include any relevant flow diagrams explaining your system or aspects of it. Many other documents of this process \(requirements, code, tests, etc\) often are text files that cannot carry documents, so put the diagrams in this document and reference them elsewhere.

### Web Aspect of the Application

While this section can simply describe a web application, consider mentioning other aspects important to the smart contract. Is there bounds checking done on the variables passed to this smart contract. How many instances can be called in parallel? Are there any aspects in the design of the web application that will affect the smart contract? Any information that would give additional relevant information to the auditor should be included.

### Hardware

If your Application uses hardware such as an Internet of Things device, this is the place to describe it. If the device will interact with the Blockchain then its code will have its own set of requirements.

## Examples

Example 1 - Tiny DNS

Example 2 - CryptoKitties

## Template

What is the top level of your System/Application/Product?

What does the User see and do with the Application.

Describe any tokens involved in the system, including value and

