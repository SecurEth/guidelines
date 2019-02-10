# Test Results

You will most likely have multiple types of [testing](../development/testing.md) that accompanies your code when you seek to get an audit. For example, a suite of functional test cases that verify your requirements, as well as additional cases meant to satisfy coverage requirements and potentially some tools that you ran for additional verification purposes on your code. You should supply these cases with their run results to the auditor. The auditor will verify they achieve the same results as you gave them, ensuring that all results are fully reproducible with the given code and environment setup specified in your [Audit Prep Report](audit-prep-report.md).

When they have verified the reproducibility of your results, they will need to validate the assumptions in your explanations for any unresolved issues you may have encountered. You can assist them in this process by providing commented test results for them to look at. Functional test results should have a 100% passing rate, but if that is not true for whatever reason, you should provide a list of which cases failed and an analysis of why this is acceptable. Coverage testing can very often be under 100%, especially when more advanced levels of coverage are sought, so you should document that alongside your reasoning of why coverage not achieved for each specific component that was missed.

## Tools

You might also run additional tools on your code. Each tool should have a separate [Tool Report](../tools/tool-reports.md) about that tool and how it was used in your codebase. Include this for every tool that verifies or validates any portion of your requirements and/or codebase. You can find a list of them [here](../tools/existing-tools.md).

##  

Got a comment?  Check out our [Gitter Channel](https://gitter.im/SecurEth_Guidelines/community#)!

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/)

