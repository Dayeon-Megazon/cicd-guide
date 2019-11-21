# [4-3] 프로덕션 서버 배포하기

안녕하세요.             
챕터 2의 개발 서버 배포가 잘 되었나요?

이번 챕터는 :star: 프로적션 서버 배포하기 :star:를 해보도록 합시다.

---

## 1# 프로덕션 서버 런타임 확인하기

우선 CICD 사이트에 접속합니다.     
현재 `atomy` 프로젝트로 실습하고 있으므로, atomy의 CICD 사이트로 접속하겠습니다.

:point_right: [ATOMY CICD 사이트로 접속하기](http://cicd.atomyops.com)

> 프로젝트에 따라 CICD 사이트가 다르므로, 자신의 프로젝트에 맞는 사이트로 접속하시길 바랍니다.

사이트에 접속하여  프로젝트에 들어간 후, `PROD-Admin`을 클릭합니다. 

`PROD-Admin`의 `배포`탭에 들어가서 `새 배포` 버튼을 클릭합니다.

![배포하기](https://user-images.githubusercontent.com/54167990/65673990-cd881d80-e086-11e9-9f75-01d0d0f79e64.PNG)

Images 창이 나오면 `배포하기`를 클릭합니다.

`Are you sure?`이라는 창에서 `진행`을 클릭합니다.

프로덕션 서버는 배포전략이 `BLUE_GREEN`이므로 2개의 인스턴스가 필요합니다.

현재 배포 진행 중인 화면을 보면 2개가 생성중인 것을 확인할 수 있습니다.

![진행중](https://user-images.githubusercontent.com/54167990/65747563-bb68b680-e13c-11e9-8e23-716cb46b4620.png)

---

## 2# ALB IP 찾기

AWS 사이트에서 EC2의 `로드밸런서`를 클릭합니다. 

로드밸런서 `ALB-ATOMY-PROD-IngressWeb`의 `DNS 이름`을 복사합니다.

![로드밸런서](https://user-images.githubusercontent.com/54167990/65745718-94f44c80-e137-11e9-9a27-fc106bd98475.PNG)

터미널 창을 열고 `nslookup` 명령어를 사용하여 DNS의 IP 주소를 확인해보겠습니다.

```
C:\Users\user>nslookup ALB-ATOMY-PROD-IngressWeb-986934413.ap-northeast-2.elb.amazonaws.com
서버:    fortinet-public-dns-53.fortinet.com
Address:  208.91.112.53

권한 없는 응답:
이름:    ALB-ATOMY-PROD-IngressWeb-986934413.ap-northeast-2.elb.amazonaws.com
Addresses:  13.124.67.220
            52.78.112.33
```

DNS의 IP 주소 중 하나인 `52.78.112.33`을 복사합니다.

:bulb: **TIP**   
Linux나 MAC OS의 경우에는 `dig` 명령어를 사용합니다.   

```
MZ01-SONDAYEON:~ $ dig ALB-ATOMY-PROD-IngressWeb-986934413.ap-northeast-2.elb.amazonaws.com

.
.
;; ANSWER SECTION:
ALB-ATOMY-PROD-IngressWeb-986934413.ap-northeast-2.elb.amazonaws.com. 60 IN A 13.124.67.220
ALB-ATOMY-PROD-IngressWeb-986934413.ap-northeast-2.elb.amazonaws.com. 60 IN A 52.78.112.33    
```

## 3# hosts 파일에 IP 등록하기

- **Windows OS**의 경우

C:\Windows\System32\drivers\etc 의 `hosts` 파일을 notepad로 엽니다.

![hosts](https://user-images.githubusercontent.com/54167990/65746839-d1757780-e13a-11e9-8dc3-a8a8f6c8880d.PNG)

파일 아래에 다음과 같은 내용을 추가 후 저장합니다.

ALB IP | 호스트
--- | ---
52.78.112.33 | comm.atomy.com
52.78.112.33 | admin.comm.atomy.com
52.78.112.33 | comm-stadby.atomy.com
52.78.112.33 | admin.comm-stadby.atomy.com

- **Linux** 또는 **Mac OS** 의 경우

터미널에서 다음과 같이 실행합니다.

```
MZ01-SONDAYEON :~ $ sudo vi etc/hosts
```
hosts 파일이 열리면 아래에 다음과 같은 내용을 추가 후 저장합니다.

<img src="https://user-images.githubusercontent.com/54167990/65747408-544b0200-e13c-11e9-814c-d540e7e4d0f8.png" width="60%"></img>

ALB IP | 호스트
--- | ---
52.78.112.33 | comm.atomy.com
52.78.112.33 | admin.comm.atomy.com
52.78.112.33 | comm-stadby.atomy.com
52.78.112.33 | admin.comm-stadby.atomy.com

:bulb: **TIP**   
리눅스 환경에서 저장 및 종료를 하려면,   
`ESC` 버튼을 누른 후에 `:wq` 를 적으면 종료됩니다.

---

## 4# 런타임

`PROD-Admin`에서 `런타임 및 환경설정`을 클릭합니다.   

`엔드포인트` 버튼을 눌러서 `퍼블릭 엔드포인트`를 클릭합니다.

'admin.comm.atomy.com'의 웹사이트 화면이 뜨는 것을 확인할 수 있습니다.

---

이번엔 인스턴스의 설정을 변경해보겠습니다.

메모리를 **2304**로 변경합니다.   

`배포` 탭에서  `새 배포`를 클릭한 후, `Images` 창이 뜨면 `배포하기`를 클릭합니다.

`배포 하기` 창이 뜨면 `Confirmation on delivery from standby server to active server`에 체크를 하여   
**활성화** 시키고 `진행`을 클릭합니다.   

`런타임 및 환경설정`탭에서 `런타임 (STANDBY)` 를 누르고 대기합니다.   

![standby](https://user-images.githubusercontent.com/54167990/69292214-dfcaa600-0c48-11ea-881c-600fa80f3c8b.png)

standby 서버가 대기중이라는 안내 문구가 뜨게 되면,

`admin.comm-standby.atomy.com`인 standby로 접속하여 배포 전에 다시 TEST를 합니다.

TEST 후에, 액츄얼 서버에 `적용` 혹은 `취소` 할 수 있습니다.

`적용하기`를 클릭하면 액츄얼 배포 수락 창이 뜨고 `진행`을 클릭합니다.

`배포` 탭에서 현재 standby의 배포현황을 확인할 수 있으며, 롤백 또는 스탠바이 삭제도 할 수 있습니다.
          
---
:cd: 참고 영상

<iframe src="https://drive.google.com/file/d/1yIVskYnUqLRpVT2mICyAe-97H--rlRP6/preview" width="640" height="480"></iframe>

---

프로덕션 서버 배포하기 단계를 완료하셨습니다! :clap: :clap:

다음 챕터는 `배포 알림 설정하기`에 대해 배워보겠습니다.
