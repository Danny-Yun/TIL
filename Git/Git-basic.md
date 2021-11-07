# Git 사용법 기초

<br>

![git-basic](https://user-images.githubusercontent.com/86466976/140633037-9d4e43d2-d806-435a-9e37-9a1cd2c9f2b3.png)

## Remote(깃헙 저장소)에서 Local로 가져오기
+ Clone - 최초, 로컬에 파일이 없는 경우   
```   
$ cd [경로설정]
$ git clone [저장소주소]
```
> 특정 브랜치 클론
```
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
```

<br>

+  git add한걸 초기화
```
$ git reset
```

<br>

+  강제 푸시
```
$ git push -u origin +master
```

<br>

+  원격 저장소 조회
```
$ git remote -v
```
> 원격 저장소 삭제
```
$ git remote remove [원격저장소명]
```

<br/>

## 브랜치 관리
+  모든 브랜치 목록 조회
```
$ git branch -a
```
> 원격 브랜치 목록 조회
```
$ git branch -r
```
> 로컬 브랜치 목록 조회
```
$ git branch
```

<br>

+  브랜치 이동
```
$ git checkout [이동할 브랜치명]
```

<br>

+  브랜치 병합
```
$ git checkout [병합시킬 브랜치명]
$ git merge [작업한 브랜치명]
```
