# [4-5] 배포 권한 설정하기

안녕하세요.             
챕터 4의 배포 알림 설정하기가 잘 되었나요?

이번 챕터는 :star: 배포 권한 설정하기 :star:를 해보도록 합시다.

---

## 1# ACL 그룹 만들기

왼쪽 상단의 버튼을 클릭하여 `ACL group`을 클릭합니다.

`+ ADD ACL GROUP`을 클릭하여 아래 표와 같이 ACL 그룹을 추가합니다.

NAME | TYPE | APP_BUILD_EDIT | APP_BUILD_START_THROUGH_UI
--- | --- | --- | ---
ACL-APP | app | Maintainer | Developer

NAME | TYPE | SETTING
--- | --- | --- 
ACL-SGR-DEV | sgr | Developer
ACL-SGR-STG | sgr | Developer

NAME | TYPE | SG_NEW_DEPLOYMENT_THROUGH_UI | SG_CONTAINER_LOG_VIEW | SG_CONTAINER_SSH | OTHERS
--- | --- | --- | --- | --- | ---
ACL-SGR-PROD | sgr | Maintainer | Maintainer | Maintainer | Developer 

---

## 2# ACL 그룹 설정하기

`apps`를 클릭하여, 해당 프로젝트 app의 `Action`에 있는 설정 버튼을 클릭합니다.

`ACL Group Allocate`에서 `ACL-APP` 정책을 선택하고 `SAVE` 버튼을 눌러 저장합니다.


프로젝트를 클릭하여 `서버 그룹`의 `ACL 정책 변경`을 클릭해 아래 표와 같이 설정하고 `SAVE` 버튼을 눌러 저장합니다.


NAME | ACL 
--- | ---
DEV-Admin | ACL-SGR-DEV 
STG-Admin | ACL-SGR-STG
PROD-Admin | ACL-SGR-PROD
DEV-Front | ACL-SGR-DEV
STG-Front | ACL-SGR-STG
PROD-Front | ACL-SGR-PROD

---
:cd: 참고 영상

<iframe src="https://drive.google.com/file/d/1PPUQJcYwCY18oLeCGbNxb9oBzIBRD7Z3/preview" width="640" height="480"></iframe>

---

배포 권한 설정하기 단계를 완료하셨습니다! :clap: :clap:

다음 챕터는 `배포 스케쥴러 설정하기`에 대해 배워보겠습니다.

---

> **작성자** : MEGAZONE DSG 웹서비스부문 개발2팀 `손다연` :sunglasses:
