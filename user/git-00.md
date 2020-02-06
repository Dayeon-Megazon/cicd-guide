# [1-1] 깃랩 그룹 및 프로젝트 생성하기

안녕하세요.  

DSG 웹 서비스 부문의 개발 2팀 :beginner:`손다연`입니다.

지금부터 DSG 웹서비스 부문의 CICD 적용 `USER` 가이드를 시작하겠습니다.  

이번 챕터는 :star: **깃랩 그룹 및 프로젝트 생성하기** :star: 입니다.

---

## 1-1# 깃랩 그룹 및 권한 확인하기

우선 이 과정을 하기 위해서는 `atomy` 그룹의 멤버로 등록 되어 있어야 합니다.  
> 만약 등록되어있지 않다면, ADMIN 계정에게 등록 요청을 하시길 바랍니다.    

또한, 자신의 권한이 `Maintainer` 또는 `Owner` 권한이여야 합니다.  

> `Maintainer` 권한이 아닌 `Guest`, `Reporter`, `Developer` 권한이라면  
> ADMIN 계정에게 권한 수정을 요청하시길 바랍니다. 

![maintainer 권한 확인하기](https://user-images.githubusercontent.com/54167990/64935965-a19eb800-d88e-11e9-9d36-7c93d64352a3.PNG)

:bulb: **확인 방법**    
관리자 영역 > 그룹들 > `atomy` 그룹 > atomy 그룹 멤버의 `액서스 관리` 버튼 > 권한 확인

---

## 1-2# 깃랩 사용자 추가 및 권한부여하기 (:lock: 관리자 영역)

깃랩에 새로운 사용자를 추가하고 권한을 주기 위해서는     
`Maintainer 이상의 권한을 가진 관리자 계정`이 필요합니다.

깃랩의 상단바에서 `관리자 영역`을 클릭하여 들어갑니다.

![사용자 추가하기](https://user-images.githubusercontent.com/54167990/73903761-402ec280-48dd-11ea-9d9e-984abef2deb1.png)

> 관리자 영역 Dashboard > Users의 `New user` 버튼 클릭    

![사용자 필수 정보 입력](https://user-images.githubusercontent.com/54167990/73903965-dcf16000-48dd-11ea-87a3-75ffa7c20fce.png)

사용자의 필수값인 `이름, Username, 이메일`을 입력합니다.    

> :zap: 주의1 : 문자, 숫자, ' _ ', ' - '및 ' . '만 포함 할 수 있습니다.       
> :zap: 주의2 : ' - '로 시작하거나 ' . ', ' .git ' 또는 ' .atom '으로 끝날 수 없습니다.                  
> :zap: 주의3 : Username을 한글로 작성하면 오류가 발생하니 `영어`로 작성해주시기 바랍니다.

![사용자 선택 정보 입력](https://user-images.githubusercontent.com/54167990/73904153-86385600-48de-11ea-8888-40b795a7b8b3.png)

새로운 사용자의 정보를 입력한 후, `Create user` 버튼을 클릭하여 사용자를 생성합니다.

:bulb: **TIP**  
`Create user` 버튼을 클릭하면 새로운 사용자에게 메일이 전송됩니다.   
사용자가 메일을 받고 깃랩에 가입을 한 이후에 깃랩의 그룹에 추가할 수 있습니다.


![추가할 그룹 선택](https://user-images.githubusercontent.com/54167990/73904328-0e1e6000-48df-11ea-9945-49e6eeaccaf7.png)

새로운 사용자가 메일을 받고 깃랩에 가입하였다면,    
깃랩 상단바의 `그룹들` > `당신의 그룹`을 클릭하여 그룹목록으로 들어옵니다.

그룹들의 목록에서 사용자를 추가할 `그룹폴더`를 클릭합니다.    
여기서는 예시로 `Atomy 그룹 폴더`를 클릭하여 들어가 보겠습니다.  

![멤버 찾기](https://user-images.githubusercontent.com/54167990/73904478-8f75f280-48df-11ea-9c78-c66bce543fe5.png)

그룹에 들어 간 후 왼쪽 탭에서 `회원`을 선택합니다.      

회원에서 새로 추가할 멤버를 검색해서 찾습니다.   

![멤버 추가하기](https://user-images.githubusercontent.com/54167990/73904600-e54a9a80-48df-11ea-8171-bd3883bbe5c6.png)

사용자에 맞게 권한 및 만료일을 설정한 후,

`Add to group` 버튼을 클릭하면 사용자가 깃랩에 성공적으로 추가됩니다. :thumbsup:

---

:cd: **참고 영상**
<iframe src="https://drive.google.com/file/d/11nHGwZBb7bk_zka9y5uKo6Vm2sFR0ObR/preview" width="640" height="480"></iframe>

---
## 2# 깃랩 프로젝트 생성하기

그룹 및 권한을 확인해 보셨나요?    
이번엔 새로운 프로젝트를 생성해보겠습니다.

GitLab의 `프로젝트` 를 눌러서 atomy 프로젝트 목록 화면이 뜨면, `New Project` 라는 초록 버튼을 클릭합니다.      
버튼을 누르면 다음과 같은 화면이 뜹니다.      

예시로 atomy의 `Community` 프로젝트를 만들어보곘습니다.

![새로운 프로젝트 생성하기](https://user-images.githubusercontent.com/54167990/64936553-871a0e00-d891-11e9-8224-efc9e212ffab.PNG)

프로젝트 설정 | 설정 값 
--- | ---
**프로젝트 이름** | atomy-comm 
**프로젝트 URL** | https://gitlab.atomyops.com/atomy  
**프로젝트 슬러그** | atomy-comm
**Visibility Level** | Private
**Initialize repository with a README**  | Allow


:bulb: **TIP**    
CICD를 설정 할 프로젝트에 맞도록 이름을 설정하시면 됩니다. Ex) atomy-ticket, atomy-club ...

---

## 3# Branches를 Unprotect로 바꾸기 

프로젝트가 잘 생성 되었나요?  

생성된 프로젝트에 들어가서, 왼쪽 하단 `설정`의 `저장소` 탭을 클릭합니다.   
저장소 설정에서 `Protected Branches`를 펼쳐봅시다.    

![Protected Branches 펼치기](https://user-images.githubusercontent.com/54167990/64938717-cc423e00-d899-11e9-8e21-1d1b6a42783a.PNG)

하단에 있는 `Unprotect` 버튼을 클릭합니다.

![Unprotect로 변경하기](https://user-images.githubusercontent.com/54167990/64937490-69e73e80-d895-11e9-8a3d-e83293a89256.png)

---

:cd: **참고 영상**    
<iframe src="https://drive.google.com/file/d/1AJWmm7rftx_DpdMtSRV32ReIMWbZ8p4W/preview" width="640" height="480"></iframe> 

---

깃랩을 활용하여 깃랩 그룹 및 권한을 확인하고 프로젝트를 생성하는 단계를 완료하셨습니다!   :clap:  :clap:  

다음 단계에서는 `코드를 이관하는 방법`에 대해 배워보겠습니다.  

---

> **작성자** : Megazone DSG 웹서비스부문 개발2팀 `손다연` :sunglasses:
