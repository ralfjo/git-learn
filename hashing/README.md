# .git folder

# Config
```
git config --local user.name
git config --local user.email
```

# Refs folder
refs/heads
- branch hash ������ ������ ����
- git log --oneline�� �ؽ� ������ ��

# HEAD
HEAD���� ���� hash ������ ����Ŵ -> refs/heads/<branch>

# Object folder
������� ��� �����͸� ����
��� Ŀ�� ����, ����Ʈ��, Ŀ�� ����, ���� ������� ���� ��ü�� ���������� ����
��ȣȭ�ǰ� ����� ���̳ʸ� ���ϵ��� ����

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
�������� �����ϰ� �ش��ϴ� hash key�� ��ȯ

### Git �����͸� �����ϱ� ���� ���
```
git hash-object <file>
git hash-object <file> -w
```
git hash-object - data�� .git/objects directory�� �����ϰ� SHA-1 hash�� ����

```
echo 'hello' | git hash-object --stdin
# -w �ɼ��� ������ �����͸� ����
# .git/objects �� ���� (hash�� ���丮/���ϸ����� ���)
echo 'hello' | git hash-object --stdin -w
ce013625030ba8dba906f756967f9e9ca394464a
```

### Git �����͸� ���������� ���
git cat-file -p <object-hash>
```
git cat-file -p ce013625030ba8dba906f756967f9e9ca394464a

# type Ȯ��
git cat-file -t <object-hash>
```

# Blobs
���� ������ �����ϴ� ��ü�̸�, hash ���� ����
Git blobs(binary large object) are the object type Git uses to store the contents of files in a given repository. Blobs don't even include the filenames of each file or any other data. They just store the contents of a file!

# Trees
���丮, ���ϻ����� ����, ������ ����
Trees are Git objects used to store the contents of a directory. Each tree contains pointers that can refer to blobs and to ther trees.
```
git cat-file -p main^{tree}
```

# Commits
Ŀ���� �ϰԵǸ� Git�� commit ��ü�� �����Ͽ� ����
Commit objects combine a tree object along with information abount the context that led to the current tree. Commits store a reference to parent commit(s), the author, the commiter, and of course the commit message!