# Some useful Git Commands


```
$ git init
```
  - Running this command creates a hidden .git directory.
    ```
		* This .git directory is the brain/storage center for the repository.
		* It holds all of the configuration files and directories and is where all of the commits 
		  are stored.
      ```
      ---

```
$ git clone <path-to-repository-to-clone>
$ git clone <path-to-repository-to-clone>  <new directory-name>
```
  - The git clone command is used to create an identical copy of an existing repository.
     ```
	This command:
	    * takes the path to an existing repository
	    * by default will create a directory with the same name as the repository that's being cloned
	    * can be given a second argument that will be used as the name of the directory
	    * will create the new repository inside of the current working directory
       ```
    ---


*  $ git status

	The git status command will display the current status of the repository.

	This command will tell us about:
	    * new files that have been created in the Working Directory that Git hasn't started 
	      tracking, yet
	    * files that Git is tracking that have been


*  $ git log

	By default, this command displays:

	    * the SHA
	    * the author
	    * the date
	    * and the message

  $ git log --oneline

  	the --oneline flag is used to alter how git log displays information

	This command:
	    * lists one commit per line
	    * shows the first 7 characters of the commit's SHA
	    * shows the commit's message

  $ git log --stat

    the --stat flag is also used to alter how git log displays information.

	This command:
	    * displays the file(s) that have been modified
	    * displays the number of lines that have been added/removed
	    * displays a summary line with the total number of modified files and lines that 
	      have been added/removed

  $ git log -p

    the -p flag (which is the same as the --patch flag) is also used to alter how git log 
    displays information

	This command adds the following to the default output:
	    * displays the files that have been modified
	    * displays the location of the lines that have been added/removed
	    * displays the actual changes that have been made

    you can supply the SHA of a commit as the final argument for all of these commands? 
    For example:   $ git log -p fdf5493


*  $ git show

	The git show command will show only one commit. So don't get alarmed when you can't find any other 
	commits - it only shows one. The output of the git show command is exactly the same as the 
	git log -p command.

	 So by default, git show displays:
	    * the commit
	    * the author
	    * the date
	    * the commit message
	    * the patch information

	However, git show can be combined with most of the other flags we've looked at:

	    * --stat - to show the how many files were changed and the number of lines that 
	      were added/removed
	    * -p or --patch - this the default, but if --stat is used, the patch won't display, so 
	      pass -p to add it again
	    * -w - to ignore changes to whitespace



*  $ git add <file1> <file2> … <fileN>

	The git add command is used to move files from the Working Directory to the Staging Index.

	This command:
	    * takes a space-separated list of file names
	    * alternatively, the period . can be used in place of a list of files to tell Git to add 
	    the current directory (and all nested files)


*  $ git commit

	The git commit command takes files from the Staging Index and saves them in the repository.

	This command:
		* will open the code editor that is specified in your configuration

	Inside the code editor:

	    * a commit message must be supplied
	    * lines that start with a # are comments and will not be recorded
	    * save the file after adding a commit message
	    * close the editor to make the commit


*  $ git diff

	the git diff command is used to see changes that have been made but haven't been committed, yet.

	This command displays:
    	* the files that have been modified
    	* the location of the lines that have been added/removed
    	* the actual changes that have been made


*  $ git tag -a beta

	the git tag command is used to add a marker on a specific commit. The tag does not move around as
	new commits are added.

	This command will:
	    * add a tag to the most recent commit
	    * add a tag to a specific commit if a SHA is passed


*  $ git branch                     		//to list all branches 
   $ git branch footer-fix          		//to create a new "footer-fix" branch
   $ git branch -d footer-fix				//to delete the "footer-fix" branch

	This command is used to:

	    * list out local branches
	    * create new branches
	    * remove branches


*  $ git merge <other-branch>              			// fast-forward merge
   $ git merge <other-branch> <master-branch>		// regular merge

	There are two types of Merges:

	    * Fast-forward merge:

		    * The branch being merged in must be ahead of the checked out branch. The checked out branch's 
		      pointer will just be moved forward to point to the same commit as the other branch.
	    
	    * The Regular type of merge:

	        * two divergent branches are combined
	        * a merge commit is created

	Resolving A Merge Conflict

		Git is using the merge conflict indicators to show you what lines caused the merge conflict on 
		the two different branches as well as what the original line used to have. So to resolve a merge  
		conflict, you need to:

		    * choose which line(s) to keep
		    * remove all lines with indicators


*  $ git commit --amend 						//  to Alter the most recent commit

		If your Working Directory is clean (meaning there aren't any uncommitted changes in the 
		repository), then running git commit --amend will let you provide a new commit message. 
		Your code editor will open up and display the original commit message. Just fix a  
		misspelling or completely reword it! Then save it and close the editor to lock in the 
		new commit message.


*  $ git revert <SHA-of-commit-to-revert>

	the git revert command is used to reverse a previously made commit:

	This command:
	    * will undo the changes that were made by the provided commit
	    * creates a new commit to record the change


*  $ git reset <reference-to-commit>

	the git reset command is used erase commits.
	It can be used to:

	    * move the HEAD and current branch pointer to the referenced commit
	    * erase commits with the --hard flag
	    * moves committed changes to the staging index with the --soft flag
* unstages committed changes --mixed flag
