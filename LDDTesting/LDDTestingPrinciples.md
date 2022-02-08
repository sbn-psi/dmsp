# LDD Testing Principles

## Why Tests?

* Passing tests provide examples of how the dictionary is used
  * This is not a substitute for documentation, but can supplement it
* Ensure that every class definition works as intended
* Ensures that schematron tests are running
  * Ensures that your schematron rules are correct
* Prevent regressions
  * Regressions are unintended side-effects created by making changes
* Warns if changes are not backwards-compatible

## How do tests work

* Upon a push to the repository, GitHub will:
  * Generate the LDDs
  * Run validate on every label with the generated LDD
  * Interpret the results
  * Mark the branch as passing/failing based on the results of the test

## Demonstration - Pushing a dictionary to GitHub

* Show tests in progress
* Show test results

## What types of tests are there?

* Valid label tests will pass if the validator passes
* Invalid label tests will pass if the validator fails

## Valid Label (passing) tests

* These are meant to test situtations where the label should work
* This can contain a variety of different labels that exercise each aspect of the dictionary

## Invalid Label tests

* These are meant to illustrate labels that are incorrect
* Additionally, they will detect if schematron rules are not running

## How do you write tests?

* Create a label
  * This could involve creating a completely synthetic label, or using an existing label
  * The simpler the part that is not under test is, the better.
* If this is an invalid label test, introduce errors
* Mark the label as a valid label test or an invalid label test
  * Add either `_VALID` or `_INVALID` to the end of the filename
* Commit the label

## Demonstration - Display Dictionary Tests

## Keeping labels uniform

* Unnecessary variations in the label will make it more difficult to track down errors.
* Sometimes variations are necessary when a discipline arrea can apply to different data types

## Monolithic tests vs granular tests

* EN's test processes are currently better suited for granular tests
* Monolithic tests are currently easier to generate and maintain

## Keeping tests granular

* Each label is invalid in only one way
* Combining multiple errors in a single file will mask errors that don't occur, since the testing framework is binary.

## Drawbacks to granular tests

* Granular tests will increase the number of labels that the LDD is tested against
* Each of these labels will need to be maintained individually

## Demonstration - Survey Dictionary Tests

## Generating Test Labels

* Hand writing labels
* Injecting discipline area fragments into label templates
* Mutating existing labels
    * Keep a mapping of xpaths and operations to perform on a location

## Monolithic tests

* Multiple tests can be packed into a single label
* Document each point where the test is expected to fail
* Examine the output of the test run to determine if there are any missed failures

## Demonstration - Spectral Dictionary Tests

## Interpreting the test output for monolithic tests

* Since monolithic tests have only a pass/fail result, and there are multiple expected failures, it's possible to miss failures
* This can be mitigated by expecting a certain number of failures, or checking for specific failure messages
    * This would require updates to the test runner

## How many tests?

* You want to have enough to thoroughly test your dictionary.
  * Typically, this means that every class should be used at least once
  * Every schematron rule should be used at least once, as well.
* Too many tests can cause problems
  * The biggest problem with too many tests is that they need to be maintained
  * Maintenance can be necessary when either your dictionary changes, or when the dependencies change (IM changes, upstream dictionaries, etc)
  * A test should have its own job -- it shouldn't just functionally duplicate another test

## Exercise every class

* At least one passing test should use each class
* Write as many test files as necessary to achieve this.

## Exercise every schematron rule

* At least one failing test should fail a schematron rule.
* This is especially important, since schematron rules can be prevented from triggering if incorrectly written.

## Demonstration - Nucspec Dictionary Tests

## Document the tests

* Documentation can be as simple as a file that lists the test name and what it is testing.
* This will remind you how each test is expected to fail, or what each test is intended to exercise.
* If writing a monolithic test, this can be further developed into the expected output for comparison in a future version of the EN testing tool.

## Organize the tests

At minimum, tests should be organized into valid and invalid label tests. Although this is embedded in the name, sorting them will make it easier to find the test that you need,
especially as the number of tests grows.




