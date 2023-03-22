#### Hash란?
- 자료를 일정한 형식의 식별 값으로 나타내기 위한 노력의 산물
- 자료를 빠르게 찾을 수 있도록 도움

#### Hash의 활용
- Hash Function
    - 특정 문자열을 식별 가능한 정수로 변환
    - 정해진 input을 넣으면 반드시 일관된 값이 되어야 한다.
    - 입력을 해시 값으로 변환하는 과정을 통틀어 해싱이라고 한다.

# HashMap이란?
- HashMap의 Hash는 자료를 조회하는 방법과 관련이 있고 Map은 자료의 특성과 관련이 있다.
- Key-Value쌍 하나만 넣는 것이 가장 기본적이며, 배열의 한 요소를 bucket이라고 한다.
- HashMap에서의 key는 unique해야한다.(key는 중복 불가, value는 중복 가능)

### Object로 부터 상속 받는 두 가지 메서드(method)
#### 1. int hashCode()
- Hash Function의 일종
- hashCode 메서드가 반환하는 해시값을 사용하면 그 값에 매핑 되어있는 인스턴스들에게 한 번 만에 접근할 수 있게 된다.
- hashCode 메서드를 통해 생성되는 Hash 값이 같은 인스턴스가 여러 개 있다면 동일한 Hash에 여러 개의 인스턴스가 매핑된다.

#### 2. boolean equals(Object)
- 여러 개의 인스턴스 중에 우리가 찾는 인스턴스를 찾아내기 위해서 두 인스턴스를 비교하는 method 사용

```
// HashMap 생성
Map<String, Integer> map = new HashMap<String, Integer>();

// HashMap 데이터 삽입
map.put("사람", 1);

// HashMap 데이터 추출
map.get("사람")
```

