# Git Alias

### Global Git Config
- ~/.gitconfig
- ~/.config/git/config

```
git config --global user.name
git config --global user.email
```

### Local Git Config
- .git (all repo)

# Adding Aliases
We can easily set up Git aliases to make our Git experience a bit simpler and faster.

```
# .gitconfig
[alias]
    s = status
    l = log

git s
git l

# command
git config --global alias.showmebranches branch
git showmebranches
```

### 인자가 있는 alias 명령
```
[alias]
    cm = commit -m
    a = add

git cm "my new commit!"
git a README.md new.js
```

### online alias repo
https://github.com/GitAlias/gitalias
https://www.durdn.com/blog/2012/11/22/must-have-git-aliases-advanced-examples/
