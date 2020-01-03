---
layout: post
title: "DBMS 아키텍처"
subtitle: "DBMS 아키텍처 기초"
categories: database
tags: dbms
comments: true
---

### DBMS는 우리와 똑같이 일한다!
---

<img src="/assets/img/dbms_architecture_easy.png">

```우리가 일하는 방식```
1. 업무지시를 받는다.
2. 어떤 업무인지 분석하고 이해한다.
3. 여러 방안을 생각해본다.
4. 회사 자료를 살펴보면서, 가장 효율적인 방법을 찾는다.
5. 선정한 방식으로 업무를 수행한다.


---
<img src="/assets/img/dbms_architecture.png">


```DBMS 동작원리```
1. SQL문 실행한다.
2. SQL문을 분석하고, 오류를 찾는다.
3. 여러 실행 계획을 세운다.
4. 비용을 평가하여 가장 효율적인 방법을 선정한다.
5. 선정된 방식으로 SQL이 실행된다.


- 쿼리 평가 엔진
  - 파서
    - 구문 오류 찾기(서류전형)
  - 옵티마이저
    - 플랜 계획
    - 비용 평가
    - 실행 계획 선정
  - Catalog Manager
    - DB에 남아있는 통계정보
    - 실시간 Update가 안됨
    - Batch와 같은 대량 변경 후 ```ANALYZE```로 업데이트 해야함.
<br/><br/>
- Access Method
- Buffer Manager
  - 데이터 캐시
    - Disk I/O없이 검색 속도 향상
  - 로그 버퍼
    - Update시 로그 버퍼에 우선 기록
    - ```Commit```하면 Disk에 기록
      - 데이터 삽입 시 실패하면 복구를 하기 위해서
    - 실제 Update 수행
  - 워킹 메모리
    - Sort, Hash 등의 연산 작업에 사용
    - 부족 시 Disk 사용(느려짐)
<br/><br/>
- Disk Manager
  - 저장장치를 효율적으로 사용
<br/><br/>
- Recovery Manager
  - 실패 시 데이터 유지
<br/><br/>
- 동시 실행 제어
  - Transaction
    - SQL이 실행되는 단위
  - Lock