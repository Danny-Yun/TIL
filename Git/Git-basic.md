# Git 사용법 기초

<br>

![git-basic](https://user-images.githubusercontent.com/86466976/140633037-9d4e43d2-d806-435a-9e37-9a1cd2c9f2b3.png)

<br>

## Remote(깃헙 저장소)에서 Local로 가져오기
+ Clone - 최초, 로컬에 파일이 없는 경우
$ cd [경로설정]
$ git clone [저장소주소]
> 특정 브랜치 클론
$ git clone -b [브랜치이름] [저장소주소] 

+ Pull - 로컬에 기존 파일이 있는 경우
$ cd [경로설정]
$ git fetch
$ git pull [원격저장소명] [브랜치명]

