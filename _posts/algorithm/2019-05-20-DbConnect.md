
#디비연동 절차!!!
~~~


JDBC (Java DataBase Conectivity)

1. 기본문법
2. 화면 (View) -JDBC 

####JDBC 연동절차

1.  드라이버 ( 각 데이터베이스를 인식할 수 있는 ) 메모리 로딩
2.  연결객체 얻어오기
3.  SQL 문장 만들기 (******)
4.  SQL 전송 객체 얻어오기
    - Statement : 완벽한 SQL
    - PreparedStatement : 미완성 SQL
    - CallableStatement : PL&SQL - Procedure /Function 호출시
5. SQL 전송
    - INSERT / UPDATE / DELETE : int executeUpdate()  , DDL도 가능!?
    - SELECT : ResultSet executeQuery()
6. 결과 처리 
7. 닫기( 연결 닫는 것이 중요 ) 


TIP
Statement - 컬럼명을 지정할때?! 컬럼명에 '' 붙지않게 하기 위해
sql은 한번만 던져준다. 

확장을 위해 인터페이스?! ->소스확인 : implements 
같은틀을 다른곳에 똑같이 적용하기 위해서 인터페이스를 구현해서 각각 사용한다.
확장성?!

~~~

// Code School의 Git 따라하기

//DELE(스페인어능력시험)

//에어비앤비 -> 서로의 방을 올리구 공유할 수 잇게 네트워으로 대화도 가능하게
