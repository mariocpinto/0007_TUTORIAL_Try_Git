
## Try Git: Tutorial Notes

These notes are based on Code School's [Try Git](https://www.codeschool.com/courses/try-git) tutorial.

The below image from Oliver Steele's [blog post](http://blog.osteele.com/posts/2008/05/my-git-workflow/) is a useful aid in understanding the commands:

![Git data transport commands](http://assets.osteele.com/images/2008/git-transport.png)

These are the commands that the tutorial covers:

``` git init ```:
Used to initialize an empty repository.

``` git status ```:
Get current status of git.
Status types:
* _staged_: Files are ready to be committed.
* _unstaged_: Files with changes that have not been prepared to be committed.
* _untracked_: Files aren't tracked by Git yet. This usually indicates a newly created file.
* _deleted_: File has been deleted and is waiting to be removed from Git.

``` git add <filename> ```:
Add a file to git staging area and start tracking the file. 
If you want to add multiple files, you can use * e.g. ```*.txt```.
Note that you need to use single quotes, so that git can recursively look into sub-directories and add files from those locations too.
It is a good practice to check which files are staged (using the git status command) prior to adding files using a wildcard character i.e. *.

``` git commit -m <’message’> ```:
Commit the code so that it is part of the repository, with a message for future reference.
Note: In addition, using the ```-a``` flag removes any files that were not deleted using ```git -rm``` command.

``` git log ```:
View history of commits. Use the ```--summary``` flag with this command for more information on each commit.

``` git remote add <remote_repository_name> <repository_url> ```:
Add a remote repository in order to push local changes to a remote server. You will first need to create a remote repository (on github) if there isn’t one already. Note: It’s typical to name your main remote repository ‘origin’.

``` git push -u <remote_repository_name> <local_branch_name> ```:
Push local changes to the remote repository.
The remote repository should be added first using the ```git remote add``` command.
The default local branch name is ‘master’.
The ```- u``` flag let’s git remember the parameters, so that you can use just ```git push``` the next time.

``` git pull <remote_repository_name> <local_branch_name> ```:
Check for changes on the remote repository and pull any changes to your local branch.
Note: if you have some local changes that you don’t want to apply prior to pull, you can stash them using ```git stash``` and then apply them later after the pull using ```git stash apply```.

``` git diff <pointer_to_the_commit_you_want_to_diff_with> ```:
List differences between the current version of the code and the version of the code referenced by the passed pointer.
If you want to compare the current / pulled version with the last committed version, you can use the HEAD pointer which by default points to the last committed version of the code.
Using the ```-- staged``` flag instead of the HEAD or another pointer lets you see differences between current code and the staged version instead.

``` git reset <filename> ```:
Unstage file ‘filename’.

``` git checkout -- <filename>```:
Roll back changes to file ‘filename’ so that it is set to the last committed version of the file.
Note: Having ```--``` is an extra precaution - if there is a branch with the same name as ‘filename’ then having the ```--``` with no options will still ensure that the checkout of the file still proceeds as expected.

``` git branch <branch_name>```:
Create a branch i.e. a copy of the code to make further modifications on.
Used without the ‘branch_name’ parameter, this command will list all the code branches with an ‘*’ indicating the active branch.
When used with the ```-d``` flag, the target branch is deleted (provided the branch has been merged. If you want to delete a branch that has not been merged, use ```-df``` or ``-D``` flag (both are equivalent).

``` git checkout <branchname>```:
Switch to ‘branchname’ branch. Note the contrast with the other usage of this same command.

``` git checkout -b <branchname>```:
This command does two things at once - it both creates a branch and then switches to it. It is the equivalent of using ```git branch <branchname>``` and ```git checkout <branchname>```.

``` git rm <’filename’>```:
Remove files from disk and also stage them for removal from the repository.
Note: This card can be used with wildcard ‘*’ to remove multiple files, and with the ```-r <foldername>``` flag to recursively remove files from subfolders and files within the target folder including the target folder.

``` git merge <branchname>```:
Merge changes from ‘branchname’ to the current branch.

#### Additonal Comments:
1. If you have created/forked a repo on github, then you can get a local copy using ``` git clone <repo path>```.
In this case, you do not need to use ```git init```, ```git remote```, and you can use ```git push``` without specifying any parameters.

2. For help on any git command, use ```git help <command_name>```.

#### Additonal Resources:
* [Git documentation](http://git-scm.com/docs)
* [Pro Git book](http://git-scm.com/book/en/v2)
* [help.github](https://help.github.com/)
* [GitHub Training](https://training.github.com/)
* [Code School courses](https://www.codeschool.com/paths/git)
