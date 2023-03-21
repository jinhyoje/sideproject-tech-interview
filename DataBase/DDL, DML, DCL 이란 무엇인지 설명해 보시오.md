[ DDL (Data Definition Language) ] - 데이터 정의어

데이터베이스를 정의하는 언어를 말하며 데이터를 생성하거나 수정, 삭제 등 데이터의 전체 골격을 결정하는 역할의 언어를 말한다.
- CREATE, ALTER, DROP, RENAME,TRUNCATE 

[ DML (Data Manipulation Language) ] - 데이터 조작어

정의된 데이터베이스에 입력된 레코드를 조회하거나 수정하거나 삭제하는 등의 역할을 하는 언어를 말한다.
쉽게 말하면, 테이블에 있는 행과 열을 조작하는 언어라고 생각하면 된다. 
데이터베이스 사용자가 질의어를 통하여 저장된 데이터를 실질적으로 처리하는데 사용하는 언어이다.
- SELECT, INSERT, UPDATE, DELETE 

[ DCL (Data Control Language) ] - 데이터 제어어

데이터베이스에 접근하거나 객체에 권한을 주는 등의 역할을 하는 언어를 말한다.
데이터를 제어하는 언어이다. 
데이터의 보안, 무결성, 회복 등을 정의하는데 사용한다.
- commit, rollback, grant, revoke

DDL을 통해 데이터 베이스와 테이블을 생성 및 변경, 제거를 하고
DML을 통해 생성된 테이블 내에 있는 데이터들(행과 열)을 입력, 변경, 수정 등을 하며
DCL을 통해 데이터베이스의 접속 권한 등을 수정할 수 있다.

DCL에서 트랜젝션 제어를 위한 별도의 명령을 TCL로 구분하기도 한다.
- commit, rollback
