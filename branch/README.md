### branch & conflict lesson

# branch
```
nano work.txt
git status
git add work.txt
git commit -m "work 1"
git commit --amend  #이전 commit 메시지 수정
git log

# 변경사항들을 보여줄때
git log -p

git log --all --graph --oneline
```

# branch 생성
```
2f7ff89 (HEAD -> main, ms, google, apple) work 3

git branch apple
git branch google
git branch ms

nano work.txt #add contents 4
git commit -am "master work 4"

f47dfcd (HEAD -> main) master work 4
2f7ff89 (ms, google, apple) work 3

git checkout apple
```

# branch merge 에서
```
base (branch에서 쪼개질때 공통 출발점)
merge commit
# merge를 위해서 main으로 checkout
git merge apple

git status # 충돌 상태 파악
Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   work.txt

# 편집기로 충돌 내용 수정
# 수정 후 저장, 충돌 수정을 git에 알림
git add work.txt
git status

git commit
```

# 2 way merge, 3 way merge
```
base와 branch 2개를 가지고 비교
```