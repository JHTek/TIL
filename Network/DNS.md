# DNS

도메인을 IP주소로 변환하여 통신하는 수직적인 체계

가짜 사이트로 유도하는 파밍공격(DNS 캐시 포이즈닝(cache poisoning) 공격)에 사용 되기도 함

정상도메인 만으로도 공격이 가능 

DNS 스푸핑, DNS 하이재킹으로 가짜 DNS서버를 사용하도록 유도

C:\Windows\System32\drivers\etc 에 존재하는 hosts파일에 구조가 있음

ipconfig /displaydns 를 통하여 DNS Cache Table 확인가능 

## DNS Name Resolution

Domian을 보내 DNS서버에 IP를 요청하면 DNS서버가 알려줌 

Root Name Server 가 존재    
비영리 단체 ICANN이 관리 