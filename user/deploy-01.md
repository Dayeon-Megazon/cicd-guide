# [4-2] 개발 서버 배포하기

안녕하세요.               
챕터 1의 런타임 및 환경 변수 설정이 잘 되었나요?

이번 챕터는 :star: **개발 서버 배포하기**:star:를 해보도록 합시다.

---
## 1# 개발 서버 런타임 확인하기

우선 CICD 사이트에 접속합니다.     
현재 `atomy` 프로젝트로 실습하고 있으므로, atomy의 CICD 사이트로 접속하겠습니다.

:point_right: [ATOMY CICD 사이트로 접속하기](http://cicd.atomyops.com)

> 프로젝트에 따라 CICD 사이트가 다르므로, 자신의 프로젝트에 맞는 사이트로 접속하시길 바랍니다.

사이트에 접속하여  프로젝트에 들어간 후, `DEV-Admin`을 클릭합니다. 

`DEV-Admin`의 `배포`탭에 들어가서 `새 배포` 버튼을 클릭합니다.

![배포하기](https://user-images.githubusercontent.com/54167990/65673990-cd881d80-e086-11e9-9f75-01d0d0f79e64.PNG)

Images 창이 나오면 `배포하기`를 클릭합니다.

`Are you sure?`이라는 창에서 `진행`을 클릭합니다.

`Dev-Admin`의 `런타임 및 환경설정` 탭에 들어가서 런타임 중인 인스턴스를 확인할 수 있습니다.

![런타임](https://user-images.githubusercontent.com/54167990/65733597-76c42780-e10a-11e9-920e-e1677e10efdd.png)

런타임을 확인 후에, 사이트에 들어가 보겠습니다.  
예시) https://admin.comm.atomydev.com

![웹사이트](https://user-images.githubusercontent.com/54167990/65733598-775cbe00-e10a-11e9-8b0c-5e73c0352b06.png)

다음과 같이 웹 화면이 뜨면 성공적으로 배포를 마쳤습니다! :smile:


## 2# 컨테이너 접속하기

`DEV-Admin`에서 `런타임 및 환경설정`의 실행중인 인스턴스를 클릭합니다.

![인스턴스](https://user-images.githubusercontent.com/54167990/65737751-85b2d600-e11a-11e9-80ca-2358ceb39242.png)

`컨테이너 접속` 탭에 들어갑니다.

![컨테이너](https://user-images.githubusercontent.com/54167990/65737875-e2ae8c00-e11a-11e9-8e6b-827a54f3f683.png)

`$ ls -l` 명령어를 사용하여, 인스턴스 안의 파일들을 볼 수 있습니다.

컨테이너가 잘 구동되는 것을 보아 개발 서버가 성공적으로 배포가 ! :smile:


---
:cd: 참고 영상

<iframe src="https://drive.google.com/file/d/1nC3gm5hFEOTNlxrhWFRgkcd7sG4I8J73/preview" width="640" height="480"></iframe>
---

개발 서버 배포하기 단계를 완료하셨습니다! :clap: :clap:

다음 단계에서는 `프로덕션 서버 하기`에 대해 배워보겠습니다.
