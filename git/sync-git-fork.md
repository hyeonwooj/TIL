## How to Sync your fork with upstream

1. git remote add

```bash
$ git remote -v
$ git remote add upstream {add url of the upstream}
$ git remote -v
```

2. git fetch

```bash
$ git fetch upstream
```

3. git merge

```bash
$ git merge upstream/master
```

4. git push

```bash
$ git push origin master
```