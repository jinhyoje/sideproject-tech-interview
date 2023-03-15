# DTO란?
- DTO(Data Transfer Object, 데이터 전송 객체)는 프로세스 간에 데이터를 전달하는 객체이다.
- DTO기법을 사용하면 중요한 정보를 노출시키지 않고 두 시스템(API와 서버 등)간 통신을 원활하게 촉진할 수 있다.

### DTO 사용 이유
1. Entity 내부 구현 캡슐화 가능
- Entity는 도메인의 핵심 로직과 속성을 가지며, 실제 DB 테이블과 매칭되는 클래스이다.
- 따라서 Entity가 Getter, Setter를 가진다면 controller와 같이 비즈니스 로직과 큰 상관없는 곳에서 자원의 속성이 실수로 변경될 가능성이 있다.
- DTO를 사용하여 Entity를 UI계층에 노출시키지 않아 보안상으로도 바람직하다.

2. 화면에 필요한 데이터 선별 가능
- 다양한 API 스펙에 따라 필요한 데이터만 포함된 DTO를 만들어 request/response 함으로써 전송 속도 개선 가능

3. 순환참조 방지
- 양방향 매핑된 Entity를 controller에서 response로 return하면 Entity가 참조하는 객체가 지연 로딩되면서 순환참조에 빠질 수 있다.
- 이때, DTO를 return하여 순환참조를 방지할 수 있다.

4. validation 코드와 모델링 코드 분리 가능
- @NotNull, @NotEmpty, @NotBlank 같은 validation 코드를 DTO에 정의함으로써 Entity에서는 모델링과 비즈니스 로직에 집중할 수 있다.


