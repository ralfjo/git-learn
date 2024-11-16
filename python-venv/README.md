### 가상환경
```
python -m venv p1env
.\p1env\Scripts\activate

.\p1env\Scripts\activate : 이 시스템에서 스크립트를 실행할 수 없으므로 C:\...\github\Project1\p1env\Scripts\Activate.ps1 파일을 로드할 수 없습니다. 자세한 내용은 about_Execution_Policies(https://go.microsoft.com/fwlink/?LinkID=135170)를 참조하십시오.
위치 줄:1 문자:1
+ .\p1env\Scripts\activate
+ ~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : 보안 오류: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

Set-ExecutionPolicy RemoteSigned

.\p1env\Scripts\activate
```

### 가상환경 사용
```
#가상환경 설정
python -m venv p1env
python -m venv p1env --system-site-packages

# 가상환경 activate
.\p1env\Scripts\activate

# 가상환경 설정 패키지 freeze
pip freeze > requirements.txt
pip install -r requirements.txt

# 가상환경 pip 설치 리스트 (local옵션 차이)
pip list
pip list --local

# 가상환경 deactivate
deactivate
```
