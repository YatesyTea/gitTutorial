# Git Basics

This file has been made in order to teach me, and potentially others in how to use git in tandem with github effectively.

![Git Logo](gitBasicsAssets/gitLogo.png)

## How Git Works

##### The version control of Git (the local section) is divided into three parts:

In the **working directory** are the changes that you make but have not told git to accept.

In the **staging area**, changes that you've told git to acknowledge are present, which you can then send to the repository, this is called a commit and is done with comments added surrounding the changes that you've made.

You can then **push the repository** as a whole to a service such as GitHub.

Or if the work changes were done on another computer/ by another user, you can pull the repository for use and viewing on your computer.



![How things work](gitBasicsAssets/gitStages.png)



## Creating Local Git Repository

Find the folder that you want to use using 

```pseudocode
ls <!-- Views the list of files within current directory -->
cd dirName <!-- Changes directory to the directory of name specified -->
mk dirName <!-- Creates a directory in the current location of name specified -->
git init <!-- Initialises a repository in the current directory -->
```



Steps

* Locate/Create location of new repository
* Use 'git init' after changing directory to the location



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

This file is still only in the staging area though, we still need to commit it to the repository.





