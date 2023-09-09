# Reflog
HEAD 참조의 이동을 기록 저장
Git keeps a record of when the tips of branches and other refences were updated in the repo.
.git/logs/HEAD
- branch 변경 기록
- checkout 기록

### reflog limitations
reflog는 지역적 (로컬)
reflog는 영구적이지 않음 (90일 기본, 설명 변경 가능)

```
git reflog show HEAD
git reflog show <branch-name>
```

### Reflog References
name@{qualifier}
```
# HEAD가 2번 움직임 전 (브랜치 이동등일 수 있음)
git checkout HEAD@{2}
git diff HEAD@{0} HEAD@{5}

# HEAD의 2번 앞 (커밋)
git checkout HEAD~2
```

### Timed References
```
git reflog master@{one.week.ago}
git checkout bugfix@{2.days.ago}
git diff main@{0} main@{yesterday}
```

### Reflogs Rescue
```
git commit -am "commit1"
git commit -am "commit2"
git log --oneline
git reset --hard <commit1-hash>
git log --oneline
git reflog show main
git checkout <commit1-hash>
git switch -
git reset --hard main@{1}
git log --oneline
git reflog show main
```

rebase를 통하여 commit을 덮어씌운 상황을 복구
```
git commit -am "commit1"
git commit -am "commit2"
git commit -am "commit3"
git commit -am "commit4"
git log --oneline
git rebase -i HEAD~4
# pick -> fixup
# rewriting history
git log --oneline
git rebase -i HEAD~2
# pick -> fixup, reword

#resue
git reflog show main
git reset --hard <target-hash>
git log --oneline
git reflog show main
```