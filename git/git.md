# Git

---

## Table of Contents

* [First-time configuration](#first-time-configuration)
* [Common Command](#common-command)
* [Reference](#reference)


---


## First-time configuration

```Bash
git config --global user.name "Full Name"
git config --global user.email "email address"
git config -- global color.ui auto
git config --global merge.conflictstyle diff3

# for Atom or VSCode
git config --global core.editor "atom/code --wait"

# for Sublime
git config -- global core.editor "'/Applications/Sublime Text 3.app/Contents/SharedSupport/bin/subl' -n -w"

ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime

git config --global core.editor "sublime"

git config --list
```

[Reference](#reference)

---

## Relative Commit References

Ancestry References:

* `^` - indicates the parent commit
* `~` - indicates the *first* parent commit

Parent commit:

* HEAD^
* HEAD~
* HEAD~1

Grandparent commit:

* HEAD^^
* HEAD~3

Great-grandparent commit:

* HEAD^^^
* HEAD~3

The main difference between the `^` and the `~` is when a commit is created *from a merge*. A merge commit has two parents. With a merge commit, the `^` reference is used to indicate the *first* parent of the commit while `^2` indicates the second parent. The first parent is the branch you were on when you ran `git merge` while the second parent is the branch that was merged in.

---

## Common Command

### Create a repo from scratch

```Bash
git init
```

[Reference](#reference)

### Clone an existing repo

```Bash
git clone <path> (new name)
```

[Reference](#reference)

### Display the current status of a repo

```Bash
git status
```

[Reference](#reference)

### Display all the commits of a repo

```Bash
git log
```

It will display the following by default:

* the SHA
* the author
* the date
* the message

To navigate a log:

* to scroll down by a line, use `j` or `↓`
* to scroll up by a line, use `k` or `↑`
* to scroll down by a page, use the `spacebar` or the `Page Down` button
* to scroll up by a page, use `b` or the `Page Up` button
* to scroll down by half the page, use `d`
* to scroll up by half the page, use `u`
* to quit, use `q`

[Reference](#reference)

#### Flags of git log

```Bash
git log --oneline
```

It will:

* list one commit per line
* shows the first 7 characters of the SHA
* shows the commit's message

```Bash
git log --stat
```

It will:

* display the files that have been modified
* display the number of lines that has been added/removed
* display a summary line with the total number of modified files and lines that has been added/removed

```Bash
git log --patch
git log -p
```

It will

* display the files that have been modified
* display the location of the lines that have been added/removed
* display the actual changes that have been made

```Bash
git log -p -w
```

It will ignore whitespace changes

```Bash
git log -p SHA
```

It will:

* start at that provided commit
* also show all of the commits that were made *prior* to the supplied SHA

```Bash
git log --decorate
```

It will display the tag information. In the 2.13 update to Git, this flag is automatically enabled.

```Bash
git log --graph
```

It adds the bullets and lines to the leftmost part of the output. It shows the actual branching that is happening.

```Bash
git log --all
```

It displays all of the branches in the repository.

### Show one commit

```Bash
git show SHA
```

It will display:

* the commit
* the author
* the date
* the commit message
* the patch information

It can work with flags of `git log`.


### From Working Directory to Staging Index and vice versa

```Bash
# space seperate
git add file-name1 file-name2

# to stage all files
git add .
```

```Bash
git rm --cached file-name
```

#### Ignore files

Add `.gitignore` file in the same directory that `.git` directory is located. `git add .` will ignore files within `.gitignore`.

Wildcard to use

* blank lines can be used for spacing
* \# - marks line as a comment
* \* - matches 0 or more characters
* ? - matches 1 character
* [abc] - matches a, b, or c
* \*\* - matches nested directories - a/**/z matches
	* a/z
	* a/b/z
	* a/b/c/z

### Make a Commit

```Bash
git commit
```

Need to exit text editor, not just close the window.

Each commit has a single focus, one aspect of the project. Finish this phrase for better commit message, "This commit will ...".

> Think about what should be in a commit is to think, "What if all changes introduced in this commit were erased?". If a commit were erased, it should only remove one thing.

**Do**

* keep the message short
* explain *what* the commit does (not *how*or *why*)

**Do not**

* explain *why* the changes are made
	* can be included in the description section
* explain *how* the changes are made (that's what `git log -p` is for)
* use the work *and*
	* using *and* might mean the commit is doing too many changes - break the changes into separate commits

#### Flags of git commit

```Bash
git commit -m "short commit message"
```

It cannot provide a description, only the message.

```Bash
git commit --amend
```

Two usage:

* change the last commit message when Working Directory is clean
* add forgotten files to commit
    * edit the file, save the file, stage the file, and run `git commit --amend`

[Reference](#reference)

### Show non-committed changes

```Bash
git diff
```

It will displays

* the files that have been modified
* the location of the lines that have been added/removed
* the actual changes that have been made

### Tagging

```Bash
git tag v1.0 SHA
```

It creates a lightweight tag.

#### Flags of git tag

```Bash
git tag -a name SHA
```

It creates an annotated flag.

It is recommended because it includes extra information:

* the person who made the tag
* the date the tag was made
* a message for the tag

```Bash
git tag -d tag-name SHA
```

### Interact with Git's branches

```Bash
git branch
```

It can be used to:

* list all branch names
* create new branches
* delete branches


#### Flag of git branch

```Bash
git branch -d repo-name
```

It will delete the provided branch. You can not delete the branch you are currently on.

```Bash
git branch -D repo-name
```

It will force delete a repo when there is unique commits within this repo.

### Switch branches

```Bash
git checkout repo-name
```

It will:

* remove all files and directories from the Working Directory that Git is tracking
	* Nothing is lost since files that Git tracks are stored in the repository
* go into the repository and pull out all of the files and directories of the commit that the branch points to

#### Flag of git checkout

```Bash
git checkout -b <name-of-new-branch> <name-of-old-branch>
```

It will create a new branch and switch to it.

### Merge

```Bash
git merge <name-of-branch-to-marge-in>
```

It will:

* look at the branches that is going to merge
* look back along the branch's history to find a single commit that both branches have in their commit history
* combine the lines of code that were changed on the separate branches together
* make a commit to record the merge

Two types of Merge:

* Fast-forward merge - the branch being merged in must be ahead of the checked out branch. The checked out branch's pointer will just be moved forward to point to the same commit as the other branch
* the regular type of merge
    * two divergent branches are combined
    * a merge commit is created

If you make a merge on the wrong branch, use the following command to undo the merge:

```Bash
git reset --hard HEAD^
```

`^` means "Relative Commit Reference"

[Reference](#Reference)

### Revert a commit

```Bash
git revert <SHA>
```

It will:

* undo the changes that were made by the provided commit
* creates a new commit to record the changes

[Reference](#Reference)

### Reset commits

```Bash
git reset <reference-to-commit>
```

It will

* move the HEAD and current branch pointer to the referenced commit
* erase commits
* move committed changes to the staging index
* unstage committed changes

Since it will erase commits from the current branch. You can create a backup branch on the current commit if you want to follow along with all the resetting stuff that is coming up.

```Bash
git branch backup
```

#### Flags of git reset

```BASH
git reset --mixed
```

This is the default setting. It will move the commit to the Working Directory.

```BASH
git reset --soft
```

It will move the commit directly to the Staging Index.

```BASH
git reset --hard
```

It will take the changes in given commit and erases them.

### Get the history back

```Bash
git reflog
```

[Reference](#Reference)

### Reference

* [Git Documentation](https://git-scm.com/documentation)
* [Git Configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)
* [Git Internals - Plumbing and Porcelain](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain)
* [Customizing Git - Git Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
* [Initializing a Repository in an Existing Directory](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository#Initializing-a-Repository-in-an-Existing-Directory)
* [git init docs](https://git-scm.com/docs/git-init)
* [git init Tutorial](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
* [Getting Started - First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
* [Associating text editors with Git](https://help.github.com/articles/associating-text-editors-with-git/)
* [Create own shortcut for Sublime](http://olivierlacan.com/posts/launch-sublime-text-3-from-the-command-line/)
* [Cloning an Existing Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository#Cloning-an-Existing-Repository)
* [git clone docs](https://git-scm.com/docs/git-clone)
* [git clone Tutorial](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
* [Checking the Status of Your Files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Checking-the-Status-of-Your-Files)
* [git status docs](https://git-scm.com/docs/git-status)
* [git status Tutorial](https://www.atlassian.com/git/tutorials/inspecting-a-repository)
* [Generating patches with -p](https://git-scm.com/docs/git-diff#_generating_patches_with_p)
* [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)
* [What’s with the 50/72 rule?](https://medium.com/@preslavrachev/what-s-with-the-50-72-rule-8a906f61f09c)
* [A Note About Git Commit Messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
* [Udacity Git Commit Message Style Guide](https://udacity.github.io/git-styleguide/)
* [gif diff docs](https://git-scm.com/docs/git-diff)
* [Ignoring files from the Git Book](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Ignoring-Files)
* [gitignore from the Git Docs](https://git-scm.com/docs/gitignore#_pattern_format)
* [Ignoring files from the GitHub Docs](https://help.github.com/articles/ignoring-files/)
* [gitignore.io](https://www.gitignore.io)
* [Git Basics - Tagging ](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
* [Git Tag](https://git-scm.com/docs/git-tag)
* [Git Branching - Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
* [Learn Git Branching](http://learngitbranching.js.org)
* [Git Branching Tutorial](https://www.atlassian.com/git/tutorials/using-branches)
* [Basic Merging from Git Book](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging#Basic-Merging)
* [git-merge from Git Docs](https://git-scm.com/docs/git-merge)
* [git merge from Atlassian blog](https://www.atlassian.com/git/tutorials/git-merge)
* [Basic Merge Conflicts from the Git book](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging#Basic-Merge-Conflicts)
* [How Conflicts Are Presented from the Git docs](https://git-scm.com/docs/git-merge#_how_conflicts_are_presented)
* [git-revert from Git Docs](https://git-scm.com/docs/git-revert)
* [git revert Atlassian tutorial](https://www.atlassian.com/git/tutorials/undoing-changes)
* [git-reset from Git docs](https://git-scm.com/docs/git-reset)
* [Reset Demystified from Git Blog](https://git-scm.com/blog)
* [Ancestry References from Git Book](https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection#Ancestry-References)
* [git-reflog](https://git-scm.com/docs/git-reflog)
* [Rewriting History](https://www.atlassian.com/git/tutorials/rewriting-history)
* [reflog, your safety net](http://gitready.com/intermediate/2009/02/09/reflog-your-safety-net.html)
