# GitHub Tutorial

_by Sherzod Mirsharipov_

---
## Git vs. GitHub  
 **Git** is a version control program which is designed to keep track of different versions of your files and makes it easier for multiple people to work the same project at the same time.  Git can be installed on your local machine and different versions of your files live there. But others can't access your files and that's where Github comes in. **Github** is a website which requires Git to operate and stores your files in remote repositories so that **anybody** can access them at **any time**, from **any place**.
 



---
## Getting Started
 * To use Github, first you need to [_create a Github account_](https://github.com/)
 * If you don't want to download git to your computer, you can sign up with [c9](https://c9.io). c9 is a program where git is already built in, and you can you use it on any device because it is on a website. However, when you download git to your computer, you can only access your local repositories on  device.
 * If you are using c9, after signing into Github, go to top-right/profile/settings
 * Now click on SSH and GPG keys and click on New SSH key
 * Go to c9, gear-icon/SSH keys, copy the 2nd code and paste in Github and click Add SHH Key
 * To check if you did everything right, enter this command, `ssh -T git@github.com`, into the terminal
 * You should get the following message, `Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.`
 * (Creating a SSH Key connection is a one time process)



---
## Repository Setup
 *  Make a folder and go into that folder. In order to create a folder, type `mkdir`, space, then type the name you want.
 *  Type in `git init` into the terminal and now this directory is a local repository
 *  Create a file and make changes
 *  Let's create a readme file as an example. So, type `touch README.md` and type `c9 README.md` to open the file. Feel free to add anything to it.
 *  Type `git add README.md` to add the file to the staging area.
 *  Type `git commit -m "  "` to commit your file (takes a snapshot of the content) and make sure that you add a good commit message between the quotation marks
 *  Now we need to create a remote repository within Github where your files can be pushed to.
 *  Go to Github, top-left/plus-icon/new-repository
 *  Name it with the name of your local repository and click Create Repository
 *  Copy the first line of code under the writing "…or push an existing repository from the command line," it should look something like `git remote add origin URL`and this command sets up a pathway between the local and the remote repositories
 *  Now go back to C9, and paste the code into the terminal 
 *  Use `git remote -v` to check if the connection has been established
 *  Copy the second line of code and paste it into the terminal and now all of your commits have been pushed to the remote repository, it should look something like `git push -u origin master`
 *  The previous cammand tells C9 to remember where to push the commits to, so whenever you push want to push just type in `git push`
 *  This process has to be repeated for every repository that is created



---
## Workflow & Commands
 * After making changes to your file, type in `git status` into the terminal. It will show the name of the file either in red or green. Red means that the changes have not been added to the staging area and green means that they have been added to the staging area and are ready to be committed.
 * If the writing is in red, go ahead and type in `git add` followed by the file name into the terminal
 * Then type in `git commit -m "  "` with a commit message between the quotation marks. It is also important to note that present tense should be used
 * Now do `git push` to send your commits up to your remote repository
 * If an error comes up while doing any one of these processes, there is a  chance that your issue will be solved be doing `git status`



---
## Rolling Back Changes
### EDIT
 To undo the changes you've made your files, type `git checkout -- filename` and wherever you see `filename` replace it with the name of your file 

### ADD
 To undo `git add filename` type in `git reset HEAD filename`

### COMMIT
 To undo a commit type in
   * `git reset --soft HEAD~1` this undoes the last commit but the file remains staged  
* `git reset HEAD~1` undoes the last commit and unstages the file  
 * `git reset --hard HEAD~1` undoes the last commit, unstages the file and deletes the changes 

### PUSH
 `git revert <commit ID>`(SAY WHERE DO YOU FIND YOUR COMMIT ID)
 
---
 ## Error Handling
  * If you did `git init` in the wrong directory all you have to do is `rm -rf .git` this removes the file `.git/` which is created by doing `git init`
  * If you want to remove your local repository, `cd ..` out of that file and type in `rm -rf repositoryname` this repo is now gone but a copy of it lives on Github, to delete that go to Github.com/profile/repositories/the-repo-you-want-to-delete/settings/down/danger-zone/delete-this-repo and type in the exact name of the repo
