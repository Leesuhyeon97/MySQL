<H1>NULL</H1>

> NULL 처리



<H3>IF NULL</H3>

> 해당 컬럼 값이 NULL일 때, 다른 값으로 출력할 수 있도록 하는 함수

```MYSQL
SELECT IFNULL(컬럼,"변경명") FROM TABLENAME;

SELECT IFNULL(NAME,"No name") AS NAME FROM TABLENAME;
```

-IF() 

> IF함수와 IS NULL 조건으로도 가능

```MYSQL
SELECT IF(IS NULL(NAME),"No name", NAME) AS NAME FROM TABLENAME;
```



<H3>CASE</H3>

> 컬럼 값을 조건식을 통해 TRUE,FALSE를 판단하여 조건에 맞게 컬럼값을 변환하는 함수

```MYSQL
CASE
	WHEN 조건1 THEN 식1
	WHEN 조건2 THEN 식2
	...
	ELSE 조건에 맞는 식이 없을 경우 실행할 식
END

SELECT
	CASE
		WHEN NAME IS NULL THEN "No name"
		ELSE NAME
	END AS NAME
FROM TABLENAME;
```



<H3>COALESCE</H3>

> 지정한 표현식중에 NULL이 아닌 첫 번째 값을 반환 - 모든 DBMS에서 사용가능

```MYSQL
SELECT COALESCE(컬럼1, 컬럼1이 NULL일 경우 대체 값 ) FROM TABLENAME;

//배타적 OR 관계 
SELECT COALESCE(컬럼1, 컬럼2, 컬럼3, 컬럼4) FROM TABLENAME;

SELECT COALESCE(NAME,"No name") FROM TABLENAME;
```

