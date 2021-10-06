# Review Process

Some of the steps that can be taken to improve the review process.

## Automation

### Code Linters 
Code linters should remove any styling issue in a review. 
There should be a automated task that runs against any CR.
If a linter was to fail no forward review should be done till the linting issue is fixed.
For project where the linters have not being set up as an automated task there should be a manual way to run the linters using a `make <target>` command.

### Unit Tests
Unit tests shoule be automated and run as part of the CR.
As a reviewer it's ok to say you wont review the CR till all the unit tests are passing or a very strong reason is give for the test to be failing.
Any reason for allowing a failing test should be documented in the CR.
If the unit test do not run as part of the CR pipeline this used be manually triggered by the reviewer.

### E2E Tests
Unlike the unit tests these might not run as part of the automation all the time.
As the E2E test could take hours to complete, they may be marked as opinital.
In the CR notes it should state what E2E test covers the changes that are being made.
If the CR does update any E2E test, all the E2e test should be ran.
Hopefully there is a command that can ran agasint the CR to trigger the running of the E2E test.
