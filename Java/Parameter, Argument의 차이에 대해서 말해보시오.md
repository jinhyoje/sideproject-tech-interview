- ### parameter는 매개변수를 뜻하며 함수와 메소드 입력 변수 명을 의미한다.

- ### argument는 전달인자 또는 인자를 뜻하며 함수 혹은 메소드를 호출할 때 전달 혹은 입력되는 실제 값을 뜻한다.

```
public int sum(int a, int b) { //---sum 매서드 호출시 입력 되는 a와 b 는 parameter
  int sum = 0;
  for(int i=a; i<=b ;i++) {
    sum += i;
  }
  return sum;
}

sum(1,10) //---sum 매서드 호출시 입력 되는 1과 10은 argument
```

## 오라클 공식 홈페이지에 나와있는 parameter, argument의 정의
https://docs.oracle.com/javase/tutorial/java/javaOO/arguments.html
