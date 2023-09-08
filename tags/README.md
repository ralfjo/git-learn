# Tags
태그는 시간의 어떤 지점을 가리키는 라벨과 같다.
태그는 릴리스를 표시하기 위해 사용 (v1.1.0, v1.2.0 ...)

# Tags 조회
```
git tag
git tag -l "*beta*"
```

# checkout
branch와 tag의 checkout 다른 점은 branch는 위치가 변한다, tag는 위치가 항상 동일하다.

# Tags 활용
```
git diff tag tag
```

# Tag 생성
일반 태그 생성 방법
```
git tag <tagname>
git tag <tagname> <commit_hash>

# 강제로 태그 이동 - 지양
git tag <tagname> <commit_hash> -f
```
commit 후 현재 헤드 위치를 기준으로 tag 생성

주석 태그 생성 방법
```
git tag -a <tagname>
git show <tagname>
```

# Tag 삭제
태그 삭제
```
git tag -d <tagname>
```

# Tag Push
중요: 태그 푸시
태그는 자동으로 푸시되지 않음. 하나씩 올리거나 --tags를 활용하여 한번이 올릴 수 있음
```
git push origin <tagname>
git push origin --tags
```