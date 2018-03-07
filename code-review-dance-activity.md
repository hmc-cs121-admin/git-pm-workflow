# GitHub Workflow an Project Management Reference


## Prerequisites

- You have a GitHub account and you know your username and password. If you
  don't have one, create one now.
- You have Git 2+ installed and configured.
- You know how to open a terminal and generally work from the command-line.
- You know enough of vi or vim to edit, move around in, save, and quit files.
- You have completed the other Github tutorial and have a basic understanding of it's features


## Form teams

Form a 2-person team. If you are the odd-person-out, join a team of 2.

Assign the following roles to the members of your team. If you are in a
team of 2, assign the recorder and navigator roles to the same person.

Roles:

-   Developer A: Sets up repoisotry with required reviews and reviews Developer B's pull request (PR)

-   Developer B: Creates an erroneous addition and attempts to create a pull request

3rd person role (if you have a 3-person team):
-   Act as a separate reviewer of Developer B's PR.


-------------

## Pracitce the Code Review Dance

If not already the case, make sure the repository is set up and code reviews are 
required for pull requests of important branches (Step 1 below).
This helps prevent errorneous code (2) from slipping into your code base from a Pull Request (3).
Performing these code reviews (4) fosters learning from your development team and sharing your own expertise.
Allowing the original coder to make changes shares your insight and maintains code ownership (5).
Multiple rounds allows for rigourous checks and understanding (6).
Mandating who merges each PR in the end maintains a good Git Blame (7).

*On GitHub*
### (1) Set up required code reviews (if necessary) (Developer A)

  Begin by creating a repository on Github. Be sure to go to the repository's "Settings" tab (found on the rightmost tab of the repo). From the left sidebar select "Collaborators and teams". Now under "Collaborators" add your team member, Developer B. Make sure they join your repository now. While still in "Settings, from the left sidebar select "Branches". Under the "Protected Branches" select the master branch to protect it from deletion and pushes by making sure "Protect this branch" is checked. Require changes to master be made through pull-requests by ensuring that "Require pull request reviews before merging" is checked. Now check the "Dismiss stale pull request approvals when new commits are pushed". This option is very important, as it makes sure that any changes to a PR submitted after approval get their own round of code review. Without this option, once you approved a branch anything could be merged to master. Finally make sure that "Require review from Code Owners" is checked. In practice this final option will mean that only the PM, the repo owner, can approve PRs (for the sake of this exercise, this is Developer A).

*On Command Line*
### (2) Create an erroneous file (Developer B)
    
  Create a new branch to work on, and in this branch create a file called "problems.rb".
  You will create a quick function that takes in a number *n* and prints "Hi *4n* times.
  Create the funtion as follows (including errors):
  * Start by defining a function that takes in one integer n.
  * Give the function a confusing, complicated, or long name (ex. `printHi3TimesNTimes`).
  * At the top of the function, put a comment saying `# TODO: Fix this whole function`
    * A TODO comment like this, similar to test statements, should never make it onto your master branch and should be removed before submitting a pull request
  * Create a for loop that loops from 0 to n times
  * Create an inner for loop that loops from 0 to 3 times
  * Finally, inside the inner for loop print “Hi” with `puts “Hi”`

*Locally and on Github*
### (3) Submit a PR for the file (Developer B)

  Save the file and `git add` your changes. `git commit` them and be sure 
  to use a good commit message with `-m`. Push your changes and create 
  a pull request comparing your branch to master. This is done by going to 
  the "Pull Requests" tab on Github and pressing the `New Pull Request` 
  button in the upper right. Set the base branch to Master and the compare 
  branch to your new branch. Give your pull request a good name, and to 
  notify Developer A that you’ve made a PR by including 
  `@[Developer A’s github handle]` in the description.
    
*On Github*
### (4) Review the new PR (Developer A)

  Navigate to the "Pull Requests" tab on Github and open the new PR. Click on the “Files Changed” tab to see what the pull request covers.
  First how to leave comments. Comments can be left on a PR in two ways: a single comment and starting a review. Leaving a single comment is acceptable for quick and short comments or questions. The developer that made the PR is notified after every comment Some people will only use single comments for everything, however, in most code-review cases, starting a review is better. Starting a review allows you to go through all of the code in one sweep and will not notify other developers of your comments until you have submitted the review. It also give you a way to be clear that you are not approving the PR until changes have been made. NOTE: You must finish a review or your comments will be invisible to other developers. Here we will start a review.
  
  On the first line that you wish to leave a comment, hover over the line and press the plus button that appears on the left of the line. Type out your comment and press "Start a Review". Continue leaving comments on other lines, pressing "Add review comment" when finished with each comment. When you are finished you will click the "Finish your review" button.
  
  Now comment on the problems in the code, including:
  * Suggest a better name for the function
  * Recommend storing “Hi” in a variable to avoid magic values
  * Suggest combining the two nested loops into one loop for code clarity
  * Point out the “TODO” comment that should be removed
  * Make any other comments you think are necessary
  
  Now press the "Finish your review" button to have the "Review Summary" box pop-up. Feel free to leave a summary of your changes. Since there are still changes to be made, select the "Request Changes" radio button and press "Submit review"

*On Github and locally*
#### (5) Respond to comments (Developer B)

  Check your "Pull Requests" tab on Github and read over the comments Developer A has 
  provided. Fix the issues they pointed out and answer any questions they left.
  `git add`, commit (with a message) and push your changes and verify that your 
  changes have been updated on the PR on Github.

*On Github*
### (6) Look to approve the pull request (Developer A)

  Refresh the pull request and check over your comments (in most cases if you commented on the correct line, your comment should be hidden if it has been addressed).
  Quickly read over the changed code again, if you have any comments, add them and have Developer B address them.
 If you have no additional comments, in the "Files changed" tab on Github, click on the "Review changes" button in the upper-right corner, select the "Approve" radiobutton, and click "Submit review".
 
  **NOTE: You’ve approved the changes, but don’t merge the branch! Let Developer B merge the branch to make sure the git blame log matches who worked on the branch**

### (7) Merge the PR! (Developer B)
  Refresh your pull request. Since Developer A has approved it, the merge button should now be clickable. Merge it!
  You are now able to delete this branch. This simply acts as a way to promote building different features on different branches, instead of constantly updating a used-up branch. After merging branches are normally deleted this way because if some problem ever occurs you can always manually revert the deletion!

This dance of writing code, reviewing code, responding to comments, repeating until satisfied
and approving, and finally merging the branch is a very common way to make sure that code is
well understood by the development team and up to par with the rest of the repository. By
following this format your development team will all be on the same page about the status of
the repository and every gets a chance to learn from one another.


## Copyright and Licensing

Adapted from an activity originally designed in 2016 by Darci Burdge and Stoney Jackson SOME RIGHTS RESERVED

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0
International License. To view a copy of this license, visit
http://creativecommons.org/licenses/by-sa/4.0/ .
