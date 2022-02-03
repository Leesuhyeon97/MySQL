<H1>GROUP_BY</H1>

> COUNT함수로 데이터를 조회하면 전체 갯수만 가져오는데 칼럼의 데이터를 그룹화 해서 유형별로 갯수를 알고 싶을 때 사용



<H3>GROUP BY</H3> 

> 특정 칼럼을 그룹화 하는 GROUP BY



<H3>HAVING</H3>

> 특정 칼럼을 그룹화한 결과에 조건을 거는 HAVING

-WHERE과는 다름. HAVING은 그룹화 한 후에 거는 조건.



```MYSQL
SELECT 컬럼 FROM TABLENAME GROUP BY 그룹화할 컬럼;
SELECT 컬럼 FROM TABLENAME WHERE 조건 GROUP BY 그룹화할 컬럼;
SELECT 컬럼 FROM TABLENAME GROUP BY 그룹화할 컬럼 HAVING 조건;
SELECT 컬럼 FROM TABLENAME WHERE 조건 GROUP BY 그룹화할 컬럼 HAVING 조건;
SELECT 컬럼 FROM TABLENAME (WHERE 조건) GROUP BY 그룹화할 컬럼 (HAVING 조건) ORDER BY 컬럼1,(컬럼2, 컬럼3, ...);
```



TABLENAME = 'STUDENT'

| NUM  | TYPE  | NAME  |
| ---- | ----- | ----- |
| 1    | MAN   | JOHN  |
| 2    | MAN   | CARL  |
| 3    | WOMAN | LILY  |
| 4    | WOMAN | DAISY |
| 5    | WOMAN | EMMA  |

예제

```MYSQL
//TYPE을 그룹화하여 NAME의 갯수를 조회 ( 컬럼 그룹화 )
SELECT TYPE, COUNT(NAME) AS CNT FROM STUDENT GROUP BY TYPE;

//TYPE이 1초과인 TYPE을 그룹화하여 NAME 갯수 조회( 조건 처리후 컬럼 그룹화 )
SELECT TYPE, COUNT(NAME) AS CNT FROM STUDENT WHERE TYPE > 1 GROUP BY TYPE;

//TYPE을 그룹화하여 NAME 갯수를 가져온 후, 그 중 갯수가 2개이상인 데이터 조회 
SELECT TYPE, COUNT(NAME) AS CNT FROM STUDENT GROUP BY TYPE HAVING CNT >= 2;

//TYPE이 1초과인 TYPE을 그룹화하여 NAME 갯수를 가저온 후, 그 중 갯수가 2개 이상인 데이터 조회 ( 조건 처리 후 컬럼 그룹화 후 조건 처리 )
SELECT TYPE, COUNT(NAME) AS CNT FROM STUDENT WHERE TYPE > 1 GROUP BY TYPE HAVING CNT >= 2;

//TYPE이 1초과인 TYPE을 그룹화하여 NAME 갯수를 가져온 후, 그중 갯수가 2개 이상인 데이터를 TYPE의 내림차순으로 조회
SELECT TYPE, COUNT(NAME) AS CNT FROM STUDENT WHERE TYPE > 1 GROUP BY TYPE HAVING CNT >= 2 ORDER BY TYPE DESC;
```

