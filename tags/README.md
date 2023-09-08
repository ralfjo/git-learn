# Tags
�±״� �ð��� � ������ ����Ű�� �󺧰� ����.
�±״� �������� ǥ���ϱ� ���� ��� (v1.1.0, v1.2.0 ...)

# Tags ��ȸ
```
git tag
git tag -l "*beta*"
```

# checkout
branch�� tag�� checkout �ٸ� ���� branch�� ��ġ�� ���Ѵ�, tag�� ��ġ�� �׻� �����ϴ�.

# Tags Ȱ��
```
git diff tag tag
```

# Tag ����
�Ϲ� �±� ���� ���
```
git tag <tagname>
git tag <tagname> <commit_hash>

# ������ �±� �̵� - ����
git tag <tagname> <commit_hash> -f
```
commit �� ���� ��� ��ġ�� �������� tag ����

�ּ� �±� ���� ���
```
git tag -a <tagname>
git show <tagname>
```

# Tag ����
�±� ����
```
git tag -d <tagname>
```

# Tag Push
�߿�: �±� Ǫ��
�±״� �ڵ����� Ǫ�õ��� ����. �ϳ��� �ø��ų� --tags�� Ȱ���Ͽ� �ѹ��� �ø� �� ����
```
git push origin <tagname>
git push origin --tags
```