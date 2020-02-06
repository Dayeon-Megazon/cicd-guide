# [4-4] 배포 알림 설정하기

안녕하세요.             
챕터 3의 프로덕션 서버 배포가 잘 되었나요?

이번 챕터는 :star: 배포 알림 설정하기 :star:를 해보도록 합시다.

---

## 1# Notification group 설정하기

왼쪽 상단의 버튼을 클릭하여 `Notification group`을 클릭합니다.

`+ ADD NOTIFICATION GROUP`을 클릭하여 그룹을 3개 만듭니다.

NOTIFY-DEV | NOTIFY-STG | NOTIFY-PROD
--- | --- | ---


원래 하고 있던 프로젝트로 돌아옵니다.             
서버 그룹을 선택 한 후 `Notification 정책 변경`을 클릭하여, 아래 표에 맞게 선택하고 `save` 합니다.

NAME | GROUP
--- | ---
DEV-Admin | NOTIFY-DEV
STG-Admin | NOTIFY-STG
PROD-Admin | NOTIFY-PROD
DEV-Front | NOTIFY-DEV
STG-Front | NOTIFY-STG
PROD-Front | NOTIFY-PROD

---
:cd: 참고 영상

<iframe src="https://drive.google.com/file/d/16yfqZ_12aXIultN7n8str9yCKCY7Fhcm/preview" width="640" height="480"></iframe>

---

배포 알림 설정하기 단계를 완료하셨습니다! :clap: :clap:

다음 챕터는 `배포 권한 설정하기`에 대해 배워보겠습니다.

---

> **작성자** : MEGAZONE DSG 웹서비스부문 개발2팀 `손다연` :sunglasses:            
> **Github** : https://github.com/It-dayeon
