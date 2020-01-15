# Git Cheet Sheet

## Create Repositories

```bash
$ git init [project name]
$ git clone [my_url]
```

## Observe Repositories

```bash
$ git status
$ git diff
$ git diff --cached
$ git diff HEAD
$ git diff commit1 commit2
$ git blame [file]
$ git show [commit]:[file]
$ git log
$ git log -p [file/directory]
```

## Working with Branches

```bash
$ git branch
$ git branch -av
$ git checkout my_branch
$ git branch new_branch
$ git branch -d my_branch
$ git checkout branch_b     $ git merge branch_a
$ git tag my_tag
```

## Make a change

```bash
$ git add [file]
$ git add
$ git commit -m "commit message"
$ git commit -am "commit message"
$ git reset [file]
$ git reset --hard
```

## Synchronize
```bash
$ git fetch
$ git pull
$ git pull --rebase
$ git push
```


---
## Refer to
[JRebel Labs](https://www.jrebel.com/blog/git-cheat-sheet)
[Git Cheat Sheet - Official](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)
