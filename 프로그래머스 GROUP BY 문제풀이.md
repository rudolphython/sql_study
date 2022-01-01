## 프로그래머스 GROUP BY 문제풀이



1. **고양이과 개는 몇 마리 있을까**

   ```sql
   SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE) FROM ANIMAL_INS GROUP BY ANIMAL_TYPE ORDER BY ANIMAL_TYPE;
   ```

   

2. **동명 동물 수 찾기**

   ```sql
   SELECT NAME, COUNT(NAME) AS 'COUNT' 
   FROM ANIMAL_INS 
   GROUP BY NAME 
   HAVING COUNT(NAME) > 1 
   ORDER BY NAME
   
   # AS를 쓴 이유는 정답 처리가 되지 않아서
   # GROUP BY를 쓸 때는, WHERE이 아니라 HAVING 절을 씀
   ```

   

3. **입양 시각 구하기 1번**

   ```sql
   SELECT HOUR(DATETIME) HOUR, COUNT(DATETIME) COUNT
   FROM ANIMAL_OUTS 
   GROUP BY HOUR(DATETIME) HAVING HOUR >= 9 AND HOUR <=19 
   ORDER BY HOUR ASC;
   
   # 테이블 이름을 HOUR, COUNT로 하기 위해서 HOUR(DATETIME) HOUR 이런 식으로 씀.
   # GROUP BY 조건절은 HAVING으로 해결
   # HOUR은 DATETIME에서 시간을 추출
   ```



4. **입양 시각 구하기 2번**

   ```SQL
   SET @hour := -1; -- 변수 선언
   
   SELECT (@hour := @hour + 1) as HOUR,
   (SELECT COUNT(*) FROM ANIMAL_OUTS WHERE HOUR(DATETIME) = @hour) as COUNT
   FROM ANIMAL_OUTS
   WHERE @hour < 23
   
   # SET은 변수 선언, @가 붙은 변수는 프로시저 종료 후에도 유지
   # :=은 대입 연산자
   # 1씩 증가하면서 조회
   ```

   