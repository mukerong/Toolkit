# Git

---

## Table of Contents 

* [Documentation](#Documentation)
* [First-time configuration](#First-time configuration)

---


### Documentation

[Git Documentation](https://git-scm.com/documentation)

### First-time configuration

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

### Common Command

```Bash
git init

git clone
```
