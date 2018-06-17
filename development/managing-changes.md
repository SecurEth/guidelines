# Managing Changes

Code changes, requirements change. This is impossible to stop. Having requirements traceable to code and test helps managing the impact of changes.

### Change in Requirements

Ideally, requirements are carefully thought through and reviewed beforehand and shouldn't change by them self, but when that happens changes need to be traced to all the affected code and tests.

Checklist:

1. Add or modify a requirement
2. Change any impacted requirements
3. Update [Traceability](traceability.md) markers
4. Look for changes in code and tests with updated markers
5. Validate if any other requirements need changes
6. Review tests of impacted requirements
7. Run test suite and validate all pass
8. Run coverage tests again, ensure new code still covered.
9. Note all the changed requirements and review them again in a batch

### New Feature

So you need to add a new feature or make a major change to existing requirements, in this case, the first changes are made in the requirements. Add the new requirements and change any impacted requirements. Next update the code. If you change code that traced to unchanged requirements, note the requirement. Test the revised code. Validate the traceability for all changed contracts. Add tests for the new requirement.

Checklist:

1. Add new Requirements
2. Change any impacted requirements
3. Update [Traceability](traceability.md) markers
4. Change code and test
5. Validate if any other requirements need changes
6. Review tests of impacted requirements
7. Run test suite and validate all pass
8. Run coverage tests again, ensure new code still covered.
9. Note all the changed requirements and review them again in a batch

### New Bugfix

After you have changed and tested your code, you consider each requirement that traced to the impacted code. Do you need to change the requirement? Adjust as required. If you change a requirement, you must review the tests and adjust as required. If you feel a need to change the test in order to cover the new code, but you have not changed the requirement, check carefully again. This is certainly possible \(if the new code covers a corner case that the requirement does not and should not cover\) but should not be common.

Checklist:

1. Change code and test
2. Validate if requirement need changes
3. Update [Traceability](traceability.md) markers
4. Review tests and code of impacted requirements
5. Run test suite and validate all pass
6. Run coverage tests again, ensure new code still covered.
7. Note all the changed requirements and review them again at a later date

### New Hotfix

Minimum possible change to stop the problem from occurring. Doing that allows you to have more time to prepare an appropriate bugfix. This should be avoided in favour of other mechanisms, like emergency stop.

