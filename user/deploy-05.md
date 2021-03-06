# [4-6] 배포 스케쥴러 설정하기

안녕하세요.             
챕터 5의 배포 권한 설정하기가 잘 되었나요?

이번 챕터는 :star: 배포 스케쥴러 설정하기 :star:를 해보도록 합시다.

---

## 1# 스케쥴러 설정하기

원하는 서버 그룹을 클릭하여 `배포` 탭의 `스케쥴러`를 선택합니다.

`+ ADD SCHEDULER`를 클릭하여 스케쥴러를 추가합니다.

예를 들어, 매일 실행하는 스케쥴이라면...

이름 | 실행 방법 | 시간 | 브랜치 | 이미지
--- | --- | --- | --- | ---
매일 실행 스케쥴 | 매일 실행 | 14:00 | 특정 브랜치 이미지(^master) | 가장 최신 이미지

- 스케쥴 실행 방법 : 매일 실행 / 한 번만 실행
  - 매일 실행 선택 시 : 시간 선택
  - 한 번만 실행 선택 시 : 날짜와 시간 선택

- 브런치 선택 방법 : 브랜치를 특정하지 않음 / 특정 브랜치 이미지
  - 특정 브랜치 이미지 선택 시 : `^`를 맨 앞에 붙여 적어야 합니다. ex) ^master
  
- 이미지 선택 방법 : 가장 최신 이미지 배포 / 특정 시간 이전의 최신 이미지를 배포 / 정해진 이미지를 배포
  - 특정 시간 이전의 최신 이미지를 배포 선택 시 : 시간 선택
  - 정해진 이미지를 배포 선택 시 : 원하는 Image 선택

---
:cd: 참고 영상

<iframe src="https://drive.google.com/file/d/1uyh33QqvdpIATUclXrZHQvCBvH1JmwZN/preview" width="640" height="480"></iframe>

---

배포 스케쥴러 설정하기 단계를 완료하셨습니다! :clap: :clap:

다음은 새로운 챕터인 `프로덕션 디버깅`에서 `와탭 설정 및 사용하기`에 대해 배워보겠습니다.

---

> **작성자** : MEGAZONE DSG 웹서비스부문 개발2팀 `손다연` :sunglasses:            
> **Github** : https://github.com/It-dayeon
