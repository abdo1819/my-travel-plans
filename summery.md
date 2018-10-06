# git cheat sheet


# globing
* blank lines can be used for spacing
* \# - marks line as a comment
* \* - matches 0 or more characters
* ? - matches 1 character
* [abc] - matches a, b, _or_ c
* ** - matches nested directories - a/**/z matches
    * a/z
    * a/b/z
    * a/b/c/z
    
# git tricks 
## view all branches graphicaly
> git log --graph --oneline --all
> gitk --all


## commit and stage all modefied files 
> git commit -am "massega"
## add chages to must resent commit
> git commit --amend
## remove changes from a commit
> git revet sha-1


## git reset 
> git reset <reference-to-commit> [--option]

move the HEAD and current branch pointer to the referenced commit
* erase commits with the --hard flag
* moves committed changes to the staging index with the --soft flag
* unstages committed changes --mixed flag

## parent relation
^ – indicates the parent commit

~ – indicates the first parent commit
![parents relation]()

<img src="https://wac-cdn.atlassian.com/dam/jcr:cb2ce970-3ef4-4eda-96a9-fe990745f5a7/02.svg?cdnVersion=jx"
     alt="Markdown Monster icon"
     style="background-color:white"
	 />



#work with remote

> git remote add 

is used to add a connection to a new remote repository.
> git remote -v

is used to see the details about a connection to a remote.

> git push origin master

 is used to send commits from a local repository to a remote repository.
> git pull origin master

geting commit from web

if web and local is changed
> git fetch origin master

> git merge origin master

# sync the remote repository to my fork
* get the cloneable URL of the source repository
* create a new remote with the *git remote add* command
* use the shortname *upstream* to point to the source repository
* provide the URL of the source repository
* fetch the new *upstream* remote
* merge the *upstream*'s branch into a local branch
* push the newly updated local branch to your *origin* repo

<div class="index--markdown--3w8oF ureact-markdown ">

## Rebase Commands

# `git rebase` :

*   use `p` or `pick` – to keep the commit as is
*   use `r` or `reword` – to keep the commit's content but alter the commit message
*   use `e` or `edit` – to keep the commit's content but stop before committing so that you can:
    *   add new content or files
    *   remove content or files
    *   alter the content that was going to be committed
*   use `s` or `squash` – to combine this commit's changes into the previous commit (the commit above it in the list)
*   use `f` or `fixup` – to combine this commit's change into the previous one but drop the commit message
*   use `x` or `exec` – to run a shell command
*   use `d` or `drop` – to delete the commit



##  list all the files that were added to the project, but not to the repo:

	git ls-files --exclude-standard --others

##  add some color to all the git output:

	git config --global color.ui true

##  choose which particular changes to stage:

	git add -p

##  see only changes that are in stage mode (ready to be commited):

	git diff --staged

##  see what was changed by commits + number of changes per file:

	git log --stat

## create branch (git branch [name]) go to it (git checkout [name]) at the same time:

	git checkout -b [name]

## show last commit on each branch:

	git branch -v

## show commits/history by branches in ascii gui:

	git log --graph --all

## show what is in one branch, but not in another:

	git log --stat onebranch --not another

## show who changed the line + where it traveled to this file from:

	git blame -C /path/to/the/file.groovy

## alias to display one liner history/log changes (put it into ~/.gitconfig):

    [alias]
        lol = log --pretty=oneline --abbrev-commit --graph --decorate 

## find the bad commit in a range of commits:

	git bisect start			// start the engine
	git bisect bad				// say that the point where I am right now is bad
	git bisect good cdf9d16		// say that at (commit's SHA1) that commit it was definitely good
	
	...git will be checking out (in a binary search way) different commit states, I can run my tests on that state, and tell git:

	...git bisect good OR git bisect bad

	...so it'll half up or down and gives me a new state to check

## reset to a particular point in time:

    git reset SHA1	// e.g. after 'git lol', you find the SHA1 you want to go to ( git reset 0179017 )

	...current modifications are still in act at this point, so branch pointer is reset to '0179017', 
       however all the files/content is still at its latest state. 
       To change that - to ignore all the present content and really go to '0179017':

    git reset --hard

## merge 'this' particular commit (SHA1):

	git cherry-pick 0179017




