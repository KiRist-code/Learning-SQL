# 1주차. What is SQL?

# Data 분석 과정

- 문제 인식 → 데디터 수집과 가공 → 데이터 분석 → 분석 결과 실행
- 여기서 2번째 단계를 전처리(Pre-processing)라고 하는데, 전체 과정에 70%~80퍼를 차지하고 있음
- 데이터 수집과 가공, 데이터 분석 과정에 SQL을 쓸 수 있다.

# 정형 데이터와 비정형 데이터

- 정형 데이터는 틀이 잡혀있는 데이터, 업무용 데이터 베이스와 같은 곳에서 가지고 오는 데이터
- 비정형 데이터는 틀이 잡혀있지 않은 데이터, 텍스트, 이미지, 음원 데이터, 빅데이터 등
- 여기서 SQL은 정형 데이터로 만들어진 관계형 데이터 베이스를 조작할 수 있는 언어

# SQL is...

- a standard language for storing, manipulating and retrieving data in databases

→ 데이터베이스에 데이터를 저장, 조작 및 검색하기 위한 표준 언어

# What Can SQL do?

- SQL can execute queries against a database
- SQL can retrieve data from a database
- SQL can insert records in a database
- SQL can update records in a database
- SQL can delete records from a database
- SQL can create new databases
- SQL can create new tables in a database
- SQL can create stored procedures in a database
- SQL can create views in a database
- SQL can set permissions on tables, procedures, and views

# CRUD

- Update
- Delete
- Select
- etc . . .

# Using SQL in Your Web Site

To build a web site that shows data from a database, you will need:

- An RDBMS database program (i.e. MS Access, SQL Server, MySQL)
- To use a server-side scripting language, like PHP or ASP
- To use SQL to get the data you want
- To use HTML / CSS to style the page

# RDBMS

- RDBMS stands for Relational Database Management System.
- RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.
- The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.

# SQL 명령어의 분류

- 데이터 조작어(DML)
    - SELECT
    - INSERT
    - UPDATE
    - DELETE
- 데이터 정의어(DDL)
    - CREATE
    - ALTER
    - DROP
    - RENAME
    - TRUNCATE
- 데이터 제어어(DCL)
    - GRANT
    - REVOKE
- 트렌젝션 제어어(TCL)
    - COMMIT
    - ROLLBACK
    - SAVEPOINT

    # Some of The Most Important SQL Commands

    - **SELECT** - extracts data from a database
    - **UPDATE** - updates data in a database
    - **DELETE** - deletes data from a database
    - **INSERT INTO** - inserts new data into a database
    - **CREATE DATABASE** - creates a new database
    - **ALTER DATABASE** - modifies a database
    - **CREATE TABLE** - creates a new table
    - **ALTER TABLE** - modifies a table
    - **DROP TABLE** - deletes a table
    - **CREATE INDEX** - creates an index (search key)
    - **DROP INDEX** - deletes an index

# 관계형 데이터베이스의 구성 요소

- TABLE(행, 열), VIEW(데이터를 선택하여 만든 가상의 부분집합), INDEX(주소를 사용한 검색), SEQUENCE(시퀸스,고유번호 자동생성), SYNONYM(시노임,객체의 별칭) 등의 객체로 구성
- ENTITY, RELATION 들의 집합

# The SQL SELECT Statement

The SELECT statement is used to select data from a database.

The data returned is stored in a result table, called the result-set.

```sql
SELECT * FROM table_name;
```

- table_name 에서 *(모든것)을 가져온다

# The SQL SELECT DISTINCT Statement

The SELECT DISTINCT statement is used to return only distinct (different) values.

Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

```sql
SELECT DISTINCT column FROM table_name;
```

DISTINCT ⇒ 중복 되는 것을 하나로 합친다

- table_name에서 column에 해당하는걸 뽑는데, 단 중복되는 것은 뺀다.

# ORDER BY

- 오름차순: ASC (기본, 작은 수에서 큰 수로)
- 내림차순: DESC (큰 수에서 작은 수로)

```sql
SELECT * FROM Customers ORDER BY CustomerID DESC;
```

```sql
SELECT * FROM Customers ORDER BY CustomerID ASC;
```

# AS

- 별칭

```sql
SELECT * AS 사원번호 FROM Customers;
```

```sql
SELECT CustomerID AS 사원번호, Country AS 나라 FROM Customers;
```

# 사칙연산

- 더하고 빼고 나누고 곱하는 것이 가능

```sql
SELECT (CustomerID/3)+5 AS 주소 FROM Customers;
```

# 연결 연산자

```sql
SELECT CustomerID AS 사원번호, City || Address ||' 분류 - ' || ' 외국 ' AS 주소 FROM Customers;
```

|| ⇒ 연결 시켜준다

# The SQL WHERE Clause

The WHERE clause is used to filter records.

The WHERE clause is used to extract only those records that fulfill a specified condition.

- 연산자의 종류: 비교연산자(=,<,>,! =,< =, > =), SQL 연산자(BETWEEN), 논리 연산자(AND, OR)

```sql
SELECT *column1*, *column2, ...*FROM *table_name* WHERE *condition*;
```

WHERE ⇒ 조건에 해당하는 것을 찾는다.

# SQL 연산자

BETWEEN A AND B: A와 B를 포함한 사이의 값

```sql
SELECT CustomerID FROM Customers WHERE CustomerID BETWEEN 30 AND 50;
```

IN A: A안에 어느 값이 일치하는 지 확인

```sql
SELECT CustomerID FROM Customers WHERE CustomerID IN (10,20,30);
```

LIKE '비교문자' : 비교 문자와 형태가 일치(%(모든문자), _(한문자) 사용)

대소문자를 안가림

```sql
SELECT CustomerID, CustomerName FROM Customers WHERE CustomerName LIKE 'A%';
```

IS NULL: NULL 값을 갖는 값

```sql
SELECT CustomerID, CustomerName FROM Customers WHERE CustomerName IS NULL;
```

# 논리 연산자

The WHERE clause can be combined with AND, OR, and NOT operators.

The AND and OR operators are used to filter records based on more than one condition:

- The AND operator displays a record if all the conditions separated by AND are TRUE.
- The OR operator displays a record if any of the conditions separated by OR is TRUE.

The NOT operator displays a record if the condition(s) is NOT TRUE.

## AND

```sql
SELECT column1, column2, ... FROM table_name WHERE condition1 AND condition2 AND condition3 ...;
```

AND ⇒ 조건의 교집합

## OR

```sql
SELECT column1, column2, ... FROM table_name WHERE condition1 OR condition2 OR condition3 ...;
```

OR ⇒ 조건의 합집합

## NOT

```sql
SELECT column1, column2, ... FROM table_name WHERE NOT condition;
```

NOT ⇒ 조건의 여집합

# `<>` 같지 않다(IOS 표준)

```sql
SELECT * FROM Customers WHERE CustomerID LIKE '1%' AND NOT (City <> 'London' AND City <> 'Berlin');
```

## example

```sql
SELECT * FROM Customers WHERE CustomerID LIKE '1%' AND NOT (City = 'London' OR City = 'Berlin');
```
