# 3. SQL 문법(2)

# SQL WildCard

## _ (underbar)

```sql
slelect * from testtable where description like '__________not%'
```

- '_' 는 글자를 대변한다. 즉, 예시를 들자면 '__________not%' 는 앞에 아무 글자 10개가 오고 그 뒤에 not이 온 것 이라는 뜻이다. (띄어쓰기도 한 글자로 포함한다.)

## %

```sql
SELECT * FROM Customers
WHERE City LIKE 'ber%'; -- ber가 맨 앞으로 오는 데이터베이스를 추출한다.
```

```sql
SELECT * FROM Customers
WHERE City LIKE '%es%'; --es가 들어간 모든 데이터베이스를 추출한다.
```

- Represents zero or more characters

# Union

The UNION operator is used to combine the result-set of two or more SELECT statements.

- Each SELECT statement within UNION must have the same number of columns
- The columns must also have similar data types
- The columns in each SELECT statement must also be in the same order

즉, SELECT 명령어를 2개 또는 그 이상으로 나열할떄, UNION을 붙여 연결한다.

```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

```sql
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2; --UNION ALL은 중복값이 있어도 쓰겠다는 것이다.
```

솔직히 이 정도만 알고 있어도 SQL Injection을 하는데 아무런 문제도 없다.

바로 다음에는 실전으로 가보겠다.