# Git

## Commit message

The __title__ of the commit message should be a one line short phrase, that summarizes the change. Follow "Verb-Object" form. Strip away tenses of the verb, or any decoration. The simpler the better.

If there's a issue tracker, the issue name can be referenced in the commit message.

The __body__ of the commit is where you expand the details. It's not always necessary.

```
Add git.md (#24)

* add notes on commit message
* add list of commands
```

Write like Hemingway.

## Commands

`git init`: Init a git repo.

`git add -A`: Add all files.

`git commit -m <your commit title>`: Make a commit, and enter a title.

`git commit -am <your commit title>`: Add all _changes_ to files already tracked by git, make a commit, and enter a title.

`git status`: Check repo status: which branch it's on, changed files, untracked files.

`git diff`: Check line-by-line changes of tracked files. In this view, press `u` to scroll up, `d` to scroll down, and `ZZ` to exit.

`git stash`: Temporarily "stash away" your current, not-staged changes. The repo goes back to its last commit. This functionality is useful for, e.g. when you are in the middle of making local changes, and the upstream has new commits.

`git stash apply`: Restore the stashed away changes back to the repo.

<!-- TODO: branching, resolving a conflict, tagging? -->