# 컬렉션 프레임워크(Collection Freamwork) 란?
- 다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 의미
- 데이터를 저장하는 자료 구조와 데이터를 처리하는 알고리즘을 구조화하여 클래스로 구현해 놓은 것을 말한다.
- 자바의 인터페이스를 사용하여 구분된다.

### 컬렉션 프레임워크의 주요 인터페이스
1. 순서가 있는 목록인 List형
2. 순서가 중요하지 않은 목록인 Set형
3. 먼저 들어온 것이 먼저 나가는 Queue형
4. KEY-VALUE의 형태로 저장되는 Map형

*  List와 Set, Queue 인터페이스는 모두 Collection 인터페이스를 상속받지만, 구조상의 차이로 인해 Map 인터페이스는 별도로 정의된다.

### 컬렉션 인터페이스의 특징
1. List 인터페이스
- 중복되는 데이터를 저장해야 할 때, 배열에 들어간 순서를 유지하고 싶을 때 사용한다.(중복 o, 순서 o)
- ArrayList, LinkedList, Vector, Stack 

2. Queue 인터페이스
- List와 유사
- LinkedList, PriorityQueue

3. Set 인터페이스
- 순서가 필요 없고, set에 저장될 데이터가 중복이 되면 안 될 때 사용한다.(중복 x, 순서 x)
- HashSet, TreeSet, LinkedHashSet(순서 보장)

4. Map 인터페이스
- 데이터를 저장할 때, key와 value 쌍으로 저장하고 싶을 때, 그리고 key를 중복 저장하고 싶지 않을 때 사용한다 (key 중복 x, value 중복 o, 순서 x)
- Hashtable, HashMap, TreeMap

