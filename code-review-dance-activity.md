# GitHub Workflow an Project Management Reference


## Prerequisites

- You have a GitHub account and you know your username and password. If you
  don't have one, create one now.
- You have Git 2+ installed and configured.
- You know how to open a terminal and generally work from the command-line.
- You know enough of vi or vim to edit, move around in, save, and quit files.
- You have completed the other Github tutorial and have a basic understanding of it's features
- You have a basic repository, akin to the one created in the other tutorial, with mandatory code reviews


## Form teams

Form a 2-person team. If you are the odd-person-out, join a team of 2.

Assign the following roles to the members of your team. If you are in a
team of 2, assign the recorder and navigator roles to the same person.

Roles:

-   Developer A: Set's up required reviews and reviews Developer B's pull request (PR)

-   Developer B: Create's an erroneous addition and attempts to create a pull request

3rd person role (if you have a 3-person team):
-   Act as a separate reviewer of Developer B's PR.


-------------

## Pracitce the Code Review Dance

If not already the case, make code reviews required for pull requests of important branches (Step 1 below).
This helps prevent errorneous code (2) from slipping into your code base from a Pull Request (3).
Performing these code reviews (4) foster learning from your development team and sharing your own expertise.
Allowing the original coder to make changes shares your insight and maintains code ownership (5).
Multiple rounds allows for rigourous checks and understanding (6).
Mandating who merges each PR in the end maintains a good Git Blame (7).

*On GitHub*
### (1) Set up required code reviews (if necessary) (Developer A)

  Go to the project's "Settings" tab and from the left sidebar select "Branches". Under the "Protected Branches" select the master branch to protect it from deletion and pushes. Require changes to master be made through pull-requests, and require each pull-request be reviewed by a maintainer (i.e., select "Require review from Code Owners").

*On Command Line*
### (2) Create an erroneous file (Developer B)
    
  Create a new branch to work on, and in this branch create a file called "problems.rb".
  You will create a quick function that takes in a number *n* and prints "Hi *4n* times.
  Create the funtion as follows (including errors):
  * Start by defining a function that takes in one integer n.
  * Give the function a confusing, complicated, or long name (ex. “printHi3TimesNTimes”).
  * At the top of the function, put a comment saying “TODO: Fix this whole function”
    * A TODO comment like this, similar to test statements, should never make it onto your master branch and should be removed before submitting a pull request
  * Create a for loop that loops from 0 to n times
  * Create an inner for loop that loops from 0 to 3 times
  * Finally, inside the inner for loop print “Hi” with “puts “Hi””

*Locally and on Github*
### (3) Submit a PR for the file (Developer B)

  Save the file and add your changes. Push your changes and create 
  a pull request comparing your branch to master. Give your pull 
  request a good name, and to notify Developer A that you’ve made a 
  PR by including “@[Developer A’s github handle]” in the description
    
*On Github*
### (4) Review the new PR (Developer A)

  Navigate to the "Pull Requests" tab and open the new PR. Click on the “Files Changed” tab to see what the pull request covers.
  Now comment on the problems in the code, including:
  * Suggest a better name for the function
  * Recommend storing “Hi” in a variable to avoid magic values
  * Suggest combining the two nested loops into one loop for code clarity
  * Point out the “TODO” comment that should be removed
  * Make any other comments you think are necessary

*On Github and locally*
#### (5) Respond to comments (Developer B)

  Check your pull request on Github and read over the comments Developer A has 
  provided. Fix the issues they pointed out and answer any questions they left.
  Git add and push your changes and verify that your changes have been updated on the PR.

*On Github*
### (6) Look to approve the pull request (Developer A)

  Refresh the pull request and check over your comments (in most cases if you commented on the correct line, your comment should be hidden if it has been addressed).
  Quickly read over the changed code again, if you have any comments, add them and have Developer B address them.
  If you have no additional comments, on the upper right corner of “files changed” click the “review changes” button, select approve, and click “submit review”.
  **You’ve approved the changes, but don’t merge the branch! Let Developer B merge the branch to make sure the git blame log matches who worked on the branch**

### (7) Merge the PR! (Developer B)
  Refresh your pull request. Since Developer A has approved it, the merge button should now be clickable. Merge it!

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
