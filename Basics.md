# git pull

```bash
$ git pull origin master
* branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories
```

* To solve it use the next command
```bash
git pull --allow-unrelated-histories origin main
```
* Is goign to appear a vim window to set a commit message
