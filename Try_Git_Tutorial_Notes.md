
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
If you want to add multiple files, you can use * e.g. ‘*.txt’.
Note that you need to use single quotes, so that git can recursively look into sub-directories and add files from those locations too.
It is a good practice to check which files are staged (using the git status command) prior to adding files using a wildcard character i.e. *.







Note: It there is already an existing repository that you want to contribute to, then you should use ``` git clone <repo path>``` instead to get a copy of the repo to your local machine.

git clone
git help

