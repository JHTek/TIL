#  XSS

Stored XSS: 공격자가 악성코드를 DB에 삽입하는 공격

Reflected XSS: 공격자가 입력하는 정보가 DB에 저장되지 않고 바로 같은 페이지에서 피해발생 

DOM XSS: DOM으로 실행됨으로 브라우저 자체에서 악성스크립트 실행 

BeEF 해킹도구와 연결하여 피해자의 쉘을 딸 수 있음

1. XSS 악성코드 작성

보고서용 악성코드 - alert로 스크립트 실행 여부 확인
```HTML
<script>alert(123)</script>
```

2. 입력값이 출력되는 포인트를 찾는다.
3. 출력되는 포인트의 전,후 문법확인
4. 삽입 후에도 정상적으로 로딩될 수 있도록 스크립트 수
```HTML
""><원하는 스크립트><""
```

[XSS Cheet Sheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)

