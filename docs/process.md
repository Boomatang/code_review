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

## Manual Review

### Understand The Change
Every change request should have a description of what the request is trying to achive.
This may require reading the linked jiras and issue to get a full picture of what is trying to be done.
As the reviewer knowing the problem the author is trying to solve will help spot misstakes that can be over looked if reviewing the CR withou the context of what it is trying to solve.

### Verifaction Steps
Does the change requst have verifacation steps for the reviewer to follow.
Verifaction steps should give a clear picture of what is expected to be seen when running the steps.
If the steps are vague or not fully understood ask the author to explain the steps or better still get them on a call while doing the verifaction steps.

### Ask Questions
While an author is working on a change request they can become narrowlly focused.
As a review you should look at the wider picture and think of what the changes could mean for the rest of the system.
If there is side affect which you feel may come for the change, ask questions for the author to answer.
There is two reasons for asking questions. 

1. As the review you may have found an issue that was over looked by the author.
This now could be address in this CR and not become a bug to be address later.
2. If author explains why their way is correct as a review you have learned something new.
Learning these new things will increase the quilty of the code overall as reviewers will also be author at times.

### What To Look For
When doing a review there are many things to look out for. 
Below are some areas that a reviewer should focus on as well as the code changes.
As an author it is easy to forget about these areas as they might not be strictly required to get a task completed.
Being the reviewer give you responabiltly of ensure the whole system is being mainatined. 

#### User Facing Compnets
What is a user facing compent?
This will depend on two things, what is the project and who are the user.
An user might be the end customer but also users can be the other developers on the team.

For example if there was a script created for use in the project to help with some complex development task.
Is that script documented with examples on how to use it.
The script may seem simple at the time of first creation but over times these things thend to get more complex.
If the documentation is missing for the start it will be much harder to get an author to add new documentation over updating existing documentation.

#### Tests
Test are importent for future authors and the current author might not see the value in them in the here and now.
As a reviewer this is possible the most importent thing to ensure is correct.

There are two main types of test that can be created and both test different things.

1. Unit tests. 
Test small bodies of work normally a single function and only one use case of that function.
Unit tests should not require the product to be installed.
The test can be parmatizes to run a number of different inputs.
It should run indpent of other tests.
2. Functionaly tests. 
These are much large tests and are some times referred to as end to end (e2e) test. 
These tests cover functions with in the product.
For example if the product was a note taking app a functional test maybe to check if a user can login and create a new note.
The different componets of the functional test (login, not creation) indevily should be covered by unit tests.
But the functional test will test the componets as a whole system, like a user will use it.

During a change request an author might try leaving out the tests.
The reviewer is responable to ask why these are being left out. 
It could be a case where the work is already covered by tests.
In these cases the author of the change request should document what existign tests cover the changes.

Change request really should not be approved with out tests.
These natualy hard for authors to do and will take time for them to learn the habit.

#### Documentation 
Documentation will fall under three main cataguires.

1. User documentation. 
This is documentation that will be used by the customer in the use of the product.
2. Support documentation. 
The target user would SRE teams which support the products.
3. Development documentation.
Documentation used in the development of the product and the onborading of new members to the development team.

Good documentation is hard to create and most change request may not need updating of documention.
It is also possible the documentation may exist in a diferent repo to the change request and/or be maintained by a different team.
On a Change request a good question to ask would be, What documentation covers these changes?

User documentation is normal handle by a docs team. 
That does not mean it should be igroned in the review process.
It maybe possible for the author to create notes that the docs team can use to create better guides.
Asking the question if the change request has affects on user documentation maybe useful.
If the change request does affect user documentation there should be some indecatior on the ticket for that work.

Support documentation should follow the "Does this make sense at 3am" rule.
These means if a SRE member is paged at 3am to fix a customer issue, will they understand the steps in the documentation.
It is normal to require approval from the SRE teams that will use the documentation. 

Development documentation will be harder to get an author to create.
The authors are living in the development and won't see the need for the documentation.
This documentation becomes usefull in the future for tasks that are not carried out often and for new members joining the team.
During the development of a product there will be lots of assumention made.
For example everyone on the development team knows how to uninstall the product.
A new person coming to a team might not know this and there may even be multiply ways to uninstall the product depending on how it was installed.

It will be much easier to get an author to add documentation for a new feature at the time of creation over getting the author create new documentation for existing features.
If the documentation is existing it will be easier to get it updated.

Over all documentation will improve the product in the long run.
Documentation does not need to be a novle, a few lines maybe enough to explain to future you what is going on.
As a reviewer you should be thinking about the documetation and who would be affected by the lacking of it.
Asking the author what docmentation would be affected by these changes is a good starting point. 


