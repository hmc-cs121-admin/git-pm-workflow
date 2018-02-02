# GitHub Workflow Reference


## Prerequisites

- You have a GitHub account and you know your username and password. If you
  don't have one, create one now.
- You have Git 2+ installed and configured.
- You know how to open a terminal and generally work from the command-line.
- You know enough of vi or vim to edit, move around in, save, and quit files.


## Start a new project

When you start a new project, you'll want to create it inside an organization (1-2). 
This will allow everyone to contribute using the same workflow. 
It's also a good idea to configure the new project to protect the master branch from accidental deletions and from pushes, and to require that changes to master only be done through reviewed pull-requests (3). Last, you'll need to invite maintainers of the code to be collaborators on the project (4-5). This will allow maintainers to review and merge pull-requests.

*On GitHub*
```
(1) Create an organization on GitHub

    Create an organization to own the new project. 
    Use the "+" in the top right corner on GitHub and select
    "New Organization". Add all team members to the organization.
    
(2) Create official upstream repository in organization

    Navigate to the organization and create a new project/repo.
    Select "Initialize this repository with a README".
    
(3) Protect the master branch
    Go to the project's "Settings" tab and from the left sidebar 
    select "Branches". Under the "Protected Branches" select the 
    master branch to protect it from deletion and pushes. Require
    changes to master be made through pull-requests, and require
    each pull-request be reviewed by a maintainer (i.e., select
    "Require review from Code Owners").
    
(4) Add collaborators
    Select "Collaborators & teams" from the left sidebar menu.
    Invite maintainers to be collaborators on the project.
    
(5) Each maintainer accepts the invitation through their email
    or on the project's page on GitHub.
```


## Prepare to work on a project

When you first start working on a project, you'll need to fork their repo(s) into your personal GitHub account (1-3), clone your fork locally (4-6), and create a `remote` back to their project in your local repository (7-9). Once you've done this setup for a particular project, you will not need to do it again unless you delete your fork, or your local repository for the project.

Why do we need this setup using forks? 
"Most commonly, forks are used to either propose changes to someone else's project 
or to use someone else's project as a starting point for your own idea." 
<https://help.github.com/articles/fork-a-repo/>
Before proceeding, read about the difference between `upstream` and `origin`:
<https://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github/9257901#9257901>

*Using GitHub*
```
(1) Navigate to the project that was just created. 
    This is the <PROJECT_REPOSITORY_URL>.
(2) Use "Fork" to fork their project into your personal
    GitHub account.
(3) Navigate to _your_ fork of the project.
(4) Use "Clone or download" to reveal _your_ fork's repository URL. 
    This is the <FORKS_REPOSITORY_URL>.
```

*Using the command-line*
Using the command-line, navigate to the directory in which you will create a local repository. In a terminal, go to the folder where your local copy of the repo will live (for example, `cd Documents/cs121/src`).
```
(5) git clone <FORKS_REPOSITORY_URL> <LOCAL_REPOSITORY_DIRECTORY>
(6) cd <LOCAL_REPOSITORY_DIRECTORY>
```

*Using GitHub*
```
(7) Navigate to the original project's page (the one you forked from).
(8) Use "Clone or download" to reveal the project's repository URL, which
    is the <PROJECT_REPOSITORY_URL>.
```

*Using the command-line*
```
(9) git remote add upstream <PROJECT_REPOSITORY_URL>
```

## Setup a Project Management (PM) system (GitHub Projects)

GitHub provides Issues and notes (and milestones) for you to keep track and prioritize your work. 
Ambiguous tasks or ideas for future tasks should be notes while well-defined tasks (or small goals) can be added to Issues.
The objectives for the following section are to 
* Create a GitHub Project via GitHub web interface
* Add a new issue via GitHub web interface
* Add a note and turn it into an issue via GitHub web interface
* Describe the difference between issues and notes shown in a GitHub project board
* Close an issue via GitHub web interface as well as via git commit command

### Set up a GitHub Project

[Developer A] 
```
(1) On the GitHub repository, select the Projects tab and click on “New Project”. 
(2) Name the new project board “New Website” and type in some description.
(3) In the Project Template section, click on “Template: None” and change it to 
    “Kanban (Automated)”.
(4) Click on “Create Project”; this will create a project board with three columns:
    “To Do”, “In Progress”, and “Done”.
```

Your team is now ready to work on the new task (creating a new website) using GitHub Project to track and prioritize the work.
It’s now time to add some specific, well-defined work (tasks, enhancements, and bugs) using Issues to the project. 

[Developer B]

Once the project board is set up, Create a new Label “feature” for your repo. Follow steps on 
https://help.github.com/articles/creating-a-label.



### Add an Issue

Issues are a great way to keep track of tasks, enhancements, and bugs for your projects. In this step, Developer B will add their task to create an `index.html` file as an issue. 

[Developer B]

```
(1) On the GitHub repository page, select the Issues tab and click on “New Issue”. 
(2) Title the issue “Create an index.html page”.
    Leave a comment giving a description or more information about it. 
(3) Click on “Submit new issue” and you should see a new page with the issue you just created. 
(4) Assign this issue (Create an index.html page) to the New Website project. 
    On this issue page, click on the cogwheel in the Projects section of the right sidebar. 
    This will open a list of Projects in this repository. 
    Click the “New Website” project created by Developer A. 
(5) This will assign this issue to the Project and will automatically add it to the To Do column.
```




## References

[1] GitHub. *Resolving a Merge Conflict from the Command Line*. Accessed April 2016. 
<https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/>.

[2] GitHub. *About Git Rebase*. Accessed April 2016. <https://help.github.com/articles/about-git-rebase/>.


## Copyright and Licensing

Adapted from an activity originally designed in 2016 by Darci Burdge and Stoney Jackson SOME RIGHTS RESERVED

This work is licensed under the Creative Commons Attribution-ShareAlike 4.0
International License. To view a copy of this license, visit
http://creativecommons.org/licenses/by-sa/4.0/ .
