## 스프링부트 2.2.0부터 application/json;charset=UTF-8 charset이 deprecated 된다. ##
  - Content-Type 으로 전달되는 속성값은 1가지 성질만 가진다.
  - MediaType.APPLICATION_JSON_UTF8 의 경우 application/json; charset=UTF-8 로 속성 2개를 가지고 있다.
  - Content-Type: application/json;charset=UTF-8 요청에 대해 Content-Type: application/json 으로 응답한다.
  - http://honeymon.io/tech/2019/10/23/spring-deprecated-media-type.html

## Why? ##
이 원인은 크롬 브라우저와 같이 주요 브라우저들이 사양을 준수하고 charset=UTF-8로 인코딩되는 특수한 문자들을 올바르게 해석해주므로 
정확히는 스프링 5.2부터, 스프링 부트의 경우 2.2.0부터 응답에 이를 포함시키지 않게 되었다.
- https://minkukjo.github.io/framework/2020/06/18/Spring-120/
