# Git Basics

## Table of Contents

1. [Introduction](#Introduction)
2. [How Git Works](#How Git Works)
3. [Creating a Local Git Repository](#Creating a Local Git Repository)
4. [Adding a new File To The Repository](#Adding a New File To The Repository)
5. [Creating a New Branch](#Creating a New Branch)
6. [Create a Repository on GitHub](#Create a Repository on GitHub)
7. [Pushing a Branch to Github](#Pushing a Branch to GitHub)
8. [Creating a Pull Request](#Creating a Pull Request)
9. [Merging a Pull Request](#Merging a Pull Request)
10. [Cleaning Up](#Cleaning Up)
11. [Getting Stuff From Gihub Back](#Getting Stuff From GitHub Back)
12. [List of Bash and Git Commands](#List of Relevant Bash and Git Commands)


<h2 id = "Introduction">Introduction</h2>

This file has been made in order to teach me, and potentially others in how to use git in tandem with GitHub effectively.

This only covers the extreme basics, and will not be able to troubleshoot any major issues.

![Git Logo](gitBasicsAssets/gitLogo.png)



<h2 id = "How Git Works">How Git Works</h2>

### The 3 parts of Git

In the **working directory** are the changes that you make but have not told git to accept.

In the **staging area**, changes that you've told git to acknowledge are present, which you can then send to the repository, this is called a commit and is done with comments added surrounding the changes that you've made.

You can then **push the repository** as a whole to a service such as GitHub.

Or if the work changes were done on another computer/ by another user, you can pull the repository for use and viewing on your computer.



![How things work](gitBasicsAssets/gitStages.png)



## Creating Local Git Repository


Find the location for the directory where you want to initialise this git repository using:

```pseudocode
ls
```

This will display all of the contents of the current directory.



You can move to the  target directory and then initialise the repository using:

```pseudocode
cd targetDirectory
git init
```

This will the initialise the repository.



## Adding a New File To The Repository


You can save a file in the directory, or use the touch command:

```pseudocode
touch fileName.fileType
```


Then use the status command to see what files git acknowledges:

```pseudocode
git status
```


It will then display text like this:

```pseudocode
On branch master

Initial commit

Untracked files:
	(use "git add <file>..." to include in what will be commited)
	
		fileName.fileType
		
nothing added to commit but untracked files present (use "git add" to track)
```


This means that we need to add the file to the staging area, we do this using the add command:

```pseudocode
git add fileName.fileType
```


Now when you type the status command:

```pseudocode
On branch master

Initial commit

Changes to be commited:
	(use "git rm --cached <file>" to unstage)
	
		new file:	fileName.fileType
```



This file is still only in the staging area though, we still need to commit it to the repository:

```pseudocode
git commit -m "Comment on what you're commiting..."
```


This will then return something along the lines of:

```pseudocode
[master (root-commit) kjfkdsf23] Comment on what you're commiting...
	1 file changed, 1 insertion(+)
	create mode 100644 fileName.fileType
```

Always make sure that the comment on the commit is relevant to the commit that you are making.



## Creating a New Branch

We use this when we're scared that we might break something by adding things, it makes sure that even if there's complete nuclear meltdown it doesn't affect the master branch.

To start with we want to use the git command below

```pseudocode
git checkout -b branchName
```

This will create the branch, and then move you to that branch as your current place where all changes take place.

You can then use the git branch command for confirmation of both creation and movement over to the new branch.

```pseudocode
git branch
	master
   *branchName
```

The asterisk refers to the branch that you're currently pointing to.

You can then change between branches by using the checkout command, for example if we want to change back to the master branch.

```pseudocode
git checkout master
```

Any changes that you make to the master will not be made to the branch and vice-versa.



## Create a Repository on GitHub

![GitHub Logo](gitBasicsAssets/githubLogo.png)

There is no way to do this directly from git bash unfortunately.
You therefore have to use either, the github gui client, or the github website in order to create a repository.
On both, you create the repository by clicking a create repository button and filling in the relevant details such as name and description, alongside a readme file.

You are then asked if you would like to create a repository from scratch or use one that you have created locally.
When you select the locally one you will then want to input in your git bash:

```pseudocode
git remote add origin https://github.com/userHandle/repositoryName.git
git push -u origin master
```

This should then respond with:

```pseudocode
Counting objects: 6, done.
Writing objects: 100% (6/6), 1226 bytes | 0 bytes/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/userHandle/repositoryName.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

With this the repository is initialised on GitHub.



## Pushing a Branch to GitHub

Pushing onto GitHub doesn't automatically override everything that is already there, you will have to merge with the master branch later:

```pseudocode
git push origin branchName
```

After this, you can then press the green button titled "Compare and pull request".



## Creating a Pull Request

This is way to notify repository owners of changes that you want to make to the 'code'.
The owner can then review it and decide whether to allow it.



## Merging a Pull Request

This is done by clicking the green button titled "Merge pull request", this will then merge the branch with the master.
In some cases there will be a merge conflict, in which case you need to tell git what to use and what to chuck.

While you don't 100% have to do this as a sole owner, it does make it more clear what you're doing and is good practice for documentation of your project.



## Cleaning Up

After making sure that the request was properly executed, it is good practice to delete the branch that was just added, this clears out space and makes things less confusing in the long run.



## Getting Stuff From GitHub Back

Things will be different on your computer than from GitHub at this point, and considering this is all about version control, that ain't good chief.
You can resolve this by pulling from GitHub to your local repository:

```pseudocode
git pull origin master
```



It will then return something like this:

```pseudocode
remote: Counting objects: 1, done.
remote: Total 15 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/userHandle/repositoryName.git
 * branch            master     -> FETCH_HEAD
   b39487d..b39387d  master     -> origin/master
Merge made by the 'recursive' strategy.
 fileName.fileType | 1 +
 1 file changed, 15 insertion(+)
```



## List of Relevant Bash and Git Commands

```pseudocode
ls <!-- Views the list of files within current directory -->
cd dirName <!-- Changes directory to the directory of name specified -->
mk dirName <!-- Creates a directory in the current location of name specified -->
git init <!-- Initialises a repository in the current directory -->
```



