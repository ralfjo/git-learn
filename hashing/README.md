# .git folder

# Config
```
git config --local user.name
git config --local user.email
```

# Refs folder
refs/heads
- branch hash 정보를 가지고 있음
- git log --oneline의 해시 정보를 비교

# HEAD
HEAD에는 현재 hash 정보를 가르킴 -> refs/heads/<branch>

# Object folder
저장소의 모든 데이터를 저장
모든 커밋 파일, 히소트리, 커밋 정보, 파일 내용등을 깃이 전체를 스냅샷으로 저장
암호화되고 압축된 바이너리 파일들이 있음

4 types of Git objects
- commit
- tree
- blob
- annotated tag

# Hashing Functions
### cryptographic hash functions
1. One-way function which is infeasible to invert
2. Small change in input yields large change in the output
3. Deterministic - same input yields same output
4. Unlikely to find 2 outputs with same value

### SHA-1
Git uses a hashing function called SHA-1
SHA-1 always generates 40-digit hexadecimal numbers
The commit hashes we've seen a million times are the output of SHA-1

# Git Database
Git is a Key-value data store.
컨텐츠를 저장하고 해당하는 hash key를 반환

### Git 데이터를 저장하기 위한 명령
```
git hash-object <file>
git hash-object <file> -w
```
git hash-object - data를 .git/objects directory에 저장하고 SHA-1 hash를 리턴

```
echo 'hello' | git hash-object --stdin
# -w 옵션은 실제로 데이터를 저장
# .git/objects 에 생성 (hash를 디렉토리/파일명으로 사용)
echo 'hello' | git hash-object --stdin -w
ce013625030ba8dba906f756967f9e9ca394464a
```

### Git 데이터를 꺼내기위한 명령
git cat-file -p <object-hash>
```
git cat-file -p ce013625030ba8dba906f756967f9e9ca394464a

# type 확인
git cat-file -t <object-hash>
```

# Blobs
파일 내용을 저장하는 객체이며, hash 값을 가짐
Git blobs(binary large object) are the object type Git uses to store the contents of files in a given repository. Blobs don't even include the filenames of each file or any other data. They just store the contents of a file!

# Trees
디렉토리, 파일사이의 관계, 구조를 정의
Trees are Git objects used to store the contents of a directory. Each tree contains pointers that can refer to blobs and to ther trees.
```
git cat-file -p main^{tree}
```

# Commits
커밋을 하게되면 Git은 commit 객체를 생성하여 저장
Commit objects combine a tree object along with information abount the context that led to the current tree. Commits store a reference to parent commit(s), the author, the commiter, and of course the commit message!