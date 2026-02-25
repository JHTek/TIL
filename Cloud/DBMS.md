# DBMS

데이터베이스 서버
- MySQL
- PostgreSQL
- MariaDB
- Amazon Aurora


관계형 데이터베이스 (RDBMS) - table    
비관계형 데이터배이스 (NoSQL) - 키밸류, 문서기반, 그래프 


## RDS

_RDBMS_ 를 클라우드에서 사용하는 **관리형** 서비스

알아서 관리되는 인스턴스의 크기를 지정가능

_Multi-AZ_ 를 사용하여 또 다른 AZ 가용영역에 예비DB생성 

읽기 전용 복제본을 만들어 읽이 부하를 분산, Master DB가 장애가 생기면 읽기 전용 DB를 Master로 승격시켜 사용한다.

_NACL_ 과 _Security group_ 을 이용하여 프라이빗 서브넷에 생성 




