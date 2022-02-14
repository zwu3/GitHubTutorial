#Github Tutorial

This will be a step-by-step tutorial on using Github. We will be learning how to use the commands to submit projects. The tutorial will use a coding example to guide you through some of the basics of Github. The tutorial will cover the uses of stashes, branches and merging.

##Step1:

Visit [https://github.com](https://github.com) to create a new account.
Pick a username following by your email address and desired password.

##Step2:
Check your machine to see if “git” is installed.
Open the terminal and enter:
`git version`

It should show the version of “git” on your machine if is already installed.

If not, we can install it with “home brew”

Simply type in:

`brew install git`

checked if is installed successfully by typing in “git version” after the instructions.

##step3:

After installing, we want to tell “git” about our identity, using the following command will save your profile information as your identity.
`$ git config --global [user.name](http://user.name/) "Gov"
`
`$ git config --global user.email [gov@edu.com](mailto:gov@edu.com)`

verify your information using
`git config --global --list`

#### Git overview 
- Working tree: Which corresponds to the current state of files on your filesystem
- Staging area : Which is the area that you can use to prepare commits/temporaily save your work
- Local Repository: is a Git repository that is stored on your computer
-  Remote Repository: is a Git repository that's hosted on the Internet or another network
#### Initialization
Here is an examply of a python code in `fruit.txt`
```Python

fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)
  if x == "banana":
    break
```
We should initialize a repo within the directory that it's located in. 
`$ cd <directory path>` 
 This command will navigate to the rirectory
Then we intialize **Git Repository** with:
`$ git init`
Then we add our files to the stagin area by
`$ gt add <fruit.txt>`
For mutiple files, use
`$ git add -A`
#### Commit 
Then we need to commit the file to local repository, by:
`$ git commit -m "<a message or a comment>"`

#### Remote Repository sync
Then we need to link our local repo with a remote repo that is independent from our computer. 
Create a new Repository and copy the link under `Quick setup`
link local repo with remote repo, by:
`$ git remote add origin <url link>`
we nedd to **push** the changes and the python code to the remote repo. Using:
`$ git push -u origin <branch name>`
You can download a remote repository hosted on Github, by:
`$ git clone <repository url>`

####Branching 
A branch is essentially is a unique set of code changes with a unique name. Each repository can have one or more branches. The main branch — the one where all changes eventually get merged back into, and is called master. This is the official working version of your project, and the one you see when you visit the project repository at github.com/yourname/projectname.
Use following command to create a new branch:
`$ git branch <name of new branch>`
Let's call this branch name "helloworld".
`$ git branch fruit`
we can swich from tha main branch to the new `helloworld` branch using:
`$git cheout <branch name>`
so
`$git cheout fruit`
Now lets add our changes 
```Python

fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)
  if x == "banana":
    break
```
Use the same command above where we used to update changes and new commits. 
```
$ git add -A
$ git commit -m "Added fruit func."
```
####Merging synchronization
You can sync your local branch with the remote repository by pulling any commits that have been added to the branch on GitHub since the last time you synced. If you make commits from another device or if multiple people contribute to a project, you will need to sync your local branch to keep the branch updated.
Let's combine the two branch using **Merging** method.
- First navigate back to the main branch:
`$ git checkout <mainl branch name>`
- Command to merge:
`$ git merge remainder`. 
- Then delete the **remainder** branch :
`$ git branch -d remainder`
#### Stashing
To apply your changes to your repository, you must save the files and then commit the changes to a branch. If you have saved changes that you are not ready to commit yet, you can stash the changes for later. When you stash changes, the changes are temporarily removed from the files and you can choose to restore or discard the changes later. You can only stash one set of changes at a time with GitHub Desktop. If you use GitHub Desktop to stash changes, all unsaved changes will be stashed. After you stash changes on a branch, you can safely change branches or make other changes to your current branch.
Save your changes in the **main** branch:
`$ git stash -u`
commit and push to remote:
`$ git stash pop`
#### Pull request
Pull requests let you tell others about changes you've pushed to a branch in a repository on GitHub. Once a pull request is opened, you can discuss and review the potential changes with collaborators and add follow-up commits before your changes are merged into the base branch. When you create a pull request, you can choose to create a pull request that is ready for review or a draft pull request. Draft pull requests cannot be merged, and code owners are not automatically requested to review draft pull requests. 
- Navigate to the original repository where you created your fork.
- Above the list of files, click  Pull request.
- On the Compare page, click compare across forks.
- In the "base branch" drop-down menu, select the branch of the upstream repository you'd like to merge changes into.
- In the "head fork" drop-down menu, select your fork, then use the "compare branch" drop-down menu to select the branch you made your changes in.
- Type a title and description for your pull request.
- To create a pull request that is ready for review, click Create Pull Request. To create a draft pull request, use the drop-down and select Create Draft Pull Request, then click Draft Pull Request.


