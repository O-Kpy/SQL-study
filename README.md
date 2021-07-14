# SQL-study
---
# DML(Data Manipuluation Language
 - 데이터 조작 언어
 - 데이터를 조작(선택, 삽입, 수정, 삭제)하는데 사용되는 언어
 - DML 사용하기 위해서는 꼭 그 이전에 ***테이블***이 정의 되어 있어야 함
 - SELECT, INSERT, UPDATE, DELETE가 이 구문에 해당
 - 트랜잭션이 발생하는 SQL도 이 DML에 속함
   (테이블의 데이터를 변경(입력/수정/삭제)할 때 실제 테이블에 완전히 적용하지 않고, 임시로 적용시키는것, 취소가능)
 
 # DDL(Data Definition Language)
  - 데이터 정의 언어
  - 데이터베이스, 테이블, 뷰, 인덱스 등의 데이터 베이스 개체를 생성/삭제/변경하는 역할
  - CREATE, DROP, ALTER 구문
  - DDL은 트랜잭션 발생시키지 않음
  - ROLLBACK이나 COMMIT 사용 불가(조심해서 사용해야 한다 대참사가 일어난다)
  - DDL문은 실행 즉시 MYSQL에 적용
 
 # DCL(Data Control Language)
  - 데이터 제어 언어
  - 사용자에게 어떤 권한을 부여하거나 빼앗을때 주로 사용하는 구문
  - GRANT, REVOKE, 

---

SHOW DATABASES;(데이터 탐색)

USE 데이터명;(데이터 선택)

SHOW TABLES;(데이터의 테이블들을 출력)

SHOW TABLES STATUS;(테이블의 상태, 정보 출력)

DESCRIBE 데이터명;(데이터의 열 정보 출력)

SELECT, FROM(선택, 어디서 부터)

WHERE(조건문)
 - 관계 연산자의 사용
  > 조건 연산자(=, <, >, <=, !=... 등)
  > 
  > 관계 연산자(NOT, AND, OR등)
  > 
  > 연산자의 조합으로 데이터를 효율적으로 추출
  
