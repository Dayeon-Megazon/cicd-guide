# [4-1] 런타임 및 환경 변수 설정하기

안녕하세요.

3번째 단원인 CI설정이 잘 진행되었나요?

이제 4번째 단원인 `런타임 및 배포`에 대해 배워보겠습니다.

이번 챕터에서는 :star: **런타임 및 환경 변수 설정하기** :star: 를 해보도록 합시다. 

---

## 1# ADMIN 서버 그룹 환경변수 설정하기

우선 CICD 사이트에 접속합니다.     
현재 `atomy` 프로젝트로 실습하고 있으므로, atomy의 CICD 사이트로 접속하겠습니다.

:point_right: [ATOMY CICD 사이트로 접속하기](http://cicd.atomyops.com)

> 프로젝트에 따라 CICD 사이트가 다르므로, 자신의 프로젝트에 맞는 사이트로 접속하시길 바랍니다.

사이트에 접속하여  프로젝트에 들어간 후, `DEV-Admin`을 클릭합니다.     

![환경 변수](https://user-images.githubusercontent.com/54167990/65661705-4b3f2f80-e06d-11e9-9119-68fc9ab6dcb7.PNG)

`런타임 및 환경설정`에서 `환경 설정` 탭을 클릭합니다.  
환경 변수 이름은 그대로 `JAVA_OPTS`로 설정한 후, 환경 변수 값을 변경합니다.

ADMIN 그룹 | 환경 변수
---- | ----
DEV-Admin | -Dwhatap.name=**COMM-ADMIN**-{ip2}-{ip3}-{pid} -javaagent:/my-agent/whatap.agent.tracer-**1.8.6.jar** -Dwhatap.okind=**COMM-ADMIN**-Dmtrace_rate=100 -server -Xms1024m -Xmx1024m -XX:NewRatio=3 -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintHeapAtGC -Xloggc:gc.log -XX:+DisableExplicitGC -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 -Dnetworkaddress.cache.ttl=0 **-Dprofile=-dev**
STG-Admin | -Dwhatap.name=**COMM-ADMIN**-{ip2}-{ip3}-{pid} -javaagent:/my-agent/whatap.agent.tracer-**1.8.6.jar** -Dwhatap.okind=**COMM-ADMIN**-Dmtrace_rate=100 -server -Xms1024m -Xmx1024m -XX:NewRatio=3 -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintHeapAtGC -Xloggc:gc.log -XX:+DisableExplicitGC -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 -Dnetworkaddress.cache.ttl=0 **-Dprofile=-stg**
PROD-Admin | -Dwhatap.name=**COMM-ADMIN**-{ip2}-{ip3}-{pid} -javaagent:/my-agent/whatap.agent.tracer-**1.8.6.jar** -Dwhatap.okind=**COMM-ADMIN**-Dmtrace_rate=100 -server **-Xms2048m -Xmx2048m** -XX:NewRatio=3 -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintHeapAtGC -Xloggc:gc.log -XX:+DisableExplicitGC -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 -Dnetworkaddress.cache.ttl=0 **-Dprofile=-prd**

설정 후, `저장`을 눌러 환경변수를 저장합니다.

---

## 2# FRONT 서버 그룹 환경변수 설정하기

`런타임 및 환경설정`에서 `환경 설정` 탭을 클릭합니다.  
환경 변수 이름은 그대로 `JAVA_OPTS`로 설정한 후, 환경 변수 값을 변경합니다.

FRONT 그룹 | 환경 변수
---- | ----
DEV-Front | -Dwhatap.name=**COMM-FRONT**-{ip2}-{ip3}-{pid} -javaagent:/my-agent/whatap.agent.tracer-**1.8.6.jar** -Dwhatap.okind=**COMM-FRONT**-Dmtrace_rate=100 -server -Xms1024m -Xmx1024m -XX:NewRatio=3 -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintHeapAtGC -Xloggc:gc.log -XX:+DisableExplicitGC -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 -Dnetworkaddress.cache.ttl=0 **-Dprofile=-dev**
STG-Front | -Dwhatap.name=**COMM-FRONT**-{ip2}-{ip3}-{pid} -javaagent:/my-agent/whatap.agent.tracer-**1.8.6.jar** -Dwhatap.okind=**COMM-FRONT**-Dmtrace_rate=100 -server -Xms1024m -Xmx1024m -XX:NewRatio=3 -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintHeapAtGC -Xloggc:gc.log -XX:+DisableExplicitGC -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 -Dnetworkaddress.cache.ttl=0 **-Dprofile=-stg**
PROD-Front | -Dwhatap.name=**COMM-FRONT**-{ip2}-{ip3}-{pid} -javaagent:/my-agent/whatap.agent.tracer-**1.8.6.jar** -Dwhatap.okind=**COMM-FRONT**-Dmtrace_rate=100 -server **-Xms2048m -Xmx2048m** -XX:NewRatio=3 -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -verbose:gc -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintHeapAtGC -Xloggc:gc.log -XX:+DisableExplicitGC -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 -Dnetworkaddress.cache.ttl=0 **-Dprofile=-prd**

설정 후, `저장`을 눌러 환경변수를 저장합니다.

---
:cd: 참고영상

<iframe src="https://drive.google.com/file/d/1ustgcVCxfgYXy7VJsRzeiuxFbLgmnUUS/preview" width="640" height="480"></iframe>
---

런타임 및 환경 변수를 설정하는 단계를 완료하셨습니다! :clap: :clap:

다음 단계에서는 `개발 서버 배포하기`에 대해 배워보겠습니다.
