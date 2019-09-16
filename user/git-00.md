# 깃랩 그룹 및 프로젝트 생성하기

안녕하세요.  
지금부터 DSG 웹서비스 부문의 CICD 적용 `USER` 가이드를 시작하겠습니다.  

이번 챕터는 :star:**깃랩 그룹 및 프로젝트 생성하기**:star: 입니다.

## 1. 깃랩 그룹 및 권한 확인하기

우선 이 과정을 하기 위해서는 `atomy` 그룹의 멤버로 등록 되어 있어야 합니다.  
> 만약 등록되어있지 않다면, ADMIN 계정에게 등록 요청을 하시길 바랍니다.    

또한, 자신의 권한이 `Maintainer` 또는 `Owner` 권한이여야 합니다.  

> `Maintainer` 권한이 아닌 `Guest`, `Reporter`, `Developer` 권한이라면  
> ADMIN 계정에게 권한 수정을 요청하시길 바랍니다. 

![maintainer 권한 확인하기](https://user-images.githubusercontent.com/54167990/64935965-a19eb800-d88e-11e9-9d36-7c93d64352a3.PNG)

> 확인 방법 : 관리자 영역 > 그룹들 > `atomy` 그룹 > atomy 그룹 멤버의 `액서스 관리` 버튼 > 권한 확인

> 참고 영상 : <iframe src="https://drive.google.com/file/d/11nHGwZBb7bk_zka9y5uKo6Vm2sFR0ObR/preview" width="640" height="480"></iframe>

## 2. 깃랩 프로젝트 생성하기

그룹 및 권한을 확인해 보셨나요?    
이번엔 새로운 프로젝트를 생성해보겠습니다.

GitLab의 `프로젝트` 를 눌러서 atomy 프로젝트 목록 화면이 뜨면, `New Project` 라는 초록 버튼을 클릭합니다.      
버튼을 누르면 다음과 같은 화면이 뜹니다.      

예시로 atomy의 `Community` 프로젝트를 만들어보곘습니다.

![새로운 프로젝트 생성하기](https://user-images.githubusercontent.com/54167990/64936553-871a0e00-d891-11e9-8224-efc9e212ffab.PNG)

- **프로젝트 이름** : atomy-comm 
- **프로젝트 URL** : https://gitlab.atomyops.com/atomy  
- **프로젝트 슬러그** : atomy-comm
- **Visibility Level** : Private
- **Initialize repository with a README** : Allow

> Tip: 현재 CICD를 설정 할 프로젝트에 맞는 이름을 만드시면 됩니다.    
> 예시) atomy-ticket, atomy-club ...


프로젝트가 잘 생성 되었나요?  
생성된 프로젝트에 들어가서, 왼쪽 하단 `설정`의 `저장소` 탭을 클릭합니다.   
저장소 설정에서 `Protected Branches`를 펼쳐봅시다.    

![Protected Branches 펼치기](https://user-images.githubusercontent.com/54167990/64938717-cc423e00-d899-11e9-8e21-1d1b6a42783a.PNG)

하단에 있는 `Unprotect` 버튼을 클릭합니다.

![Unprotect로 변경하기](https://user-images.githubusercontent.com/54167990/64937490-69e73e80-d895-11e9-8a3d-e83293a89256.png)

>  참고 영상 : <iframe src="https://drive.google.com/file/d/1AJWmm7rftx_DpdMtSRV32ReIMWbZ8p4W/preview" width="640" height="480"></iframe> 

---

깃랩을 활용하여 깃랩 그룹 및 권한을 확인하고 프로젝트를 생성하는 단계를 완료하셨습니다!   :clap:  :clap:          
다음 단계에서는 `코드를 이관하는 방법`에 대해 배워보겠습니다.  

