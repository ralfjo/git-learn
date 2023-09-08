# rebase
git log를 재작성
히스토리를 업데이트 다시쓰게된다.
```
git switch feature
git rebase main
```
main branch를 포함 재작성하는 것이 아니라, feature branch의 commit을 재작성하는 것임.

# why rebase?
작업의 히스토리 추적을 쉽게 해준다.

# WARNING!
이미 공유한 커밋을 리베이스 하면 안됨. 작업한 브랜치만 리베이스.
Never rebase commits that have been shared with others. If you have already pushed commits up to Github...DO NOT rebase them unless you are positive no one on the team is using those commits.