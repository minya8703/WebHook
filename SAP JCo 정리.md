# SAP Java Connector(JCo) 설정
## '1. sapjco3.jar / sapjco3.dll / libsapjco3.so 는 SAP 연동시 필요한, SAP Java Connector(JCO) 관련 파일을 준비
- https://support.sap.com/en/product/connectors/jco.html?anchorId=section_2129803369
- 기본적으로 SAP계정이 있다면 위의 사이트에서 받을 수 있다.
![image](https://github.com/minya8703/WebHook/assets/97384342/c09b98d8-8ac5-4c9b-b14a-b8922c61cef1)


## 2. 사용하는 서버에 따라 파일 설정 방식이 다르기에 사용하는 서버를 확인	
- 【참고】 서버별 설정 방법
- 이 파일은 Windows Server기준으로 작성

##  3. Window LOCAL환경 셋팅	
- sapjco.dll 파일을 C:\Windows\System32 폴더 안에 넣어준다.
![image](https://github.com/minya8703/WebHook/assets/97384342/b96faf41-84f1-4bb6-ac0f-b2abc1703034)
## 4. WebServer 프로젝트에서 lib폴더를 만들어 "sapjco3.jar" 라이브러리 추가		
- Spring boot 프로젝트라면 Build Tool 에 따라 다르기에 아래의 Tool에 따라 dependency를 추가	
  -	※ Gradle
  -	1. lib 폴더에 sapjco3.jar을 추가
![lib](https://github.com/minya8703/WebHook/assets/97384342/39b6840e-20fe-4c67-a719-5763f42d5978)
  -	2. build.gradle파일에 dependencies { 여기에 추가 } 아래의 정보를 추가
  -	      implementation files("lib/sapjco3.jar")

## 【참고】 서버별 설정 방법
<br> https://husheart.tistory.com/135
###  Window LOCAL
- sapjco3.jar : Java Build Path 메뉴에서 라이브러리 추가
- sapjco3.dll : System32에 추가.

###  Windows Server
- sapjco3.jar, sapjco3.dll : Apache Tomcat - lib 폴더에 추가.

###  Linux Server
- sapjco3.jar, libsapjco3.so : Apache Tomcat - lib 폴더에 추가.

###  ETC Server
- ▶ IBM AIX 서버: libsapjco3.so, sapjco3.jar
- ▶ HP-UX11 서버 : libsapjco3.sl/so, sapjco3.jar
- ▶ Linux 서버 : libsapjco3.so, sapjco3.jar
- ▶ Oracle Solaris 서버 : libsapjco3.so, sapjco3.jar
- ▶ Microsoft Windows 서버 : sapjco3.dll, sapjco3.jar
- ▶ IBM iSeries 서버 : libicudata34.a, libicui18n34.a, libicuuc34.a, libsapjco3.so, os4apilib.so, sapjco3.jar


