# rebase
git log�� ���ۼ�
�����丮�� ������Ʈ �ٽþ��Եȴ�.
```
git switch feature
git rebase main
```
main branch�� ���� ���ۼ��ϴ� ���� �ƴ϶�, feature branch�� commit�� ���ۼ��ϴ� ����.

# why rebase?
�۾��� �����丮 ������ ���� ���ش�.

# WARNING!
�̹� ������ Ŀ���� �����̽� �ϸ� �ȵ�. �۾��� �귣ġ�� �����̽�.
Never rebase commits that have been shared with others. If you have already pushed commits up to Github...DO NOT rebase them unless you are positive no one on the team is using those commits.