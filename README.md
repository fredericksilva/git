## GIT Commands


Shortcut to output commit history

```$ git config --global alias.l "log --oneline --stat"```

 Quick graph of commit history and branches

```$ git config --global alias.lol "log --graph --all --oneline --decorate"```

 Shortcut to repository status

```$ git config alias.s "status -s"```


### Details

Files in Git transition through well-defined states of tracking.

#### Adding files

 Stage all updated files

```$ git add -u [file|pattern]```

 Stage all files no matter the state

 ```$ git add -A [file|pattern]```

#### Removing files

When already tracked files are no longer needed, they can be removed from tracking and from the file system:

 Permanently delete file, stage for commit

 ```$ git rm [file]```

If there's a reason to preserve the file on disk after removing it from tracking, Git facilitates this behavior variant:

 Stop version tracking, stage for commit

 ```$ git rm --cached [file]```

#### Moving files

 Change the path of a file

 ```$ git mv [path]```

#### Reviewing moved files

 Show history including those with prior path names

 ```$ git log --stat -M```


#### Revert

Revert is the kindest undo functionality. It creates a new inverse commit and links back to the old one in the proposed commit message:

 Create a new commit undoing the patch in that specified

 ```$ git revert [commit]```

#### Reset

 Move current branch's HEAD to point in history

 ```$ git reset [commit|branch|tag]```

Reset offers a plethora of options to adjust the nuances of its restorative behavior:

 Move HEAD, keep changes in staging

 ```$ git reset --soft [commit|branch|tag]```

 Move HEAD, keep changes, clear staging area

 ```$ git reset --mixed [commit|branch|tag]```

 Move HEAD, discard all uncommitted changes

 ```$ git reset --hard [commit|branch|tag]```

#### Reviewing historical states

```$ git reflog```

Restoring a historical state

```$ git reset --[option] HEAD@{[n]}```

Specific paths

```$ git checkout HEAD@{[n]} -- [path]```

----

:octocat: [Frederick Silva](http://fs.mint-license.org) :coffee: === :yum: 
