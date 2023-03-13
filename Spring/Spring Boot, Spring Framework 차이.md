# Spring Framework

자바 플랫폼을 위한 오픈소스 애플리케이션 프레임워크로서 간단히 스프링이라고도 불린다.

동적인 웹 사이트를 개발하기 위한 여러 가지 서비스를 제공하고 있다.

#### 장점

- 경량 컨테이너
- IoC(Invertion of Control: 제어 역행)
- DI(Dependency Injection: 의존성 주입)
- AOP(Aspect-Oriented Programming: 관점지향 프로그래밍)

# Spring Boot

스프링 부트는 **스프링 프레임워크를 사용하기 위한 설정의 많은 부분을 자동화**하여 사용자가 편하게 스프링을 활욯할 수 있도록 돕는다.

#### 차이점

#### 1. Dependency

스프링 프레임워크의 경우 dependency를 설정해 줄 때 설정 파일이 매우 길고, 모든 deoendency에 대해 버전 관리도 하나하나 해줘야 한다.

- 스프링 부트의 경우 쉽게 설정해준다.
- 버전 관리도 자동으로 해준다.
- Gradel을 사용하는 경우  build.gradle파일에 dependency를 추가해주면 스프링부트로 웹 개발을 할 때 필요한 모든 denpendency를 자동으로 추가하고 관리해준다.

#### 2. Configuration

Spring Framework의 경우 configuration설정을 할 때도 매우 길고, 모든 어노테이션 및 빈 등록 등을 설정해 줘야 한다.

- Spring Boot Framework는 application.properties파일이나 application.yml파일에 설정하면 된다.

### **Spring Boot의 강력한 AutoConfiguration**

- @SpringBootApplication

외부 라이브러리, 내장 톰켓 서버 등이 실행될 수 있다.

- @ComponentScan

@Component, @Controller, @Repository, @Service라는 어노테이션이 붙어있는 객체들을 스캔해 자동으로 Bean에 등록해준다.

- @EnableAutoConfiguration

@ComponentScan 이후 사전에 정의한 라이브러리들을 Bean에 등록해준다.

의존성들을 모드 스캔하며 조건에 따라 의존성을 주입해 준다.

#### 3. 편리한 배포

- Spring Boot Framework의 경우, Tomcat 이나 Jetty 같은 내장 WAS를 가지고 있기 때문에 jar 파일로 간편하게 배포할 수 있다.
