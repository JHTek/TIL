## ELB

트래픽을 배분하는 기능

- 상태확인을 통한 애플리케이션 고가용성
- HTTPS 지원
- 애플리케이션자동크기조정지원


ALB (Application Load Balancer)   
온프레미스의 L7역할   
추가적인 보안그룹 가능



NLB (Network Load Balancer)   
온프레미스의 L4역할

날 마다 트래픽이 바뀔 때 쓸 수 있는게 오토스케일링   
클라이언트의 요청 수요가 많아지면 EC2를 늘림   
가용성이 향상되고 비용이 절감되는 효과   
오토 스케일링 정책 생성가능   

Scale-up vs Scale-down : 수직 확장 ex) micro -> samll   
Scale-out vs Scale-in : EC2 개수 조절    
비용이 허용되는 선으로 MAX지정
가용성 기준으로 MIN지정
