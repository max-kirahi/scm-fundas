
# **SCM Fundamentals**
One of the basics of SCM is to figure out starting out - mono repo or multiple repos. Before we get into that discussion, let's get basics of git out of the way.

## How to setup git user
```
git config user.name "adfaf"
git config user.email "adfdf@adfadf" '
```

## First time for a new repo
```
git init in the root folder
git add <folder or files>
git commit -m "Version 0.0.1"
```

Any change from this point ---> As changes in "Working area"
You can move the change to "Staging Area"  by doing a git add after the changes are made
Commit the change again to make the next Version

## Visualze all these changes
`git log --all`
only shows the latest branch info
`git log --all --graph`
shows all brnahces 

## Scenario 1

You make make changes after staging a file
this just makes another change
If thre there is another change that was changed, and now 
you try to commit the second change, both changes get merged

To remove from staging area
`git reset <folder or file>`

To remove changes from Changes area
`git checkout -- <folder or file>`

Going back to a previous version
`git checkout "version's commit hash" (for the whole repo)`

so when we go to a previous version of the repo and make changes from there
1. the HEAD moves to the new modified version - meaning the branch
2. "master" or "main" stays with the latest version on the main or master

To go back from an update to a restored version to the previous latest main or master
`git checkout master`

## Scenario 2
You are in Version 4 and now you want to go back to 
either the whole repo version 2 or 
you want only select files from version 2 
 -- to be pulled back in as the lastest main or master
 git checkout <commithascode> <file or folder>
 remember the variants of this command
 [   git checkout <file or foler> ---> undo changes in the changes area 
     git checkout <branch name> ---> makes the head point back to the master fron a branch
     git checkout <commit hashcode> <file or folder> - takes a previus version and makes it the head and master or main ]
-- Overwrites files from the previous commit hash 
-- stages the changse automatically
-- does not automatically commit
 
### Connecting to GitHub

First get the fine grained token

Create a new repo and no do not include the readme.md, as it will create a branch with the name "main" and that is a lot of trouble

get the URL of the repo (can include the git file at the end)

`git add remote origin <URL>`
Once that is done, push stuff into the cloud
`git push origin master`

Let's say you made some minor edits online and made some commits there, to figure out whats going on in the online repo, from local :
`git fetch`

After than to synch local from the cloud
`git pull origin master` (remember master is just the name of the branch for this discussion)