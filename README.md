## 스프링부트2.2.0부터 application/json;charset=UTF-8의 charset이 deprecated 된다. ##
  - Content-Type 으로 전달되는 속성값은 1가지 성질만 가진다.
  - MediaType.APPLICATION_JSON_UTF8 의 경우 application/json; charset=UTF-8 로 속성 2개를 가지고 있다.
  - Content-Type: application/json;charset=UTF-8 요청에 대해 Content-Type: application/json 으로 응답한다.
  - honeymon.io님 블로그 참조 http://honeymon.io/tech/2019/10/23/spring-deprecated-media-type.html

## Why? ##
<img src="https://user-images.githubusercontent.com/24876345/144778474-8cd2f5cd-ec9e-4dd2-b985-354e083541c4.jpg" width="200" height="300"/>

- 이 원인은 크롬 브라우저와 같이 주요 브라우저들이 사양을 준수하고 charset=UTF-8로 인코딩되는 특수한 문자들을 올바르게 해석해주므로 
정확히는 스프링 5.2부터, 스프링 부트의 경우 2.2.0부터 응답에 이를 포함시키지 않게 되었다.
- minkukjo 블로그 참조 https://minkukjo.github.io/framework/2020/06/18/Spring-120/


## SpringBoot utf8 설정 ##
- 스프링에서 CharacterEncodingFilter를 @Bean으로 등록한뒤 UTF-8 설정
- But 스프링부트는 기본적으로 CharacterEncodingFilter가 등록되어있기 때문에 Bean 등록 필요없이 propertie에 등록한다.
````java
spring.http.encoding.charset=UTF-8
spring.http.encoding.enabled=true
spring.http.encoding.force=true
````
