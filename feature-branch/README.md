### feature branch
```
# user1
git switch -c navbar
git status
git add index.html
git commit -m "add broken navbar"
git remote -v
git push origin navbar

# user2
git branch
git pull origin main
git switch -c pricing-table
git status
git add index.html
git commit -m "add container to index"
git status
git add index.html
git acommit -m "add pricing table"
git push origin pricing-table

git status
git fetch origin
git branch -r
git checkout origin/navbar
git switch -
git branch 
git switch navbar
git status
git add index.html
git commit -m "fix navbar bug"
git push origin navbar
git switch pricing-table

# user1
git pull origin navbar
git log --oneline

# user2
git switch main
git pull origin main
git merge pricing-table
git status
git push origin main

# user1
git switch main
git pull origin main
```

### Pull request
```
git pull origin main
git switch main
git branch -D navbar
git branch
git pull origin main
```

conflict
```
git fetch origin
git switch new-heading
git checkout -b new-heading origin/new-heading
git merge main
git switch main
git pull origin main
git switch new-heading
git merge main
git add index.html
git commit -m "resolve confict"
git status
git switch main
git merge --no-ff new-heading
git push origin main
```
