# [1-3] 지라 이슈 트래커와 깃랩 연동하기

안녕하세요.  
챕터 2의 코드 이관이 잘 되었나요?

이번 챕터는 :star: **자라 이슈 트래커와 깃랩을 연동** :star: 해보도록 합시다.

---

## 1# API 토큰 만들기 

우선 atlassian 사이트에 들어가 로그인합니다.         
:point_right: [atlassian 사이트로 이동하기](https://id.atlassian.com/login)

로그인 후, `계정 관리`에서 `보안`에 들어가 `API 토큰 생성 및 관리`를 클릭합니다. 

![계정 관리](https://user-images.githubusercontent.com/54167990/65202404-4c002080-dac5-11e9-9bff-cf3f5c329809.PNG)

API 토큰 탭에 들어가서 `API 토큰 만들기` 버튼을 클릭하여 토큰을 만들어보겠습니다.

![API 토큰 생성](https://user-images.githubusercontent.com/54167990/65202902-b44f0200-dac5-11e9-8673-905190138116.png)

그럼 다음과 같은 API 토큰 값이 나오게 되며, **이 값을 복사하여 저장**해놓아야 합니다.  

<img width="372" alt="Screen+Shot+2017-09-25+at+5 09 09+pm" src="https://user-images.githubusercontent.com/54167990/65207839-101d8900-dace-11e9-9f65-f523eb278adf.png">

:bulb: **TIP**    
보안상의 이유로 **대화 상자를 닫은 후 토큰을 볼 수 없습니다.**    
토큰 값을 꼭 안전하게 저장해주시기 바랍니다.

---

## 2# GITLAB에 JIRA 연동하기

깃랩에 접속해서 프로젝트 목록에서 현재 작업하고 있는 프로젝트를 클릭합니다.

설정 > 연동 > Project Services 에서 `JIRA` 를 선택합니다.

![JIRA](https://user-images.githubusercontent.com/54167990/65203692-bf566200-dac6-11e9-9a5e-c7ff869a5f80.PNG)

JIRA에 들어가 다음과 같이 작성합니다.

![JIRA 작성하기](https://user-images.githubusercontent.com/54167990/65207568-f465b300-dacc-11e9-8f34-5debd694ae79.PNG)

- **Active** : 활성화
- **Trigger** : Commit, Merge request 활성화
- **Web URL** : 회사의 지라 Web URL 적기 ex) https://mzdevs.atlassian.net
- **JIRA API URL** : 지라의 API URL 적기 ex) https://mzdevs.atlassian.net
- **Username or Email** : 본인의 이름 또는 회사 이메일 ex) sondayeon 또는 sondayeon@mz.co.kr
- **Password or API token** : 1번에서 만든 API 토큰 값 

다 작성한 후 아래의 `Test setting and save changes` 버튼을 누릅니다.

---

## 3# JIRA 이슈 트래커와 깃랩 연동 

이제 JIRA에 접속하여, 미결 이슈 중 하나를 골라서 이슈 링크를 복사해보도록 합시다.

![이슈 링크 복사](https://user-images.githubusercontent.com/54167990/65208369-cc2b8380-dacf-11e9-8717-f10469516f40.PNG)

복사한 후, GitLab 프로젝트의 저장소 > 파일로 들어갑니다.    
파일에서 커밋하며 메세지를 적어보겠습니다.

![커밋 메세지](https://user-images.githubusercontent.com/54167990/65209955-87561b80-dad4-11e9-9f9e-4dac881a9efd.PNG)

메세지엔 아까 복사한 이슈 링크 번호를 넣어 작성합니다.     
예시) [ATOMYCWS-1714] Update test.txt file

작성 후, `Commit changes` 버튼을 눌러 commit 합니다.

다시 JIRA에 접속하면 commit 메세지가 댓글로 생성된 것을 확인할 수 있습니다.

![댓글 생성](https://user-images.githubusercontent.com/54167990/65210185-53c7c100-dad5-11e9-8fc0-d752924b6b4a.PNG)

---

:cd: **참고 영상**   
<iframe src="https://drive.google.com/file/d/1bPACGUlMSVk3xmZW4b3zqbjdLBO0SyLq/preview" width="640" height="480"></iframe>

---

지라 이슈 트래커와 깃랩을 연동하는 단계를 완료하셨습니다!   :clap:  :clap:  

다음 단계에서는 `머지 리퀘스트 사용하기`에 대해 배워보겠습니다.
