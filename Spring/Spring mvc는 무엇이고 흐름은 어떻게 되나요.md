- MVC 패턴은 코드의 재사용에 유용하며, 응용 프로그램 개발에 소요되는 시간을 줄여주는 효과적인 설계 방식을 말합니다.
- 스프링은 MVC 2 패턴방식을 사용하고 있음.

구성요소로는 Model, View, Controller가 있음
모델은 핵심적인 비즈니스 로직을 담당하여 데이터베이스를 관리하는 부분, 
뷰는 사용자에게 보여주는 화면, 
컨트롤러는 모델과 뷰 사이에서 정보 교환을 할 수 있도록 연결시켜주는 역할을 합니다.

1. client로부터의 request가 들어오면, DispatcherServlet 이 HandlerMapping으로 @Controller로 스캔된 url과 mapping 되고 빈 controller 가 return 됩니다.
2. DispathcerServlet은 동일한 방식으로 request를 처리하기 위해 adapter로 위임하고, @RequestMapping을 통해 매칭된 메소드를 실행합니다.
3. 이 과정에서 dependency injection으로 주입된 service를 실행하고, db에 접근해야 한다면, repository에서 db와 요청된 로직을 수행합니다.
4. controller는 수행된 결과를 DispatcherServelt에게 view 정보와 수행된 결과를 전달하고 ModelAndView 형태로 전달합니다.
5. DispathcerServlet 은 반환된 view 정보를 viewResolver 에게 전달하고 해당하는 view jsp를 반환 받습니다.
6. 'DispathcerServlet`은 반환받은 view 정보를 render하고, view 를 생성하고 응답을 마치게 됩니다.

하지만, @ResponseBody가 붙어있는 RestController에서는 동작방식이 바뀌게 된다.

5. @ResponseBody 가 있다면 위 과정에서 viewResolver를 호출하지 않고, HttpMessageConverter가 동작하게 됩니다.
6. 문자열이면 StringMessageConverter가 호출되고, json형태라면 MappingJackson2HttpMessageConverter 가 호출되어서 response body에 응답으로 반환되게 됩니다.
