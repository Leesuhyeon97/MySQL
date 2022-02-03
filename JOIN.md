<H1>JOIN</H1>

> 데이터베이스 내의 여러 테이블에서 가져온 레코드를 조합하여 하나의 테이블이나 결과 집합으로 표현해주는 것.



<H3>INNER JOIN</H3>

> 두 테이블이 동시에 가지는 값만 가져옴

```MYSQL
SELECT * FROM TABLE1 INNER JOIN TABLE2 ON TABLE1.COL = TABLE2.COL;
SELECT * FROM TABLE1 JOIN TABLE2 ON TABLE1.COL = TABLE2.COL;

SELECT * FROM TABLE1 AS T1, TABLE2 AS T2 WHERE T1.COL = T2.COL;
```



<H3>LEFT JOIN</H3>

> 첫번째 테이블을 기준으로, 두 번째 테이블을 조합하는 JOIN

```MYSQL
SELECT * FROM TABLE1 LEFT JOIN TABLE2 ON TABLE1.COL = TABLE2.COL (WHERE 조건);
```





<H3>RIGHT JOIN</H3>

> 두번째 테이블을 기준으로, 첫 번째 테이블을 조합하는 JOIN

```MYSQL
SELECT * FROM TABLE1 RIGHT JOIN TABLE2 ON TABLE1.COL = TABLE2.COL (WHERE 조건);
```



<H2>UNION</H2>

> 여러 개의 SELECT 문의 결과를하나의 테이블이나 결과 집합으로 표현할 때 사용. 
>
> 이때 각각의 SELECT문으로 선택된 필드의 갯수와 타입은 모두 같아야 하며, 필드의 순서또한 같아야 함.

-자동적으로 중복을 제외하고 출력됨

```MYSQL
SELECT COL1 
FROM TABLE1
UNION
SELECT COL1
FROM TABLE2;
```

- 중복되는 값까지 출력할 때

```MYSQL
SELECT COL1
FROM TABLE1
UNION ALL
SELECT COL1
FROM TABLE2;
```

