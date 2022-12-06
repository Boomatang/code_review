# Introduction

This content aim to provide a set of best practices for reviewer during a code review.

## What is a code review

A code review is the process of reviewing a change request normally liked to a Jira which has being requested by an author.
The process is about improving and add new feature to a code base over time.
Reviewers would be responsible for maintaining a projects state. 

## What are the stages of a code review
There are different stage of a review.
Most stages will repeat depending on how large and complex the changes being made are.

0. Authors Initial Change Request.
1. Reviewers Initial Review.
2. Authors Updating Of Change Request.
3. Reviewers Re-Reviewing Of Change Request.
4. Change Request Gets LGTM.
5. Author Gets Approver Label On Change Request.

**Authors Initial Change Request.**<br/>
This is the time where an author will spend creating the change request to suit the requirements stated in the related ticket.
The author will create the change request against the appropriate repo.
Adding description information such as, links to related tickets, verification steps, etc.
At this stage the author believes the changes are correct and the change request is created with that understanding.

**Reviewers Initial Review.**<br/>
This is the first stage that the reviewer will see the change request.
The reviewer should review the description and related tickets first.
An understanding of what the change request is try to achieve is required to understand the different parts of the change request.
During the review try use the platform tools to help with the review.
Try not to create single comments for every change but instead add them to a review.
This will help later.
Ask questions if there is parts of the change request you do not full understand.

**Authors Updating Of Change Request.**<br/> (not happy about this section)
After the initial review the author will be required to address any comment that were made during the review.
This does not mean that the author has to implement the changes but it should open a discussion on the comments.
All comments should be address in some fashion by the author.

**Reviewers Re-Reviewing Of Change Request.**<br/>
Once there has be a discussion the changes required the author will push the relevant changes.
When doing the follow up review first check to see if any comments have being left unaddressed.
These really should be address before doing the next round of review as they may require change that would need a follow up review.

Look at the new changes in the change request.
The can be done by looking at the single comments on the change request.
This is being to done for two main reasons.

1. Has the author added changes to address comments.
It is always possible the author would say they will change something but forget to do the changes.
If this does happen the reviewer should let the author know as soon as possible.
2. Has there being new changes being add that is not related to any comments that were made during the previous review.
There can be many reason why this might happen.
One such reason is during the authors addressing of comments the author may notice an issue the reviewer may have missed.
These changes should relate to the ask of the tickets.

After checking comments have being addressed and seeing what change have been added to the change request, a follow review should be carried out.
It is possible that a small change could have introduced a new bug in the change request so it is important to review the whole change request and rerun the verification steps.

It is okay to create a new review on the change request asking for more changes.
This is a cycle and every time the work should get better.
Importantly as a reviewer remember that perfection is the enemy of done.
At some point work has to be done and if it seems like there is a lot of back and front happening it may be a good idea to get someone else in on the review.

**Change Request Gets LGTM.**<br/>
After the review has gone through a hand full of cycles and all comments are addressed in some form.
Once happy the LGTM label should be added to the change request.
This lets the author know that the changes have been accept and are now ready to get an approve to approve.
At this stage the reviewers work is done and it is up to the author get the change merged.

**Author Gets Approver Label On Change Request.**<br/>
Once the change request has a LGTM it is up to the author to get an approver to approve the change.
Depending on the repo this may be done in a number of ways. 
Some repos will have commands the approves run to get pipeline to merge the change.
Others will require the approver to do some manual steps.

## Terminology
 - **C**hange **R**equest (**CR**) - As different platforms use different terms for a change request i.e. GitHub uses pull request (PR) and GitLab uses merge request (MR), This guide will use the change request style.
 - Author or CR Author - refers to the person that is requesting a change to a repo or project. 
 - Reviewer - Refers to the person that is doing the review for a CR.
 - Approver - Refers to a person who has the final say if a CR is accepted into a project.
 - **L**ooks **G**ood **T**o **M**e (**LGTM**) - This notes that a reviewer is happy with a change. Some projects will require this being added as a label. Other project will have this added a comment in the review.

