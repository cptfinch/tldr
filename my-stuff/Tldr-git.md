---
tags:
  - cheatsheet
---

## Create diff of 2 branches:

`git diff branch1 branch2`

`git diff branch1:file1 branch2:file2`

## Apply the diff to branch 1 -> working copy . 

```
git apply < patch 
git apply --reject --whitespace=fix < patch
```

## Add one by one the changes , or refuse them:

`git add -p`

## Make working same as staged

`git worktree add -b`

# repo, staged, working

![git1.png](../_resources/65ebeb5713c943c59b5a831ad8db7fa0.png)
[TODO]

git stash push --patch


log in to cyclhad.org
1, passwords - root - change
2, authorized_keys - root
3, nagios configs - if have logged in to nagios with agent forwarding, then can get to gitlab. git checkout; the git repo should be set up as a group node.
local repo files should be g+swX  this means that anyting new created will be in teh git users group.


What SCM do you use? if using Git you can:

Before generating the actual patch use git add -p to only add parts of your changes. It is good practice to generate smaller commits with only related changes (however some organizations don't like this and only allow a mega commit).

If you already have the patch apply it then use git add -p to add the parts of the code you want to keep to your index. You can commit and throw away the rest (git co .) or stash it (git stash).

edit (based on the git add -p comment)

git add -p allows you to split a hunk into smaller pieces using the s option, in cases when you need more detail you need to use the e option to edit, that will take you to your gitconfig editor and it will have the instructions on how to edit the hunk.


The problem with git add -p is that it only offers small part of the functionality that git diff (and its underlying driver) offers. For instance, if I want to make sense of the changes I have made before committing, using -w flag to git diff to ignore the white-space, that helps me nil if I want to git add -p some of these changes interactively, because there is no -w for git add. What people do is that they generate the patch file with git diff -w ... and then use git apply, but that again brings them back to a patch editor -- since git add is not there to help them. – amn Jul 20 '16 at 13:47




# Testing my Style.css file


[TODO] what does this command do ?  git stash push --patch

[TODO] find the _resources folder where many images are saved   ![git1.png](../_resources/65ebeb5713c943c59b5a831ad8db7fa0.png)


## create diff of 2 branches:
git diff branch1 branch2

git diff branch1:file1 branch2:file2

## Apply the diff to branch 1 -> working copy . 
git apply < patch 

git apply --reject --whitespace=fix < patch

## Add one by one the changes , or refuse them:
git add -p

## make working same as staged
git worktree add -b

## The 3 locations of git


![repo, staged, working](2021-11-18-12-37-55.png)
<figcaption>

repo, staged, *working* 

</figcaption>

<a href="bbc.co.uk">hello</a>


## Update local config files using git , and allow a group to do it not just the owner

nagios configs - if have logged in to nagios with agent forwarding, then can get to gitlab. git checkout; the git repo should be set up as a group node.

local repo files should be g+swX  this means that anyting new created will be in teh git users group.


## Using `git add -p`
Before generating the actual patch use git add -p to only add parts of your changes. It is good practice to generate smaller commits with only related changes (however some organizations don't like this and only allow a mega commit).

If you already have the patch apply it then use git add -p to add the parts of the code you want to keep to your index. You can commit and throw away the rest (git co .) or stash it (git stash).

edit (based on the git add -p comment)

git add -p allows you to split a hunk into smaller pieces using the s option, in cases when you need more detail you need to use the e option to edit, that will take you to your gitconfig editor and it will have the instructions on how to edit the hunk.

The problem with git add -p is that it only offers small part of the functionality that git diff (and its underlying driver) offers. For instance, if I want to make sense of the changes I have made before committing, using -w flag to git diff to ignore the white-space, that helps me nil if I want to git add -p some of these changes interactively, because there is no -w for git add. What people do is that they generate the patch file with git diff -w ... and then use git apply, but that again brings them back to a patch editor -- since git add is not there to help them. – amn Jul 20 '16 at 13:47


![](2021-11-18-12-35-40.png)