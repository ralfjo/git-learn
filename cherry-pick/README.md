# git-learn

### cherry-pick
```
# 특정 체크포인트에 변화내용만을 가져와서 적용
# 가져오고 싶은 브랜치로 이동
git cherry-pick 78150ab

# conflict 시 3way merge를 이해하는 것이 중요
# conflict를 해결하고
git cherry-pick --continue
# (--abort는 변경 내용 취소)
```


### rebase
```
# base를 변경
# 이동할 branch 로 이동 후 base 이동할 branch를 선택
git rebase topic

# rebase 시기
# 이동할 checkpoint가 내 컴퓨터에 있을 경우만 (아직 push 전일 경우에만 진행)
# push를 통하여 원격지에 올라갔다면 하면 안됨

# 여러 사람이 작업할 시 다른사람이 먼저 commit이 올라왔을 경우
# 내 저장소에서는 origin/master가 다른 commit으로 보이는데,
# 내가 아직 다른사람에게 공유 (원격 저장소에 push) 안한 상태에서 진행한다.
git merge origin/master  # 버전 정보가 복잡하게 됨
git rebase origin/master # rebase를 통해서 다른사람의 commit 이후로 나의 버전을 이어줌
```

### pull 과 fetch
```
# pull은 원격 저장소의 내용을 가져와서 HEAD를 새로 받은 것으로 이동
# fetch는 원격저장소의 내용은 가져오지만, 현재 HEAD 위치는 그대로
## merge를 통해서 fetch 내용을 적용할 수 있음
```