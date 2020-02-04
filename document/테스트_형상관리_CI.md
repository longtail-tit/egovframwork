# 개발환경 테스트 구조, 형상 관리 및 CI 서버 

- 테스트 
- 개요 
- 테스트 종류 
- Unit Test
- Mock
- Batch Job Test
- DB Test
- Test Automation
- Test Reporting
- Test Coverage


> ## 테스트 

테스트 대상에 입력값을 넣었을 때 그 결과가 성공 혹은 실패의 결과를 내는 것. 

- 수동 테스트 
    - 장점: 쉽고 간편. 테스트 불가능 사항 거의 없음. 
    - 단점 : 휘발성. 테스트항목 들어나게되면 곤란. 재현의 어려움 

- 자동 테스트 
    - 장점 : 항상 같은 테스트 여러번 수행 가능. 빠름. 테스트가 축적이 되기 때문에 편리하다. 
    - 단점 : 코드로 작성해야함. 모듈화 관리 필요. 



> ## 개요 

![knjdf](https://user-images.githubusercontent.com/48245776/73707637-82ba9880-473f-11ea-889f-f57ab07ce6b8.PNG)

**TestCase 작성 지원 도구** 
- Unit Test Framework
- Mock Framework
- DB Test Framework

Test Automation, Test Coverage, Test Reporting 등의 기능을 제공한다. 

<br/>

**process**

![dsafdfadfds](https://user-images.githubusercontent.com/48245776/73707970-581d0f80-4740-11ea-8ed8-7ee5b97fc07a.PNG)

<br/>

> ## 테스트 종류 

테스트 도구는 개발자가 코드로 작성하고 도구를 통해 자동화할 수 있는 테스트 중 단위테스트에 해당된다. 

이후 Integratin Test, Access Test 까지 범위를 확장할 수 있는 토대를 마련했다. 

![fsdfasdfs](https://user-images.githubusercontent.com/48245776/73708127-e396a080-4740-11ea-96d9-f83dcc3d9c83.PNG)


<br/>

> ## Unit Test

특정 메소드를 실행해서 그 결과가 기대값과 일치하는지 확인하는 형대이다. Unit Test 는 서로 독립적으로 수행되어야 한다. 

- 효과 
    - 코드 품질에 대한 확신 
    - 코드 수정 시 버그 쉽게 찾음 
    - 자동회된 회귀 테스트를 가능하게 해주는 Source가 됨
       ( ***Regression Test*** : 기능 추가나 수정을 했을 때 새로 유입된 오류가 있는지 없는지 확인하는 테스트)

- 작성 범위 
    - 주요 흐름에 대한 테스트 
    - 또 다른 주요 흐름에 대한 테스트 
    - 경계 조건에 대한 테스트 (null 인자 체크 ..)
    - Exception 테스트 

[Unit Test 작성 범위 더 알아보기](http://i5on9i.blogspot.com/2017/05/unit-test.html)

<br/>

- 구성 

![etw](https://user-images.githubusercontent.com/48245776/73708470-d1693200-4741-11ea-86ee-a0f193e57f4e.PNG)

Unit Test는 Class로 생성된다. 공용으로 사용하는 테스트데이터(test fixture) , 테스트 데이터를 준비하는 Test Data SetUp , 테스트 메소드 (testXXX()..)가 있다. 

테스트 메소드는 테스트 대상 메소드를 실행하고  assert문을 이용한 결과 확인이 이루어진다. (assertTrue, assertEquals etc.)



- JUnit

자바 프로그래밍 언어를 위한 Unit Test Framework. 

<br/>

> ## Mock

Unit Test 의 독립성을 높여주기 위해서 사용된다. 테스트하고자 하는 코드와 관련이 있는 객체를 흉내내어서 Unit Test를 수행할 수 있도록 도와주는 객체이다. 즉, 가짜 객체 

***사용 종류***
- 이미 구현된 Mock 객체 사용 : Spring test(web, jndi), mock runner
- EasyMock, JMock, Mock 

***when?*** (참고: http://www.incodom.kr/Mock )
- 테스트가 특정 경우나 순간에 의존적인 경우. 
- 테스트 작성을 위한 환경 구축이 어려운 경우.

<br/>

**Spring Test web 샘플**

![testtesttest](https://user-images.githubusercontent.com/48245776/73712994-2a8b9280-474f-11ea-8b59-c356b9543321.PNG)

**EasyMock + Unitils 샘플**

![dfasdfadfas](https://user-images.githubusercontent.com/48245776/73713052-59096d80-474f-11ea-8aea-40d548e21568.PNG)

<br/>

> ## Batch Job Test 

참고: https://www.egovframe.go.kr/wiki/doku.php?id=egovframework:dev2.5:tst:batch_job_test_wizard

전자정부 표준프레임워크에서는 생성된 배치 파일들을 활용하여 간단한 테스트를 할 수 있는 테스트 마법사를 제공한다.

배치 테스트시 필요한 항목들을 골라서 테스트파일을 생성해주고 JUnit을 통한 테스트를 진행한다. 


![dfadfasdfasdfafsfawe](https://user-images.githubusercontent.com/48245776/73713411-a6d2a580-4750-11ea-92c9-edf1f7f42da5.PNG)

**배치 테스트 절차** 
1. 배치 job 정보 선택
2. Job Launcher 정보 선택 
3. 필요 시 Job Parameter 정보 선택 
4. Generate Batche Test File 클릭 -> 배치 테스트 팡리 생성 
5. Test 버튼 -> 테스트 수행 

<br/>

> ## DB Test

 DAO 와 DB 모두를 통틀어 Persistence Layer를 테스트하는 것을 말한다. 테스트DB와 테스트 데이터를 준비하여 실제로 DB를 이용한 단위테스트를 수행한다. 

 - DB Test Framework
   - DbUnit

- DbUnit 기능
    - DB 데이터를 XML파일 형태로 import / export
    - DB 연결, DB초기화
    - DB의 데이터가 기대값과 같은지 확인 
    - 빌드 도구를 통한 테스트 자동화 기능 제공 

<br/>

***TestCase 작성***
```java
@RunWith(UnitilsJUnit4TestClassRunner.class) 
@Transactional(TransactionMode.COMMIT) 
@DataSet //클래스 시작할 때 같은 위치에 있는 DaoOperationTest_noticeDas.xml 파일을 읽어 DB초기화 
@SpringApplicationContext( { 
    "/META-INF/persistence/connection/datasource-spring-with-unitils.xml",   // Datasource 연결 정보 (Unitils를 사용함)
     "/META-INF/spring/context-common.xml", "/META-INF/spring/context-sqlmap.xml" }) 
public class DaoOperationTest_noticeDao { 

    @TestDataSource   // dataSource 객체를 설정함. Unitils의 Datasource 정보 사용 
    private DataSource dataSource;

    /** Target Dao */ 
    @SpringBean("noticeDao") // Unitils의 Injection of Spring beans - noticeDao 라는 이름으로 정의된 Bean을 Spring Application Context로부터 가져옴 
    private NoticeDao noticeDao;
    private NoticeVo noticeVo;

    @Test 
    @ExpectedDataSet("/META-INF/**/AutoVerifyTestResultsTest_ExpectedDataSet.xml")  //지정된 위치의 Dataset 파일을 읽어 들여, 메소드 처리 후반에서 결과를 비교함. assert 기능
    public void testInsert() { 
        assertNotNull(noticeVo); 
        noticeDao.insert(noticeVo); 
        int count = noticeDao.selectCount(); 
        assertEquals(4, count); 
        }
}

```

***DataSet 구조***
```xml
<dataset>
    <TABLE_NAME COLUMN_NAME1 = "value1"
                COLUMN_NAME2 = "value2" 
    />
</dataset>
```

<br/>

> ## Test Automation

작성된 다수의 TestCase를 자동으로 수행하여 소스 단위의 품질을 높이고자 하는 것. CI 서버와 연계될 때 주기적으로 테스트 수행으로 인해 목표 시스템의 품질을 향상시킬 수 있다. 

- Test Suite
: TestCase 모음 

- Test Suite 설정 방법 
    -  Test Suite Class 작성 
    ```java
    @RunWith(Suite.class)
    @SuiteClasses({HttpRequestMockTest.class, SessionMockTest.class, FileUploadMockTest.class, EmailMockTest.class, JDBCMockTest.class})
    public class MockTestSuite{

    }
    ```

    - 빌드 도구의 batchtest 묶음 
    ```xml
    <junit...>
        <batchtest fork="yes" todir="${testreports.dir">
         <fileset dir="{testbuild.dir}">
            <include name="**/*Test.class" >
            <exclude name="**/Abstract*Test.class" >
         </fileset>
        </batchtest>
    </junit>
    ```


