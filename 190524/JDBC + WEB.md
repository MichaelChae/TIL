## [JDBC 프로그래밍 정리]

ODBC ==>C, C++

- JDBC API(Interface) + JDBC Driver

  Java.sql                        DB서버에 따로 추가로 준비

- JDBC 프로그램의 구현 과정

  (1) JDBC 드라이버 로딩(Class.forName(대표클래스이름))

  ```java
  Class.forName("oracle.jdbc.driver.OracleDriver");
  ```

  (2) DB 서버 접속(DriverMAnager.getConnection(JDBCURL, ID, PASSWD))

  ```java
  Connection conn = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:XE",
  					"scott", "tiger");
  ```

  

  (3)  Statement, PreParedStatement 객체 생성

  ```java
  Statement stmt = conn.createStatement();
  esultSet rs = stmt.executeQuery("SELECT * from product");
  PreparedStatement pstmt = conn.prepareStatement("select deptno, upper(ename) ename, " + "to_char(hiredate, 'yyyy\"년\" mm\"월\"') hiredate from emp where deptno=?");
  ```

  

  (4) executeQuery(), executeUpdate()

  ​		ResultSet			Int

  ​		next(), getXxx()   변화된 행의 갯수

  (5) 연결된 자원 해제 : close 

  ```java
  scn.close();
  pstmt.close();
  conn.close();
  ```

  

  시험 문제  connection이 나온다 

  































