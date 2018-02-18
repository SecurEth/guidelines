# Creating Toolsets
As processes become well-defined, tools can be created to automate, augment, or otherwise aide
developers in generating, analyzing, deploying, simulating, and testing smart contract code.
Depending on the usecase of the toolset, it is necessary to determine the severity of a mistake in
that tool, and how it can potentially effect the security of the smart contract system it is used for.

For example, a verification tool may be developed that automates the generation of some series of common test cases.
The impact of this is minor because although it affects the very critical verification process, the test cases
still require traceability analysis to determine if the smart contract system is throughly testing all logical states.
In contrast, a verification tool that automates the verification of those test cases has a higher impact, because it
can incorrectly report a false negative which would lead to an incorrect determination of the verification state
of the system. This impact analysis needs to be formalized for a toolset prior to use on productionized code,
which includes some assurance that the underlying functionality is also properly verified enough to trust.

# Toolset Qualification
A set of requirements should be developed, derieved from a set of goals underpinning the tool,
and proper traceability of those requirements to relevant test cases must be shown. Some level of formal
analysis should be performed to ensure that these requirements properly implement the goals of the tool,
and that the test cases test all relevant states the tool operates in (as well as proper function).
