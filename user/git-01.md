# 2# 코드 이관하기

안녕하세요.  
챕터 1의 깃랩 그룹 및 프로젝트가 잘 생성 되었나요?

이번 챕터는 앞에서 생성한 프로젝트로 :star: **코드 이관** :star: 을 해보도록 합시다.


## 1. 코드 이관하기

우선 AWS 사이트에 로그인 합니다.    
:point_right: [AWS 사이트로 이동하기](https://aws.amazon.com/ko/)

콘솔 창에서 개발자도구의 `Codecommit`에 들어갑니다.    
리포지토리에서 코드를 이관할 항목을 골라 들어갑니다.

예시로 `club-atomy`로 들어가보겠습니다.

![Codecommit Repository](https://user-images.githubusercontent.com/54167990/65102741-041ac400-da07-11e9-818e-c64d108b6fd4.PNG)

URL 복제를 누른 후 `HTTPS 복제`를 클릭합니다.

이제 로컬의 터미널 창을 열어서 코드를 작성해보겠습니다.

우선 시작 전에 폴더를 하나 만들고, 폴더 안으로 들어가보겠습니다.

```
user@MZ01-SONDAYEON ~: $ mkdir temp
user@MZ01-SONDAYEON ~: $ cd temp/
user@MZ01-SONDAYEON /temp ~: $
```

폴더 안에 `git clone`을 생성해보겠습니다.

`사용 방법`

```
$ git clone --bare [source-git-url]
```

`사용 예시`
```
user@MZ01-SONDAYEON /temp ~: $ git clone --bare \
https://git-codecommit.ap-northeast-2.amazonaws.com/v1/repos/club-atomy

club-atomy
Cloning into bare repository 'club-atomy.git'...
```
완료된 후, git 파일이 생성되었는지 확인해보겠습니다.

```
user@MZ01-SONDAYEON /temp ~: $ ll

total 0
drwxr-xr-x 10 mz-sdy staff 320 Aug 25 15:37 club-atomy.git
```
:bulb: **TIP 1** : Windows 환경에서는 `dir` 명령어를 사용하여야 합니다.
 
:bulb: **TIP 2**      
소문자 L을 두번 쓰면 (ll) `ls -al`과 같은 의미입니다.  
- **ls 명령어 (list)** : 디렉토리에 있는 내용을 확인할 수 있습니다.   
- **a 옵션 (all)** : 숨겨진 파일이나 디렉토리까지 확인할 수 있습니다.   
- **l 옵션 (long)** : 자세한 내용을 확인할 수 있습니다.( 권한, 소유자 등...)   
 

git clone이 생성된 것을 확인하였으니, 그 안으로 들어가서 작업해보도록 하겠습니다.

`사용 방법`
```
$ cd [cloned-directory]
```
`사용 예시`
```
user@MZ01-SONDAYEON /temp ~: $ cd club-atomy.git
user@MZ01-SONDAYEON /temp/club-atomy.git ~: $
```
깃랩에서 `clone with HTTPS`를 복사합니다.

![clone with HTTPS](https://user-images.githubusercontent.com/54167990/65104734-80b0a100-da0d-11e9-8022-5af325819a8c.PNG)

`사용 방법`
```
$ git remote set-url --push orgin [copy-git-url]
$ git config remote.origin.fetch 'refs/heads/*:refs/heads/*'
$ git --bare fetch -p origin
```

`사용 예시`
```
user@MZ01-SONDAYEON /temp/club-atomy.git ~: $ git remote set-url --push orgin \
https://gitlab.atomyops.com/atomy/atomy-club.git
```
```
user@MZ01-SONDAYEON /temp/club-atomy.git ~: $ git config remote.origin.fetch 'refs/heads/*:refs/heads/*'
```
```
user@MZ01-SONDAYEON /temp/club-atomy.git ~: $ git --bare fetch -p origin
```


이제 push 해보도록 하겠습니다.

`사용 방법`
```
$ git push --mirror -f 

Username for 'https://gitlab.atomyops.com/atomy/atomy-club.git' : [your-user-name]
Password for 'https://[user-name]@gitlab.atomyops.com/atomy/atomy-club.git' : [your-password]
```
`사용 예시`
```
user@MZ01-SONDAYEON /temp/club-atomy.git ~: $ git push --mirror -f 
Username for 'https://gitlab.atomyops.com/atomy/atomy-club.git' : sondayeon
Password for 'https://sondayeon@gitlab.atomyops.com/atomy/atomy-club.git' : 
Enumerating objects: 1530, done.
.
.
```

push 하게 되면 다음과 같이 코드가 폴더로 이관되는 것을 확인 할 수 있습니다.
![코드 이관 완료](https://user-images.githubusercontent.com/54167990/65120100-135e3980-da28-11e9-8796-1c5270a8e8c1.PNG)

:cd: **참고 영상**
<iframe src="https://drive.google.com/file/d/1bJPgj710-imWvvUiKMpZUV0BkdK72F2m/preview" width="640" height="480"></iframe>

---

깃랩으로 코드를 이관하는 단계를 완료하셨습니다!   :clap:  :clap:  

다음 단계에서는 `자라 이슈 트래커와 깃랩 연동하기`에 대해 배워보겠습니다.  
