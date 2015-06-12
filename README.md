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

#### Commitish

Historical commit points are simple to discuss using commitish rather than hexadecimal SHA1 identifiers. This shorthand works on the command line, as well as on GitHub.


| Shorthand | Explanation |
| ------------- | ------------|
| HEAD	| Current commit |
| ```HEAD^^``` |	Second parent of current commit|
| ```HEAD~2``` |	Two commits from current commit|
| ```HEAD@{one.day.ago}```|	Reachable by current branch from one day ago |
| ```HEAD@{today}```	|All commits reachable by current branch made today|

#### Navigation history

The log command is like a search engine. By default, all history is shown, but greater control can be applied, isolating commits by author and committer, the time changes occurred, patch content, or even the message description.

Dramatically narrow the search time when combined with filters related to a partial or full match of a Git user.name or within a particular time range.

```
$ git log --author [author-name]
$ git log --since [integer].days.ago

```

Searching by a string or regular expression is often the most efficient way of finding history:

```
$ git log -S [string-in-patch]
$ git log -G [regex-pattern-in-patch]
$ git log --grep=[regex-in-message]
```

Filtering by file state, added (A), modified (M), or deleted (D), also narrows what change requires assessment

```
$ git log --diff-filter=[A|M|D]
$ git log --follow --stat --diff-filter=[A|M|D] -- <filename>
```

Revision selection and commit ranges are extremely powerful in narrowing historical output, and is detailed on the Git-SCM.com web site.

```
$ git log --oneline --left-right master..other
$ git log --oneline --left-right master...other
```

----

# License

:octocat: [Frederick Silva](http://fs.mint-license.org) :coffee: === :yum:
