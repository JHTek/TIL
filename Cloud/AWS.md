# Amazon Web Services

Internet에서 IT 리소스를 On-demand로 서비스를 제공받을 수 있음

 

### 클라우드 컴퓨팅 특징

클라우드 컴퓨팅 VS 온프레미스  

- 유연함
  - 서버의 자원과 수를 설정에서 쉽게변경
  - 장애를 예상한 설계
- 초기 비용 낮음
  - 종량요금제
- 운용 비용 낮음
  - DC를대신 관리 해주기 때문에 관리 노력 없음
- 가시적인 접근성
- AWS의 어플리케이션을 사용해 별도의 개발 필요없음
- 독립성은 낮은 것이 단점
  
### 클라우드컴퓨팅 서비스모델
IaaS - 인프라   
PaaS = 인프라, 플랫폼   
SaaS - 인프라, 플랫폼, 애플리케이션   

### AWS Global 인프라

[AWS 글로벌 인프라](https://aws.amazon.com/ko/about-aws/global-infrastructure/)   

**D**ata **C**enter < **A**vailability **Z**one < Rigeon

원하는 지역에 원하는 서비스를 배포가능하다.   

리전 선택의 기준
- 지연시간
  - 내 주요 클라이언트들의 접근이 용이한가?
- 법적인 문제
- 가용서비스
  - 새로운 서비스가 사용가능한 리전인가?
- 비용

**D**ata **C**enter < 엣지로케이션   
해시 전용공간

