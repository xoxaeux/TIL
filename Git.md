- git config (최초 1회 실행)

```
// git commit에 사용될 username
git config --global user.name "your_name"
 
// git commit에 사용될 email
git config --global user.email "your_email@example.com"
 
// 설정한 내용을 확인할 수 있다.
git config --list
```

- git init

```bash
// 로컬저장소로 설정할 프로젝트 위치로 이동한다.
cd C:/dev/workspace/eom2017
 
// 로컬저장소로 설정한다.
// (master) 브랜치로 보이면 성공한 것이다.
git init
 
// 만약 init을 취소하려면 아래의 명령어를 입력한다.
rm -r .git
```

- git remote

```bash
// Github 원격저장소와 연결한다.
git remote add origin [자신의 Github 원격저장소 주소]
 
// 연결된 원격저장소 확인한다.
git remote -v

// 연결된 원격저장소와 연결 해제
git remote remove origin
```

- git add : 파일을 준비영역(Staging Area)으로 옮긴다. (GitHub와 연동하려면 **git remote**로 원격 저장소와 연결해야 함)

```bash
// a.html 파일만 추가
git add a.html
 
// 워킹 디렉터리 내 모든 파일을 추가
git add .
 
// 명령 프롬프트에서 상호작용하면서 추가 (나갈땐 q를 입력)
git add -i
 
// 진행중인 파일일 경우, Staging Area에서 워킹 디렉터리로 옮겨온다. 
$git rm --cached a.html
$git rm -r --cached .
```

- git commit

```bash
// 에디터가 출력되고, 에디터에서 커밋 메시지 입력 후 저장하면 커밋됨
git commit
 
// 간단한 커밋 메시지를 입력후 커밋
git commit -m "커밋 메시지"
 
// Staging Area에 들어간 파일에 대해서만 (워킹 디렉터리는 적용 X)
git commit -a -m "커밋 메시지"
```

- git push

```bash
// 원격저장소에 저장한다. (master에는 branch 이름)
git push -u origin (master)
 
// 에러 - ! [rejected] master -> master (fetch first)
// 이미 변경된 파일이 원격저장소에 있을경우 발생
git pull origin (master) 
 
// 에러 - ! [rejected] master -> master (non-fast-forward)
git push origin +master
```

- git log

```bash
// 커밋 이력 상세조회
git log 
 
// 커밋 이력중 커밋ID, 타이틀 메시지만 조회
git log --oneline
 
// 모든 브랜치 커밋 이력 조회
git log --oneline --decorate --graph --all
 
// 특정 파일의 변경 커밋 조회
git log -- a.html
```

- git 상태보기

```bash
// 로컬저장소의 현재 상태보여줌
git status

```

- git branch

```bash
// branch 상태보기
git branch

// branch 변경 (-b 를 넣으면, 새로운 branch를 만듬)
git checkout -b <branch>
git switch <branch>
```
