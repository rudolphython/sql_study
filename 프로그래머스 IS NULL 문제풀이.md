## 프로그래머스 IS NULL



1. **이름이 없는 동물의 아이디**

   ```sql
   SELECT ANIMAL_ID FROM ANIMAL_INS WHERE NAME IS NULL;
   ```

   

2. **이름이 있는 동물의 아이디**

   ```sql
   SELECT ANIMAL_ID FROM ANIMAL_INS WHERE NAME IS NOT NULL;
   ```

   

3. **NULL 처리하기**

   ```SQL
   SELECT ANIMAL_TYPE, IFNULL(NAME, 'No name') AS NAME, SEX_UPON_INTAKE FROM ANIMAL_INS;
   
   # IFNULL(컬럼명, 바꿀 이름)
   ```

   

