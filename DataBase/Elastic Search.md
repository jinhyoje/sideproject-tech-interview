# Elastic Search

**Elastic Search란?**

- Apache Lucene( 아파치 루씬 ) 기반의 Java 오픈소스 분산 검색 엔진

**루씬이란?**

- 자바 기반의 고성능 정보 검색 라이브러리 / 검색 엔진 x

**왜 Elastic Search를 사용하나요?**

- 설치와 서버 확장이 매우 편리

**ES vs RDBMS(데이터 구조)**

- index - database / Shard - Partition / Type - table / Document - Row / Field - Column / Mapping - Schema / Query DSL - SQL

**Elastic Search 특징**

- REST API를 통해 데이터 조작
- NoSQL이며 분산처리를 통해 실시간성 빠른 검색 가능 → 기본적으로 검색엔진이지만 MongoDB나 Hbase같은 대용량 스토리지로도 활용 가능
- **장점**
    - 오픈소스
    - 전문 검색
    - 통계 분석 가능 → 비정형 로그 데이터 수집하여 통계 분석 활용 / Kibana 연결하면 실시간으로 로그 분석하고 시각화 가능
    - Schemaless → 정형화되지 않은 문서도 자동 색인하고 검색 가능
    - RESTful API → HTTP 헤더와 URL만 사용하여 다양한 형태의 요청 가능한 HTTP 프로토콜 최대한 활용하도록 고안된 아키텍처
    - (Data CRUD - ES → SELECT - GET / INSERT - PUT / UPDATE-POST / DELETE-DELETE)
    - Multi-tenancy → 서로 상이한 index라도 검색 필드명만 같으면 여러 인덱스 한번에 조회가능
    - Document-Oriented → 여러 계층 구조로 문서 저장 가능 / 이런 계층 구조의 문서도 한번의 쿼리로 쉽게 조회 가능
    - 역색인(역 인덱스 ; inverted index) : 단어로 해당 페이지 탐색
    
    - 확장성(**Scale out**) → 분산 구성 가능 / 분산 환경에서 데이터를 shard라는 단위로 나눔
- **단점(사용시 주의점)**
    - 완전 실시간 x → 색인 데이터는 1초 뒤에 검색 가능 → 내부적으로 commit과 flush 과정이 있기 때문(commit과 flush 있음)
    - Transaction Rollback 지원 x → 전체적인 클러스터 성능 향상을 위해 시스템적으로 비용 소모가 큰 롤백과 트랜잭션 지원하지 않음(Rollback 지원 x)
    - 데이터 업데이트 제공 x → 기본적으로 제공하지 않기 때문에 delete/insert를 추가 작업해야함 → 데이터 불변성(es 자체를 건드려야하는 건지 아니면 코드를 건드려야하는 건지)
