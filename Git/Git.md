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

"""
Create own shortcut for Sublime: http://olivierlacan.com/posts/launch-sublime-text-3-from-the-command-line/
"""

ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime

git config --global core.editor "sublime"

git config --list
```

[Reference](#reference)

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

### Make a Commit

```Bash
git commit
``` 

Need to exit text editor, not just close the window.

Each commit has a single focus, one aspect of the project. 

> Think about what should be in a commit is to think, "What if all changes introduced in this commit were erased?". If a commit were erased, it should only remove one thing.

#### Flags of git commit

```Bash
git commit -m "short commit message"
```

It cannot provide a description, only the message.

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
* [Cloning an Existing Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository#Cloning-an-Existing-Repository)
* [git clone docs](https://git-scm.com/docs/git-clone)
* [git clone Tutorial](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
* [Checking the Status of Your Files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Checking-the-Status-of-Your-Files)
* [git status docs](https://git-scm.com/docs/git-status)
* [git status Tutorial](https://www.atlassian.com/git/tutorials/inspecting-a-repository)
* [Generating patches with -p](https://git-scm.com/docs/git-diff#_generating_patches_with_p)
