../../../../etc/passwd

/etc/shadow - root권한 만 가능 웹서버를 root로 실행하면 shadow파일 유출 될 가능성 높음 

대응방안: tomcat apache재설치... 설정 하나하나 확인해도 되지만 자원이 너무 많이드는 작업임

Exploit db - 버전에 맞는 취약점 사이트

"../" -> "" 필터링 우회법   
..././ -> .(../)./ -> ../

asdf.jsp%00.png -> %00은 종결문자로 asdf.jsp로 공격가능 (하위버전 리눅스 취약점)

~bash.history

---

대응방안
파일명과 경로명을 DB에서 관리
필터링
다운할 때 권한 검사

