Stored XSS

Reflected XSS

DOM XSS: DOM의 일부로 실행됨으로서 

XSS 

BeEF 해킹도구와 연결하여 피해자의 쉘을 딸 수 있음

1. XSS 악성코드 작성

보고서용 악성코드
```HTML
<script>alert(123)</script>
```

2. 입력값이 출력되는 포인트를 찾는다.
3. 출력되는 포인트의 전,후 문법확인
4. 삽입 후에도 정상적으로 로딩될 수 있도록 스크립트 수
```HTML
""><원하는 스크립트><""
```
