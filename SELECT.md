<H1>SELECT</H1>

> 테이블의 레코드 선택

```mysql
SELECT 필드이름 FROM 테이블이름 (WHERE 조건);
```

* 테이블의 모든 필드 선택하기

```mysql
SELECT * FROM TABLENAME;
```

* 특정 조건의 레코드 선택하기

```mysql
SELECT * FROM TABLENAME WHERE Name = 'John';
```

* 연산자를 이용한 WHERE절 조건 명시

```mysql
SELECT * FROM TABLENAME WHERE ID <= 3 AND DATECHECK > '2022-02-03';
```

* 특정 필드만 선택하기

```mysql
SELECT ID, DATE FROM TABLENAME;

SELECT Name, DATE FROM TABLENAME WHERE ID <= 3 AND DATECHECK > '2022-02-03';
```

* 중복되는 값 제거하기

```mysql
SELECT DISTINCT Name FROM TABLENAME;
//Name을 다 가져오는데 중복값을 제외하고 가져옴.
```

* 결과값 정렬하기

```mysql
SELECT * FROM TABLENAME ORDER BY DATECHECK;
SELECT * FROM TABLENAME ORDER BY DATECHECK ASC;
SELECT * FROM TABLENAME ORDER BY DATECHECK DESC;
SELECT * FROM TABLENAME ORDER BY DATECHECK DESC, Num ASC;
```

-기본적으로 오름차순(ASC), 내림차순은 (DESC) 키워드를 마지막에 추가하면 됨.

-대소문자까지 구분하여 정렬하고 싶을때는 ORDER BY BINARY를 사용.

* 별칭 사용하기 (Alias)

```mysql
1.SELECT 필드이름 AS 별칭 FROM TABLENAME;

2.SELECT 필드이름 FROM TABLENAME AS 별칭;
```

1. 해당 필드에 새로운 별칭을 부여.
2. 해당 테이블에 새로운 별칭 부여.





