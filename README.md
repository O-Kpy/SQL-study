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

- SHOW DATABASES;(데이터 탐색)

- USE 데이터명;(데이터 선택)

- SHOW TABLES;(데이터의 테이블들을 출력)

- SHOW TABLES STATUS;(테이블의 상태, 정보 출력)

- DESCRIBE 데이터명;(데이터의 열 정보 출력)

- SELECT, FROM(선택, 어디서 부터)

- WHERE(조건문, if,where,for문)
  1. 조건 연산자(=, <, >, <=, !=... 등)
  2. 관계 연산자(NOT, AND, OR등) 
  3. 연산자의 조합으로 데이터를 효율적으로 추출
  
- BETWEEN ... AND ...(숫자로 구성되어 연속적인 값을 반환 받도록 할때) 

- IN (A,B,C) (()안에 있는 것들을 것들을 반환) ex)```WHERE NAME IN (A,B,C)```

- LIKE (**문자열**을 포함하는것을 반환, find()) ex)```WHERE NAME LIKE 'KO_' ==> KOR```
  1. _(언더바)는 한 글자를 매치 하기 위함
  2. %(퍼센트)는 문자열 무엇이든 포함하면 반환 ex) ```WHERE CITY LIKE 'tel %' ==> tel aviv```

- Sub Query(쿼리 문 안에 또 쿼리문이 들어 있는 것)
  1. 서브 쿼리의 결과가 두개 이상이면 에러
  2. ex) ```SELECT * FROM file WHERE citycode = ( SELECT citycode FROM file WHERE name like 'kore_')``` ==> 'KOR'로 시작되는 자료 반환

- ANY(서브 쿼리 중 한가지만 만족해도 출력, or(|)), SOME
  1. ex) ```SELECT * FROM file WHERE price > ANY( SELECT price FROM name WHERE building LIKE 'KJ%')``` ==> 'KJ'로 시작되는 빌딩들의 가격보다 하나라도 높은 price를 가지는 자료 반환
 
- ALL(서브 쿼리 중 모두 만족하는 자료 출력, and(&))
  1. ex) ```SELECT * FROM file WHERE price > ALL( SELECT price FROM name WHERE buliding LIKE 'KJ%')``` ==> 'KJ'로 시작되는 빌딩들의 가격들보다 모두 높은 것을 출력(모두 만족)

- ORDER BY(결과 출력 순서, sorted, sort_values(ascending=False))
  1. default = 오름차순(ascending) ex) ```SELECT * FROM file ORDER BY population ASC```
  2. 내림차순(descending) ex) SELECT * ```FROM file ORDER BY population DESC```
  3. ex) ```SELECT * FROM file ORDER BY countrycode DESC, population ASC``` ==> countrycode는 내림차순, population은 오름차순으로 정렬 반환

실습1 인구수로 내림차순 하여 '한국'에 있는 도시 보기
 = ```SELECT * FROM file WHERE countrycode = 'KOR' ORDER BY population DESC```
 
실습2 국가 면적 크기로 내림차순하여 나라 보기
 = ```SELECT * FROM file ORDER BY surfacearea DESC```
 

