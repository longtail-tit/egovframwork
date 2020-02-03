# 개발환경 소개 및 구현도구, 개인빌드 

- 개발환경 개요 
    * 개발환경 개요 
    * 개발환경 구성요소 
    * 적용 오픈 소스 
    * 서비스 별 소개 
- 개인 빌드(Maven)

<br/>
<hr>

 ## 개발환경 개요 

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


<br/><br/>
<hr>

## Maven

불필요한 설정을 최소회한다는 개졈 아래 Ant와 같은 빌드 기능을 제공할 뿐 아니라 구조화 된 빌드 기능을 통해 learning curve 및 재사용성을 향상시킨다. 

**특징**

* 장점
    1) 뛰어난 의존성 관리
    2) 모든 프로젝트에 걸쳐 쉽게 적용 가능한 일괄적인 사용법 
    3) 라이브러리 및 메타 저장을 위한 지속적으로 확장되고 있는 저장소 
    4) 쉽게 작성 가능한 플러그 인을 통한 확장성 
    5) 동시에 다수의 프로젝트를 핸들링 할 수 있는 쉬운 설정 기반의 메커니즘 
    6) 간단한 설정을 통한 배포 관리 
    7) Java, C++ 등 다수의 프로그래밍 언어 지원 

* 단점
    1) repository 관리의 불편함 
        - Maven 프로젝트의 급속한 발전으로 central repository 가 제공하는 라이브러리들이 급속히 증하하고 있으나, 아직 3rd 파티 라이브러리 등 미제공 라이브러리 등이 존재. 
    
    2) pom.xml 파일 관리 
        - 메이븐 프로젝트 관리에 대한 모든 내용이 pom.xml 파일에 담기게 되므로 길고 장황하게 될 수 있다. 

    3) 프로젝트에 특화된 복잡한 빌드 기능 제약 
        - 메이븐 프로젝트 특성상 소프트웨어 빌드에 통용되는 라이프 사이클을 제공하고 있어 세부 항목 또는 특화된 빌드 환경에 대한 지원이 미약하다. 


**Maven 아키텍처**

![hahahaahahahah](https://user-images.githubusercontent.com/48245776/73634627-f491d400-46a4-11ea-8c48-ef893547e020.PNG)

- 프로젝트 객체 모델(POM) : 메이븐 엔진 내장 + POM.XML  파일에서 선언적으로 제공 
- 의존성 관리 모델 : 로컬 및 리모트 저장소를 이용하여 관리 
- 빌드 생명주기와 각 단계 : 잘 정의된 단계들과 빌드 사이클에 따라 플러그인들을 조율


**Maven 디렉토리 구조**

![mavenderectory](https://user-images.githubusercontent.com/48245776/73634849-7aae1a80-46a5-11ea-9277-2bf2a6c28ff3.PNG)

- ```/pom.xml``` : 프로젝트 객체 모델. 해당 프로젝트에 대한 전반적인 정보를 갖는다. 
- ```/src/main/java``` : Java 소스 파일 위치 
- ```/src/main/resoureces``` : 배포할 리소스, XML, properties...등 설정 파일들
- ```/src/main/webapp``` : 웹 어플리케이션 관련 파일 위치(WEB-INF, css 등)
- ```/src/test/java``` : 테스트 케이스 java 소스
- ```/src/test/resoureces``` : 테스트 케이스 리소스 
- ```/target``` : 빌드 된 output이 위치하는 디렉토리 


**빌드 LifeCycle**

![DFLKJDFALDKSF](https://user-images.githubusercontent.com/48245776/73635180-44bd6600-46a6-11ea-9b67-ae71c34591dd.PNG)


**Maven repository**

artifact들의 저장소로 로컬 및 리모트 repository로 구성되며 프로젝트는 pom.xml에서 선언한 dependency들을 저장소로부터 불러와서 사용한다. 

![zzz](https://user-images.githubusercontent.com/48245776/73635402-ce6d3380-46a6-11ea-9268-9b59a7c5af2f.PNG)



**프로젝트 객체 모델(POM)**

프로젝트의 구조와 내용 설명. pom.xml파일에 프로젝트 관리 및 빌드에 필요한 환경 설정, 의존성 관리 등의 정보들을 기술한다. 

![d](https://user-images.githubusercontent.com/48245776/73635574-273ccc00-46a7-11ea-85b5-90e24a6ea510.PNG)

-> 프로젝트의 세부 메타 데이터 정보를 포함한다. 
- ***버전 및 설정 관리, 빌드 환경, 라이브러리 저장소 및 의존성***

![하하](https://user-images.githubusercontent.com/48245776/73635683-60753c00-46a7-11ea-8811-66e5c6a1f7d4.PNG)



**Maven 기본 기능**

프로젝트 우클릭 - Update Project - maven clean - maven install