[ 가비지 컬렉션(Garbage Collection)의 과정 ]
- 가비지 컬렉션(GC)은 메모리를 정리하는 과정입니다. 그렇기 때문에 일반적으로 메모리의 사용을 중단한 채로 진행이 되어야 합니다. 
JVM은 GC를 실행하기 위해 애플리케이션의 실행을 멈추는 stop-the-world를 먼저 실행하게 됩니다. 
stop-the-world를 실행하면 GC를 실행하는 쓰레드를 제외한 모든 쓰레드가 작업을 멈춥니다. 
그리고 GC가 끝나면 다시 작업을 재개합니다.<br>

기본적으로 JVM의 메모리는 총 5가지 영역(class, stack, heap, native method, PC)으로 나뉘는데, GC는 힙 메모리만 다룹니다.
- 일반적으로 다음과 같은 경우에 GC의 대상이 됩니다.
  - 객체가 NULL인 경우 (ex. String str = null)
  - 블럭 실행 종료 후, 블럭 안에서 생성된 객체
  - 부모 객체가 NULL인 경우, 포함하는 자식 객체
<br>

- GC의 작업은 Young 영역에 대한 Minor GC와 Old 영역에 대한 Major GC로 구분됩니다.
  - Young 영역: 새롭게 생성한 객체들이 위치한다. 대부분의 객체는 금방 접근 불가능한 상태가 되기 때문에, 많은 객체가 Young 영역에 생성되었다가 사라진다.
  - Old 영역: Young 영역에서 계속 사용되어 살아남은 객체가 복사되는 영역이다. Young 영역보다 크게 할당되며, 더 적은 GC가 발생한다.
<br>

- Young 영역은 또 1개의 Eden 영역과 2개의 Survivor 영역으로 구성되는데, Young 영역에 대한 GC는 다음과 같이 작동한다.

1. 새로운 객체가 Eden 영역에 생성됨
2. Eden 영역에 GC가 동작하고, 그 중에서 살아남은 객체가 Survivor0으로 이동함
3. 2번의 동작이 반복되어 Survivor0이 꽉차게 됨
4. Survivor0 영역에 GC가 동작하고, 살아남은 객체들은 Survivor1으로 이동하고 Survivor0을 비우게 됨
5. (2개의 Survivor 영역 중 1개는 반드시 비어있어야 됨)
6. 위의 동작들이 반복되어 특정 횟수만큼 살아남은 객체는 Old 영역으로 이동함

그리고 Old 영역이 가득차서 Survivor 영역에서 Old 영역으로 이동이 불가능할 때 Old 영역에 대한 GC(Major GC)가 실행됩니다.
