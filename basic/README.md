### config environment

# ssh-key 등록
```
cat ~/.ssh/id_rsa.pub
ssh-keygen
cat ~/.ssh/id_rsa.pub
# copy text
# gitlab 계정정보 - ssh keys에 등록
```

1. Git 설치
2. Git - name & email 설정
```
git config --global user.name "username"
git config --global user.email "useremail"
```
3. Git repo 설정
```
git init
```
3-1. Git status
```
git status
```
3-2. Git log
```
git log
git log --oneline
```
4. Git add file
```
git add filename
git add .
```
5. Git commit
```
git commit -m "message"
git commit -a -m "message"
```
6. Git editor 설정
```
git config --global core.editor "code --wait"
git config --global core.editor "vim"
```
7. Git branch
```
git branch "branch name" ##branch 생성
# branch를 삭제하기 위해서는 다른 branch로 이동해야 함
# branch 삭제 전 merge를 진행하라고 하며, 강제로 삭제할 수 있음
git branch -d "branch name" ## branch 삭제
git branch -D "branch name" ## branch 강제삭제
# branch 이름을 변경할 수 있으며, 이름 변경을 위해서는 해당 branch로 switch해야 함
git branch -m "branch-name"
```
7-1. Git switch
```
git switch "branch-name"
git switch -c "branch-name" ##branch생성 후 바로 이동
# branch 이동 시 commit하지 않는 데이터는 삭제될 수 있음, 이동전 commit 필요
```
7-2. Git checkout
```
git checkout "branch-name" ##switch명령과 비슷한 기능, switch명령을 선호
```
8. Git merge
```
## fast forward merge
git merge <branch-name>
```
9. Git diff
```
git diff
git diff HEAD
git diff --staged
git diff --cacheds
git diff <branch>..<branch>
git diff commit1..commit2
git diff HEAD HEAD~1
```
10. Git stash
```
git stash
git stash pop  #빼고 삭제
git stash apply  #빼고 그대로 유지
git stash apply stash@{2}
git stash list
git stash drop stash@{2}
git stash clear
```
11. Git checkout
```
git checkout <commit-hash>  ##detached head
git switch master
## redo
git checkout <commit-hash>
git switch -c <commit-redo>
git switch master
## 이전 커밋
git checkout HEAD~1
git checkout HEAD~2
git checkout HEAD~3
git switch -
```