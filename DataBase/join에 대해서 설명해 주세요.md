JOIN은 데이터베이스 내의 여러 테이블에서 가져온 레코드를 조합하여 하나의 테이블이나 결과 집합으로 표현해 줍니다.

이러한 JOIN은 보통 SELECT 문과 함께 자주 사용됩니다.

연결하려면 테이블들이 적어도 하나의 컬럼을 공유하고 있어야 하는데 이 공유하고 있는 컬럼을 PK 또는 FK값으로 사용

1. INNER JOIN : 내부조인 ->교집합
2. LEFT JOIN : 부분집합
3. RIGHT JOIN : 부분집합

* OUTER JOIN : 외부조인 ->합집합
* 오라클은 OUTER JOIN있지만, MYSQL은 없어서 LEFT조인 + RIGHT조인