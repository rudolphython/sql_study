## 프로그래머스 String, Date 문제풀이



1. **루시와 엘라 찾기**

   ```sql
   SELECT ANIMAL_ID, NAME, SEX_UPON_INTAKE
   FROM ANIMAL_INS
   WHERE NAME = 'Lucy' OR NAME = 'Ella' OR NAME = 'Rogan' OR NAME = 'Pickle' OR NAME = 'Sabrina' OR NAME = 'Mitty'
   ORDER BY ANIMAL_ID;
   ```

   

2. **이름에  EL이 들어가는 동물 찾기**

   ```sql
   SELECT ANIMAL_ID, NAME FROM ANIMAL_INS 
   WHERE ANIMAL_TYPE = 'Dog' AND NAME LIKE '%el%' OR '%EL%' ORDER BY NAME;
   ```

   

3. **중성화 여부 파악하기**

   ```sql
   SELECT ANIMAL_ID, NAME, 
   CASE
    WHEN SEX_UPON_INTAKE LIKE '%Neutered%' OR SEX_UPON_INTAKE LIKE '%Spayed%'
    THEN 'O'
    ELSE 'X' END as '중성화'
   FROM ANIMAL_INS
   ORDER BY ANIMAL_ID
   
   # CASE는 삼항 연산자 같이 생각. THEN과 ELSE 사용
   ```

   

4. **오랜 기간 보호한 동물(2)**

   ```sql
   SELECT A.ANIMAL_ID, A.NAME
   FROM ANIMAL_INS A, ANIMAL_OUTS B
   WHERE A.ANIMAL_ID = B.ANIMAL_ID
   ORDER BY B.DATETIME-A.DATETIME DESC
   LIMIT 2
   ```

   

5. **DATETIME에서 DATE로 형 변환**

   ```sql
   SELECT ANIMAL_ID, NAME, DATE_FORMAT(DATETIME, '%Y-%m-%d') AS 날짜 FROM ANIMAL_INS
   ```

   

