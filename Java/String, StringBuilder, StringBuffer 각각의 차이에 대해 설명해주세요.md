- 문자열을 다루는 자료형 클래스
- 사용 목적에 따라 쓰임새가 다르다. 


# StringBuffer / StringBuilder 클래스
- 문자열을 연산(추가하거나 변경) 할 때 주로 사용하는 자료형이다.
  - String 자료형은 +연산이나 concat()메소드로 문자열을 이어붙일 수 있다.
  - +(덧셈) 연산자를 이용해 문자열을 결합하면, 내용이 합쳐진 새로운 인스턴스를 생성하게 되어 공간의 낭비뿐만 아니라 속도도 매우 느려지게 된다.


# String vs (StringBuffer, StringBuilder) 비교
1. 문자열 자료형의 불변과 가변
- #### String은 불변
    - 기본적으로 자바에서는 String 객체의 값은 변경할 수 없다.
    - 이는 한번 할당된 공간이 변하지 않는다고 해서 '불변(immutable)' 자료형 이라고 불린다.
- #### StringBuffer / StringBuilder 는 가변
    -  객체의 공간이 부족해지는 경우 버퍼의 크기를 유연하게 늘려주어 가변(mutable)적이라는 차이점이 있다.
    - 두 클래스는 내부 Buffer(데이터를 임시로 저장하는 메모리)에 문자열을 저장해두고 그 안에서 추가, 수정, 삭제 작업을 할 수 있도록 설계되어 있다.

2. 문자열 자료형의 값 비교
- #### String 객체는 간단하게 equals() 메서드를 통해 문자열 데이터 동등 비교가 가능하다.
- #### toString() 으로 StringBuffer/StringBuilder 객체를 String 객체로 변환하고 난 뒤에 equals 로 비교를 해야 한다.

### 결론
- StringBuffer나 StringBuilder을 생성할 경우 buffer의 크기를 초기에 설정해줘야하는데 이러한 동작으로 인해 무거운 편에 속한다.
- 그리고 StringBuffer나 StringBuilder에서 문자열 수정을 할 경우에도 마찬가지로 버퍼의 크기를 늘리고 줄이고 명칭을 변경해야하는 내부적인 연산이 필요하다.
- 문자열 추가나 변경등의 작업이 많을 경우에는 StringBuffer를, 문자열 변경 작업이 거의 없는 경우에는 그냥 String을 사용

# StringBuffer vs StringBuilder 차이점
- 멀티 쓰레드(Thread)에서의 안전(safe)
- 두 클래스는 문법이나 배열구성도 모두 같지만, 동기화(Synchronization)에서의 지원의 유무가 다르다.

1. StringBuffer 클래스는 쓰레드에서 안전하다. (thread safe)
   - StringBuffer는 동기화를 지원하여 멀티 스레드 환경에서도 안전하게 동작할 수 있다.
   - web이나 소켓환경과 같이 비동기로 동작하는 경우가 많을 때는 StringBuffer를 사용
2. StringBuilder 클래스는 쓰레드에서 안전하지 않다.(thread unsafe) 
  - StringBuilder는 동기화를 지원하지 않는다.
  - 속도면에선 StringBuffer 보다 성능이 좋다.

