# Reflog
HEAD ������ �̵��� ��� ����
Git keeps a record of when the tips of branches and other refences were updated in the repo.
.git/logs/HEAD
- branch ���� ���
- checkout ���

### reflog limitations
reflog�� ������ (����)
reflog�� ���������� ���� (90�� �⺻, ���� ���� ����)

```
git reflog show HEAD
git reflog show <branch-name>
```

### Reflog References
name@{qualifier}
```
# HEAD�� 2�� ������ �� (�귣ġ �̵����� �� ����)
git checkout HEAD@{2}
git diff HEAD@{0} HEAD@{5}

# HEAD�� 2�� �� (Ŀ��)
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

rebase�� ���Ͽ� commit�� ����� ��Ȳ�� ����
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