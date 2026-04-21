### Union sql injection

Union = 병합하다


```SQL
SELECT ZIP_CODE, DONG, ADDRS FROM POST WHERE DONG= '%param%'
```
param = param 8%'--

실제 실행코드
```SQL
SELECT ZIP_CODE, DONG, ADDRS FROM POST WHERE DONG= '%param 8%'--%'
```

- SQL Injection 참고사이트 : pentest monkey

- SQL 쿼리 테스트 사이트 : sql fiddle

- SQL 정보 검색 사이트 : gurubee
  - gurubee SQL 커뮤니티 검색할 때 gurubee를 사용하면 원하는 문법을 빠르게 찾을 수 있음


USER_TABLES   
유저가 생성한 테이블   
개인정보가 여기에 담겨있을 확률이 높다!

'' / ‘’ SQL 에서 Single Quote입력시 혼동주의!
세로방향과 살짝 누워있는게 있음 ''을 사용   
word에 붙여넣기 할 경우 자동으로 바뀜 주의, Cntl + C 할때는 메모장에 하는 걸 권장

### ERROR SQL Injection

SELECT COUNT(테이블) FROM ALL_TABLES;   
테이블 수 나옴

더 많은 문법은 Database참조


### Blind Injection

SUBSTR(자르고 싶은 문자열, 자르고싶은 위치, 자르고싶은 개수)

ASCII(SUBSTR((SELECT ..FROM(..)WHERE RNUM = 60 )1,1)) > 75

param8%' AND LENGTH((SELECT TABLE_NAME FROM (SELECT TABLE_NAME, ROWNUM AS RNUM FROM USER_TABLES) WHERE RNUM=3)) > 8 --

## 대처방안

구문분석 - 치환 - 실행 - 인출

구문분석(parse) - 시간이 가장 오래걸리는 작업
- 문법검사
- 의미검사
- 권한검사
- 실행계획

Prepared Statement를 통해 속도와 보안성 증가

문자를 필터링해 방어ex)
- ALL_TABLRS
- USER_TABLES 
