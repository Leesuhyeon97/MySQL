<h1>String</h1>

> MySQL에서 문자열



1. IN

```MYSQL
SELECT SELECTLIST FROM TABLENAME 
WHERE 조건 IN('STRING1','STRING2');
```



2. LIKE

```MYSQL
1. 특정 문자로 "시작하는" 데이터 검색 
SELECT 필드명 FROM TABLENAME WHERE 필드명 LIKE 'STRING%';

2. 특정 문자로 "끝나는" 데이터 검색
SELECT 필드명 FROM TABLENAME WHERE 필드명 LIKE '%STRING';

3. 특정 문자를 "포함하는" 데이터 검색
SELECT 필드명 FROM TABLENAME WHERE 필드명 LIKE '%STRING%';

4. "복수개의" 특정 문자 포함 데이터 검색
SELECT 필드명 FROM TABLENAME 
WHERE 필드명 LIKE '%STRING%' OR 필드명 LIKE '%STRING%';

5. 맨 앞 한 글자 뒤에 특정 문자가 있는 데이터 검색
SELECT 필드명 FROM TABLENAME WHERE 필드명 LIKE '_STRING%';

6. 맨 앞 두 글자 뒤에 특정 문자가 있는 데이터 검색
SELECT 필드명 FROM TABLENAME WHERE 필드명 LIKE '__STRING%';

7. 특정 문자 앞뒤로 2개의 문자가 있는 데이터 검색
SELECT 필드명 FROM TABLENAME WHERE 필드명 LIKE '__STRING__';
```



3. REGEXP

> LIKE 보다 복잡한 패턴을 검색할 때 사용

```MYSQL
SELECT 필드명 FROM TABELNAME WHERE 필드명 
REGEXP 'STRING1 | STRING2 | ...';
```

