# Annotation이란?

### 자바 Annotation

- 자바에서 어노테이션은 사전적의미로는 **주석**이라는 뜻을 가지고 있다.
- 자바의 어노테이션은 소스코드에 추가해서 사용할 수 있는 메타 데이터의 일종이다
  - 메타 데이터 : 애플리케이션이 처리해야할 데이터가 아니라 **컴파일 과정과 실행 과정**에서 코드를 어떻게 처리해야하는지를 알려주기 위한 추가 정보이다.
- 자바의 어노테이션은 보통 '@' 기호를 앞에 붙여서 사용한다.
- JDK 1.5 버전 이상에서부터 사용가능하며, 자바 어노테이션은 클래스 파일에 임베드되어 컴파일러에 의해 생성된 이후 JVM에 포함되어 동작한다.

#### 자바 어노테이션의 용도

- 컴파일러에게 코드 작성 문법 에러를 체크하도록 정보 제공
- 소프트웨어 개발 환경이 빌드나 배포시 코드를 자동으로 생성할 수 있도록 정보 제공
- 런타임에 특정 기능을 실행하도록 정보를 제공

### 스프링에서 자주 사용하는 Annotation

- Annotation은 클래스와 메서드에 추가하여 다양한 기능을 부여하는 역할을 한다.
- Annotation을 통하여 코드량이 감소하고 유지보수하기 쉬우며, 생산성이 증가된다.

#### 스프링의 대표적인 Annotation과 역할

1. @Component
- 개발자가 생성한 class를 spring의 Bean으로 등록할 때 사용하는 Annotation

2. @ComponentScan
- spring Framework는 @Component, @Service, @Repository, @Controller, @Configuration 중 1개라도 등록된 클래스를 찾으면, Context에 bean으로 등록합니다. @ComponentScan Annotation이 있는 클래스의 하위 Bean을 등록 될 클래스들을 스캔하여 Bean으로 등록해줍니다.

3. @RequestHeader,  @RequestParam, @ResponseBody, @RequestBody
4. @RequestMapping, @GetMapping, @PostMapping

   ```
   @Controller                   // 이 Class는 Controller 역할을 합니다
   @RequestMapping("/user")      // 이 Class는 /user로 들어오는 요청을 모두 처리합니다.
   public class UserController {
       @RequestMapping(method = RequestMethod.GET)
       @ResponseBody
       public String getUser(@RequestParam String nickname, @RequestParam(name="old") String age {
           // GET method, /user 요청을 처리
           // https://naver.com?nickname=dog&old=10
           User user = new User();
           user.setName(nickname);
           user.setAge(age);
           return user;
       }
   }
   ```

#### Lombok의 대표적인 Annotation과 역할
- Lombok은 코드를 크게 줄여주어 가독성을 크게 높힐 수 있는 라이브러리이다.

1. @Setter
- Class 모든 필드의 Setter method를 생성해줍니다.

2. @Getter
- Class 모든 필드의 Getter method를 생성해줍니다.

3. @AllArgsConstructor
- Class 모든 필드 값을 파라미터로 받는 생성자를 추가합니다.

4. @NoArgsConstructor
- Class 기본 생성자를 자동으로 추가해줍니다.
