#Git fundamentals

## Working with branches

### Clone a branch (feature, sprint)

	$ git clone -b [branch name] https://1pls1@bitbucket.org/1pls1/developer-tools.git/wiki

### Switch to a branch

	$ git checkout [branch name]

### Retrieve last changes of a branch from the remote repository

	$ git pull origin [branch name]

### List branches
	
	$ git branch
 
### Create a new branch

	$ git branch [new branch name]

### Rename existing branch

	$ git branch -m [old branch] [new branch]

### Delete a local branch

	$ git branch -d [local branch]

### Delete a remote branch

	$ git push origin :[remote branch]

### Remove tracking of non-existing branch on the remote 

	$ git fetch -p
	
or 
	
	$ git remote prune origin

## Adding, committing, pushing your changes

###  Add specific files to staging area

	$ git add [files to stage]	

###Adding all modified and newly created files to staging area

	$ git add .

###  Adding all files (modified, created, removed) to staging area

	$ git add -A

_See : http://stackoverflow.com/questions/572549/difference-of-git-add-a-and-git-add_

###  Commit files to local repository

	$ git commit -m [Commit description. Should contain #ID of task related]

###  Push changes to remote repository

	$ git push origin <branch name>

## Merging

### Merge branch "feature-1" into branch "sprint-1"

	$ git checkout sprint-1
	$ git merge feature-1

### Merge branches "feature-1", "feature-2" and "feature-3" into branch "sprint-1"

	$ git checkout sprint-1
	$ git merge feature-1 feature-2 feature-3

## Further reading

* http://git-scm.com/book (git principles)
* http://gitref.org/ (git reference sum up)
* https://na1.salesforce.com/help/doc/en/salesforce_git_developer_cheatsheet.pdf (main git functions - PDF)

## Apps

https://www.sourcetreeapp.com

