---
tags:
---


# What
## SQL의 종류
SQL은 RDBMS의 데이터를 관리하기 위해 설계된 특수목적의 프로그래밍 언어다. DBMS의 필수 기능에는 정의, 조작, 제어가 있다.

- 정의 : 데이터베이스 구조를 생성하거나 변경, 삭제
- 조작 : 데이터베이스 안에 저장된 데이터에 접근해 생성, 수정, 삭제 및 검색
- 제어 : DBMS는 여러 사용자가 동시에 접근하더라도 항상 데이터를 정확하고 안전하게 유지하도록 통제한다.

SQL은 여기에 TCL을 더해 4가지 종류가 있다.
### DDL (데이터 정의 언어, Data Definition Language)

DB 객체 (TABLE, INDEX, VIEW 등)를 생성, 수정, 삭제할 목적으로 사용되는 언어. CREATE, ALTER, DROP, RENAME 등이 있다.

> CREATE 학생(학번, 이름, 학년, 성별, 전공)

![https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2019/01/01111318/Relational-databse.png](https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2019/01/01111318/Relational-databse.png)

데이터베이스 구조는 **스키마**(schema)라고도 한다. 테이블 이름과 열 이름으로 표현될 수 있다.

### [[DML]] (데이터 조작 언어, Data Manipulation Language)

### DCL (데이터 제어 언어, Data Control Language)

데이터베이스를 제어하기 위한 언어. 데이터베이스가 안정적으로 동작하고 성능을 유지하도록 각종 제약이나 옵션을 설정함으로써 DBMS가 데이터베이스를 올바르게 관리하도록 한다.

GRANT, REVOKE, CREATE USER 등이 있다.

### TCL (Transaction Control Language) : 트랜잭션 제어어

DML 명령문으로 수행한 변경을 관리 (트랜잭션 관리)하는 언어.  
COMMIT, ROLLBACK, SAVEPOINT 등이 있다.

# Why


# How