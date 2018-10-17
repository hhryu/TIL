## Git bash로 프로젝트 업로드 하기.

- config 세팅.

```bash
git config --global user.name "GITHUB_ID"		#ID 설정
git config --global user.name "GITUB_EMAIL"		#Email 설정
```

- 로컬 저장소 생성.

```bash
mkdir ~/MyProject			#저장소 생성, ~/는 최상위
cd ~/MyProject				#해당 디렉토리로 이동
git init					#git 초기화, 해당 디렉토리가 git repo라고 
```

- commit 대상 확인. 

```bash
git status				#로컬 저장소 상태 확인.
```

- commit 파일 추가.

```bash
git add 파일명				#하나의 파일을 커밋대상으로 추가
git add .				  #해당 디렉토리의 모든 파일을 커밋대상으로 추가
git commit -m "Add 파일명" #커밋
```

- 로컬 저장소와 Github 저장소 연결.

```bash
#해당 경로 github 저장소를 origin으로 지정.
git remote add origin https://github.com/계정ID/myproject.git

#origin 경로 변경.
git remote set-url origin https://github.com/계정ID/myproject.git
```

- push

```bash
git remote -v					#remote 확인
git push origin master			#master로 push.
```

