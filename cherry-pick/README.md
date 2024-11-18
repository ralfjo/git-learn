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
```
