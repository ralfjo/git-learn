### branch & conflict lesson

# branch
```
nano work.txt
git status
git add work.txt
git commit -m "work 1"
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


```
