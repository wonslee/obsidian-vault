# What



# Why

## [[Spring]] vs Spring Boot

의존성 설정의 편리함 (e.g. XML -> build.gradle)

프로퍼티 설정. Configuration -> .yml OR .properties

어노테이션(`@SpringBootApplication`)

스프링 부트는 **내장된 서버**(내장 [[Tomcat]], Jetty, Undertow)를 제공하여 별도의 서버 설정 없이 애플리케이션을 실행할 수 있습니다. 

배포를 위해 War 파일을 생성해서 Tomcat에 배포할 필요 없으며, JAR 파일에는 모든 의존성 라이브러리가 포함되어 있어 외부 서버 없이도 애플리케이션을 실행할 수 있습니다. 이는 애플리케이션의 배포와 관리를 간편하게 만들어 줍니다.

# How