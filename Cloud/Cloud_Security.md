# 클라우드보안

기밀성(Confidentiality)
- 인가된 사용자에게만 허가
  
무결성(Integrity)
- 손실, 변경되지않은 데이터

가용성(Availability)
- 서비스가 준비된 상태인가

온프레미스에 비해 보안에 드는 비용이 낮음 


공동 책임 모델: AWS와 사용자간의 책임공유

하드코딩 금지 

보안사고를 대비하기 위해 백업 필수

AMI Baking

 - Full Baking - AMI + Userdata 모두 설계되어있음, 내가 원하는 AMI 만들기에도 유리함
 - Half Baking 
 - Raw Baking - 모든설계를 내가 해야함

CloudTrail -> S3 저장

CloudWatch Logs



AWS SSM(Systems Manager)
다수의 EC2 운영 및 애플리케이션, 보안관리, 패치 관리, 명령어 실행 등


CloudFormation

반복 배포하는 인프라는 자동으로 생성가능

AWSConfig 

규정 준수, 미준수 적용

미준수에 대해 수동 또는 자동으로 보정가능


AWSGuardDuty

지능형(머신러닝) 위협 탐지 서비스

### AWS Shield & WAF

DDoS 공격 - 서비스 중단을 목적으로 1시간 이내의 짧은 시간에 대량의 트래픽을 보내는 공격

DDoS를 완화 시킬 수 있는 서비스



WebACL을 구성하여 규칙 생성 


### SSM

키페어 관리 불필요 SSh 포트 불필요
