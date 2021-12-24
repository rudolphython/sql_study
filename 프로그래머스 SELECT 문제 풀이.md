## **프로그래머스 SELECT 문제 풀이**



1. **모든 레코드 조회하기**

   ```sql
   SELECT * FROM ANIMAL_INS ORDER BY ANIMAL_ID ASC;
   ```



2. **역순 정렬하기**

   ```sql
   SELECT NAME, DATETIME FROM ANIMAL_INS ORDER BY ANIMAL_ID DESC
   ```

   

3. **아픈 동물 찾기**

   ```SQL
   SELECT ANIMAL_ID, NAME FROM ANIMAL_INS WHERE INTAKE_CONDITION = 'sick';
   ```

   

4. **어린동물 찾기**

   ```sql
   SELECT ANIMAL_ID, NAME FROM ANIMAL_INS WHERE INTAKE_CONDITION != "Aged";
   # 나이든 상태가 아니니 WHERE 조건문에서 != 사용
   ```

   

5. **동물의 아이디와 이름**

   ```SQL
   SELECT ANIMAL_ID, NAME FROM ANIMAL_INS ORDER BY ANIMAL_ID ASC;



6. **여러 기준으로 정렬하기**

   ```sql
   SELECT ANIMAL_ID, NAME, DATETIME FROM ANIMAL_INS ORDER BY NAME ASC, DATETIME DESC;
   ```

   

7. **상위 N개 레코드**

   ```SQL
   SELECT NAME FROM ANIMAL_INS ORDER BY DATETIME ASC LIMIT 1;
   ```

   