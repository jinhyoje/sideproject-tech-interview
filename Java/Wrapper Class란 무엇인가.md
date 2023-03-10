# Wrapper Class란?

- 8개의 기본 타입에 해당하는 데이터를 객체로 포장해 주는 클래스를 래터 클래스라고 한다.
- 래퍼클래스는 각각의 타입에 해당하는 데이터를 인수로 전달받아, 해당 값을 가지는 객체로 만들어 준다.
- java.lang 패키지에 포함되어 있다.
- 대부분 기본 타입의 첫 글자만 대문자로 바꾼 형태지만, int, char은 Integer, Charater이니 주의

#### Boxing(박싱) vs Unboxing(언박싱)


- 기본 타입과 래퍼 클래스는 상호 변환이 이루어지는데, 이러한 과정을 각각 boxing, unboxing라고 한다.
  - boxing(박싱) : 기본 타입에서 wrapper 클래스로 전환
  - unboxing(언박싱) : wrapper 클래스 객체를 기본 타입으로 전환

#### 오토 박싱(AutoBoxing)과 오토 언박싱(AutoUnBoxing)

- JDK 1.5부터는 박싱과 언박싱이 필요한 상황에서 자바 컴파일러가 이를 자동으로 처리해 준다.
- 자동화된 박싱과 언박싱을 오토 박싱(AutoBoxing)과 오토 언박싱(AutoUnBoxing)이라고 부른다.

```
Integer num = new Integer(17); // 박싱
int n = num.intValue();        // 언박싱
System.out.println(n);

Character ch = 'X'; // Character ch = new Character('X'); : 오토박싱
char c = ch;        // char c = ch.charValue();           : 오토언박싱
System.out.println(c);
```
