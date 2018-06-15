# Managing Changes

Code changes, requirements change. This is impossible to stop. Having requirements traceable to code and test helps managing the impact of changes.

In this case, we are talking about changes in code and/or requirements after the developer has started using our process but before deployment. Code changes after deployment will be discussed in a subsequent article.

### Code Changes

So consider you have to make a small change in your code for a good reason.  After you have changed and tested your code, you consider each requirement that traced to the impacted code.  Do you need to change the requirement? Adjust as required. If you change a requirement, you must review the tests and adjust as required.  If you feel a need to change the test in order to cover the new code, but you have not changed the requirement, check carefully again. This is certainly possible \(if the new code covers a corner case that the requirement does not and should not cover\) but should not be common.

Checklist:

1. Change code and test
2. Validate if requirement need changes
3. Review tests of impacted requirements
4. Run test suite and validate all pass
5. Run coverage tests again, ensure new code still covered.
6. Note all the changed requirements and review them again at a later date

### New Features

So you need to add a new feature or make a major change to existing requirements, in this case, the first changes are made in the requirements.  Add the new requirements and change any impacted requirements. Next update the code. If you change code that traced to unchanged requirements, note the requirement. Test the revised code. Validate the traceability for all changed contracts. Add tests for the new requirement.

Checklist:

1. Add new Requirements
2. Change any impacted requirements
3. Change code and test
4. Validate if any other requirements need changes
5. Review tests of impacted requirements
6. Run test suite and validate all pass
7. Run coverage tests again, ensure new code still covered.
8. Note all the changed requirements and review them again in a batch

