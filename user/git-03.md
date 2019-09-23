# [1-4] 머지 리퀘스트 사용하기

안녕하세요.  
챕터 3의 자라 이슈 트래커와 깃랩이 잘 연동 되었나요?

이번 챕터는 앞에서 생성한 프로젝트로 :star: **머지 리퀘스트** :star: 를 사용해 봅시다.

---

## 1# 브랜치 생성하기

우선 GitLab의 프로젝트에서 `저장소`의 `브랜치` 탭에 들어갑니다.   
`새 브랜치` 버튼을 클릭하여 새로운 브랜치를 생성해봅시다.

브랜치 이름은 챕터 3에서 실습했던, `이슈 링크 번호`로 하겠습니다.

![브랜치 생성](https://user-images.githubusercontent.com/54167990/65210979-1ca6df00-dad8-11e9-9a8e-d44759f2a21b.png)

작성 후 , `Create branch` 버튼을 눌러 완료합니다.

---

## 2# 프로젝트 코드 Clone 하기

이제 GitLab의 코드를 받아서 열어보겠습니다.

챕터 2번과 내용은 동일하지만, 다시 한 번 진행해보겠습니다.         
:point_right: [챕터 2번으로 돌아가기](https://megazonedsg.github.io/cicd-guide/#/user/git-01)

프로젝트의 `Clone` 버튼을 눌러 `Clone with HTTPS`를 복사합니다.

![HTTPS 복사](https://user-images.githubusercontent.com/54167990/65120624-e3fbfc80-da28-11e9-9c30-6e27d6b3b6de.PNG)

새로운 폴더 또는 원래 있던 폴더에 git을 clone 합니다.            
예시로 원래 있던 폴더로 진행하겠습니다.  
> 새로운 폴더를 만든다면 `$ mkdir [directory-name]` 명령어를 사용하시면 됩니다.

`사용 방법`
```
$ cd [directory]
$ git clone [project-clone-with-HTTPS]
```

`사용 예시`
```
user@MZ01-SONDAYEON ~: $ cd IdeaProjects/
user@MZ01-SONDAYEON /IdeaProjects ~: $ git clone \
https://gitlab.atomyops.com/atomy/atomy-club.git

club-atomy
Cloning into bare repository `club-atomy.git`...
.
.
```

Windows의 경우 `dir` 명령을,                
Mac 또는 Linux 환경에서는 `ll` 또는 `ls -al` 명령을 사용하여       
폴더 안의 디렉토리에 있는 git 이름을 확인해봅니다.

```
user@MZ01-SONDAYEON /IdeaProjects ~: $ ll

total 0
drwxr-xr-x 10 mz-sdy staff 320 Aug 25 15:37 club-atomy.git
```

git 이름을 확인하였으면, 그 git에 들어간 후 `push` 합니다.

`사용 예시`
```
$ cd [your-git-name]
$ git push --mirror -f
```

`사용 방법`
```
user@MZ01-SONDAYEON /IdeaProjects ~: $ cd club-atomy.git
user@MZ01-SONDAYEON /IdeaProjects/club-atomy.git ~:$ git push --mirror -f

Enumerating objects: 9849, done.
.
.
```
---

## 3# 플랫폼에서 Git Commit

이제 위에서 clone 한 `atomy-club`을 `인텔리제이`에서 열어보겠습니다.      
> 다른 플랫폼으로 사용하여도 상관없습니다.

플랫폼에서 연 후, 터미널을 열어서 작업을 시작해보겠습니다.

![git fetch](https://user-images.githubusercontent.com/54167990/65216131-e6bf2600-daea-11e9-9f20-0e3f70a6b91d.png)

터미널에서 `$ git fetch` 라고 명령하면, 아래에 새로운 브런치 목록을 보여줍니다.     
저희가 위의 1번에서 생성한 브런치가 생성된 것을 확인할 수 있습니다.

![git checkout](https://user-images.githubusercontent.com/54167990/65216510-1ae71680-daec-11e9-9aa8-9f860554390d.png)

`$ git checkout [branch-name]`을 사용하여, brunch를 바꿔줍니다.  
여기서는 위에서 만든 브런치를 사용하였습니다.

그 후 새로운 파일을 하나 만들어보겠습니다.  
![new file](https://user-images.githubusercontent.com/54167990/65216760-f7709b80-daec-11e9-8d27-c968acea91ad.png)

루트에서 우클릭하여 새로운 파일을 생성해 보겠습니다.    
파일 이름은 `sample.text` 로 만들고, 내용은 `sample!!!` 이라고 작성해보겠습니다.

작성 후, `git commit`을 해보겠습니다.  
위에 있는 초록색 체크 아이콘을 눌러주면 다음과 같이 commit 창이 나오게 됩니다.

![commit](https://user-images.githubusercontent.com/54167990/65217667-af06ad00-daef-11e9-9553-c95b2d366e29.PNG)

commit 메세지는 이슈 번호를 사용하여 적겠습니다.         
예시로 `[ATOMYCWS-1712] create sample.text` 라고 적은 후에, `Commit and Push` 을 눌러서 commit 합니다.

![push](https://user-images.githubusercontent.com/54167990/65219510-a87a3480-daf3-11e9-8091-07de2f9fbe4b.PNG)

`Push` 버튼을 클릭합니다.

---

## 4# 머지 리퀘스트 생성하기
   
깃랩 프로젝트로 돌아와서 `머지 리퀘스트(MR)` 탭으로 들어옵니다.

![머지 리퀘스트 만들기](https://user-images.githubusercontent.com/54167990/65219513-a9ab6180-daf3-11e9-800f-f8e7e36f752f.PNG)

`머지 리퀘스트 만들기` 버튼을 눌러 머지 리퀘스트를 만듭니다.

![머지 생성](https://user-images.githubusercontent.com/54167990/65219516-ab752500-daf3-11e9-8b35-a6959afc659a.PNG)

제목은 위에서 Commit 메세지로 작성한 내용과 동일하게 생성됩니다.   
Source branch는 새로 만든 브런치를 적용하며, 브랜치 아래의 버튼을 모두 눌러 활성화 시킵니다.     
`Submit 머지 리퀘스트` 버튼을 눌러 완료합니다.


다시 지라로 돌아가 보겠습니다.      
지라의 이슈로 돌아가서 확인해보면 `merge`에 관련된 댓글이 생성된 것을 확인할 수 있습니다.

![머지 확인](https://user-images.githubusercontent.com/54167990/65220117-fb082080-daf4-11e9-9543-0352bf7b5898.PNG)

---

## 5# 깃랩에서 Merge 하기

다시 플랫폼으로 돌아와서 sample.text 파일의 내용을 수정해보겠습니다.      
`sample!!`이라는 내용을 아랫 줄에 추가하고 `Commit and Push` 해보겠습니다.   

![다시 commit하기](https://user-images.githubusercontent.com/54167990/65221777-a8306800-daf8-11e9-8816-5cf36824e4e2.png)


깃랩의 프로젝트로 돌아가서 `머지 리퀘스트`로 돌아갑니다.   
아래 탭의 `commits`를 확인해보면 한 개 더 늘어난 것을 확인할 수 있습니다.

![Commit](https://user-images.githubusercontent.com/54167990/65221184-77036800-daf7-11e9-97b9-9a1c2719e0fa.PNG)

이제 가운데에 있는 `Merge` 버튼을 눌러 머지를 시작해보겠습니다.

![Merge](https://user-images.githubusercontent.com/54167990/65221187-78349500-daf7-11e9-8af1-94fbbd46ebf5.PNG)

머지가 완료된 것을 확인할 수 있습니다.

---

:cd: **참고 영상**  
<iframe src="https://drive.google.com/file/d/1qOnIUSQSjMIdCPvXnQQvuJdnHYmkHAeC/preview" width="640" height="480"></iframe>

---

머지 리퀘스트를 사용하는 단계를 완료하셨습니다!   :clap:  :clap:  

다음은 새로운 챕터인 `CD 설정`에서 `서비스 구성`을 살펴보겠습니다.  
