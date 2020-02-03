# 개발환경 소개 및 구현도구, 개인빌드 

1. 개발환경 개요 
    * 개발환경 개요 
    * 개발환경 구성요소 
    * 적용 오픈 소스 
    * 서비스 별 소개 
    * 개발자 개발환경 구성 
    * 서버 개발환경 구성 
2. 구현도구 
3. 개인 빌드(Maven)

<br/>

> 개발환경 개요 

개발환경 크게 4가지로 분류 
1) 개발환경 : 개발자가 정부 개발 프레임워크를 기반으로 어플리케이션을 개발하기 위한 개발환경  
2) 실행환경 : 응용소프트웨어 그 자체
3) 관리환경 : 프레임워크 관리자로서 개발프레임워크를 효과적으로 관리하기 위한 환경
4) 운영환경 
: 운영소프트웨어로서 운영 지원을 받기위한 환경 


>  개발환경 구성요소 

개발환경은 개발자 PC에서 개발서버, 운영서버로 연결되는 개발 흐름을 지원한다. 

![dsfafad](https://user-images.githubusercontent.com/48245776/73625286-81c63000-4687-11ea-9447-710d6959a6f5.PNG)



> 적용 오픈 소스 

전자정부 프레임워크는 오픈소스로 제공된다. 라이선스 범위를 확인하고 스코프에 맞게 개발을 한다면 문제가 없다. 

사용화를 할 경우엔 라이선스를 참고해서 범위에 벗어나지 않게 유의하면 된다. 

![개발환경선정결과](https://user-images.githubusercontent.com/48245776/73625016-69094a80-4686-11ea-993e-0b175f39a975.PNG)


![캡처](https://user-images.githubusercontent.com/48245776/73625055-a5d54180-4686-11ea-873f-df07e3d05b6d.PNG)


***m2eclipse란?***

이클립스의 Run As 메뉴에 Maven 기본 생명주기 단계를 추가하여 빌드 편의성을 제공한다. 

왜 메이븐? - 메이븐은 pom.xml을 통한 로컬 관리가 가능하기 때문에 


> 서비스 별 소개 

 ***1) 구현도구*** 

개발자의 코드 작성 및 디버깅을 지원하는 도구로 Eclips 기반 하에 Plug-in 을 제공한다. 

![캡처](https://user-images.githubusercontent.com/48245776/73625253-65c28e80-4687-11ea-8198-0f97d42443ca.PNG)


 ***2) 테스트 도구*** 

JUnit 기반으로 TestCase 작성 및 수행을 지원하고, 자동으로 테스트하고 리포팅하도록 지원하는 도구. 


테스트를 하는 이유? - 배포를 하기 전에 개발소스를 점검하고 문제점을 찾기 위해. 

![dasfdffdas](https://user-images.githubusercontent.com/48245776/73625385-e84b4e00-4687-11ea-9826-edf1a40946cc.PNG)

 ***3) 배포도구*** 

Maven 기반의 개발자 빌드와 CI서버를 통한 지속적인 통합을 지향. 

메이븐의 문제점 중 하나가 서드레파지토리를 사용 할 때 바로 굿어이 안되는 경우가 있다. 그 경우에 넥서스리파지토리를 사용하거나, 다른 방식을 찾아서 메이븐 로컬에 연결이 가능하다. 


**빌드 자동화 도구?**   CI서버, 배포-빌드-형산관리-변경까지 지원해주는 것. 



주요 메커니즘에는 구현도구를 올리고 빌드 자동화를 하게 됐을 때, 빌드가 올라가면서 리포트가 된다. 허드슨도 마찬가지. 

허드슨이 왜 필요한가? 허드슨 결과를 보고 pm이 확인을 한다. 날씨 아이콘을 통해 빌드 현황을 확인할 수 있다. 


 ***4) 형상관리*** 
 

svn활용을 통한 이슈관리. 자바기반의 이슈관리 시스템을 통해 이슈등록, 검색, 처리까지 가능.

![hyungsang](https://user-images.githubusercontent.com/48245776/73625682-36ad1c80-4689-11ea-9488-4e4de7104115.PNG)
 

<br/><br/>

> 개발자 개발환경 구성 

**교육자료 및 실습자료 설치** -  
eGovFrame-3.6.0.exe 



***디렉토리 정보***

* bin
    * android-sdk-windows&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 윈도우용 안드로이드 SDK 폴더 
    * apache-tomcat-7.0.59   
    * apache-tomcat-8.0.24&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 아파치 톰캣
    * eclipse&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 개발환경이 포함된 ecilp JEE Mars.2 Release(4.5.2)
    * jdk 1.8.0_45 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - JDK_HOME
    * mysql-5.6.21    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - 실습용 DB
* maven/repository &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- LocalMaven Repository
* textbook &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 교육 교재 파일 
* workspace.edu &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-  Eclipst Workspace

설치를 완료하고 이클립스를 실행하면 교육자료가 바로 나온다. 

<**Maven Installations 설정 확인**>

![mavensetting](https://user-images.githubusercontent.com/48245776/73628597-06b74680-4694-11ea-8b69-c8e780b9db4e.PNG)

보통은 pom.xml로 repository를 자동으로 가져오기 때문에, 바로 가져올 수 없는 라이브러리에 대하여 모르고 넘어가는 부분이 있다. 

preferences-maven-user setting 에 가면 "setting.xml"이라는 파일이 있는데 Maven 레파지토리가 저장되는 부분이 있다. 

문제가 없을 경우엔 자동으로 라이브러리를 끌어와서 사용할 수 있지만, 서드라이브러리 같은 바로 당겨올 수 없는 것들이 존재한다. 특히 공공기관 개발 같은 경우엔 공인인증서 라이브러리가 대표적인 예이다. 특히 공인인증서 같은 경우는 바로 사용 불가하고, local에 넣어서 가져와야한다. 

심지어 바로 local 에 가져올 수 있는것이 아니라 사이트에서 관련 레파지토리를 등록하고 받아서 저장해야한다. 참 번거롭다. 공인인증서는 사라져야해...

이 부분만 숙지한다면 그 외에는 프레임워크를 통해 자동으로 라이브러리를 관리할 수 있다. 



