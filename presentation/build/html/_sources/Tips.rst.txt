Git Tips
========

Semantic Changes
----------------

Removing A Change From The Index
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
**Previously**
``$ git reset HEAD <file>``

Totally intuitive to use git reset to remove a file from staging right?

**New and *Slightly* Improved** 
``$ git restore --staged <file>``

Makes a little more sense, i.e. "I'm restoring the index to a previous state"

Changing Branches
~~~~~~~~~~~~~~~~~
**Previously**
``$ git checkout <branch>``

Always annoyed me

**New and Improved**
``$ git switch <branch>``

Helpful Stuff
-------------

**For Those Prone To Typos**
``$ git config --global help.autocorrect 1``

**For The Love of One-Liners**
List all untracked files
``$ git ls-files -o``

Find root directory of the repo
``$ git rev-parse --show-toplevel``

Get name of branch
``$ git rev-parse --abbrev-ref HEAD``

**Quickly Remove Old Local Branches**
``$ git pull --prune``

**Pull Remote Changes Without Merge Commit**
``$ git pull --rebase``

Creating Custom Git Commands
----------------------------

When running ``git <command`` git searches $PATH for **"<command>"** if it isn't a builtin command by looking for executable files named **git-<command>**.

This enables git to be easily extended or customized. Here's one I wrote called git-propen_.
It gathers information about the current branch then uses Github's API to open a PR quickly and easily. 

.. _git-propen: https://github.com/mraspberry/scripts/blob/master/python/bin/git-propen
