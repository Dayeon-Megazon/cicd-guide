# [4-2] 개발 서버 배포하기

안녕하세요.               
챕터 1의 런타임 및 환경 변수 설정이 잘 되었나요?

이번 챕터는 :star: **개발 서버 배포하기**:star:를 해보도록 합시다.

---
## 1# 호스트 확인하기

`admin.comm.atomydev.com`의 IP주소를 확인하겠습니다.

터미널을 열어 다음과 같이 적어 확인합니다.

```
C:\Users\user>nslookup admin.comm.atomydev.com
서버:    fortinet-public-dns-53.fortinet.com
Address:  208.91.112.53

권한 없는 응답:
이름:    admin.comm.atomydev.com
Addresses:  52.78.122.33
          13.124.46.182
```

:bulb: **TIP**    
Linux 나 Mac OS의 경우에는 `dig` 명령어를 사용합니다.

```
MZO1-SONDAYEON ~ : $ dig admin.comm.atomydev.com

.
.
;; ANSWER SECTION:
admin.comm.atomydev.com. 60     IN     A     52.78.122.33
admin.comm.atomydev.com. 60     IN     A     13.124.46.182
.
.
```

## 2. 컨테이너 접속하기

`DEV-Admin`에서 `런타임 및 환경설정`의 실행중인 인스턴스를 클릭합니다.

![인스턴스](https://user-images.githubusercontent.com/54167990/65737751-85b2d600-e11a-11e9-80ca-2358ceb39242.png)

`컨테이너 접속` 탭에 들어갑니다.

![컨테이너](https://user-images.githubusercontent.com/54167990/65737875-e2ae8c00-e11a-11e9-8e6b-827a54f3f683.png)

접속하여 `$ ls -l` 명령어를 사용하여, 인스턴스 안의 파일들을 볼 수 있습니다.

---
:cd: 참고 영상

<iframe src="https://drive.google.com/file/d/1nC3gm5hFEOTNlxrhWFRgkcd7sG4I8J73/preview" width="640" height="480"></iframe>
---

개발 서버 배포하기 단계를 완료하셨습니다! :clap: :clap:

다음 단계에서는 `프로덕션 서버 하기`에 대해 배워보겠습니다.
