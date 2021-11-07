# Git 사용법 기초

<br>

![git-basic](https://user-images.githubusercontent.com/86466976/140633037-9d4e43d2-d806-435a-9e37-9a1cd2c9f2b3.png)

## Remote(깃헙 저장소)에서 Local로 가져오기
+ Clone - 최초, 로컬에 파일이 없는 경우   
```   
$ cd [경로설정]
$ git clone [저장소주소]

//특정 브랜치 클론시
$ git clone -b [브랜치이름] [저장소주소]
```

<br>

+ Pull - 로컬에 기존 파일이 있는 경우     
```
$ cd [경로설정]
$ git fetch
$ git pull [원격저장소명] [브랜치명]
```

<br/>

## Local에서 Remote(깃헙 저장소)로 업로드
```
$ cd [경로설정]
$ git init
$ git remote add [원격저장소명] [저장소주소] 
$ git add .(전체) or $ git add [파일명]
$ git commit -m [커밋메시지]
$ git push [원격저장소명] [브랜치명]
```

<br>

+ 깃의 현재 상태 조회
```
$ git status
$ git status -s   //짧게 조회
```

<br>

+  git add한걸 초기화
```
$ git reset
```

<br>

+  변경사항 확인하기
```
$ git diff   //(커밋 전)변경사항 모두 확인
$ git diff [파일명]   //특정 파일 변경사항 확인
$ git diff --cached   //(커밋 후) 변경사항 확인
```

<br>

+  강제 푸시
```
$ git push -u origin +master
```

<br>

+  원격 저장소 관리
```
$ git remote -v  //원격 저장소 조회
$ git remote add [원격저장소명] [저장소주소]   //원격 저장소 추가
$ git remote remove [원격저장소명]   //원격 저장소 삭제
```

<br/>

## 브랜치 관리
+  브랜치 목록 조회
```
$ git branch -a   //모든 브랜치 목록 조회
$ git branch -r   //원격 브랜치 목록 조회
$ git branch   //로컬 브랜치 목록 조회
```

<br>

+  브랜치 생성
```
$ git branch [새로운 브랜치명]
```

<br>

+  브랜치 변경
```
$ git checkout [이동할 브랜치명]
```

<br>

+  브랜치 병합
```
$ git checkout [병합시킬 브랜치명]
$ git merge [작업한 브랜치명]
```

<br>

+  브랜치 이름 변경
```
$ git branch -m {기존 이름} {변경할 이름}

만약 현재 변경할 브랜치에 체크아웃한 상태라면, 아래의 명령으로도 가능하다.
$ git branch -m {변경할 이름}
```

<br>

+  원격 저장소의 브랜치 삭제
```
$ git push origin --delete {브랜치명}
```

+  로컬 브랜치 삭제
```
$ git branch -d {브랜치명}
```
