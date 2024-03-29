---
layout: default
title : 2. MSA 아키텍쳐 개요
description : "MSA 아키텍쳐 개요"
nav-order: 2
parent: MSA
---

## MSA의 특징을 나타내는 몇 가지 키워드
* 대규모 시스템
* 분산 처리 시스템
* 컴포넌트들의 집합
* 시스템 확장
-> 서비스 지향 아키텍쳐(SOA, Service Oriented Architecture)와 비슷하다

---

## SOA와 공통점
* 서비스 기능 단위로 시스템을 만든다.
* 각 시스템은 서로 표준화된 인터페이스를 통해 서비스를 통합한다.
* MSA : SOA 설계를 따르며 발전된 아키텍쳐

## 서비스 간의 독립적인 구성
* 서로 의존도가 있으면 복잡도가 증가한다. -> 하나의 서비스가 문제가 생기면 연쇄적 장애가 발생한다 : 느슨한 결합(loosely coupled) 유지
* 각각 독립된 저장소가 필요하다. -> 데이터 저장소가 공유되면 데이터 저장소가 장애 지짐이 될 수 있다.
* 서비스는 규모를 잘 고려해야 한다. 너무 작으면 관리해야하는 서비스가 많아지고, 너무 크면 하나의 서비스에 집중된다.
  
## 특징 정리
* 잘 분리된(fine grained) 마이크로서비스로 인한 탈중앙화
* 대규모 시스템을 위한 아키텍쳐
* 가벼운 네트워크 프로토콜
* 느슨한 결합(loosly coupled)
* 서비스 지향 아키텍쳐(SOA)

---

### 장점
* 독립성, 의존성 최소화
* 대용량 처리에 비교적 자유롭다.
* 시스템 장애에 견고함. 각각 독립되어 있기 때문에, 장애시 격리 가능하다.
* 배포 주기가 빠르다. CI/CD 필요
* 서비스 단위로 확장 가능하여 확장성이 좋다. <- 최고 장점
* 사용자 반응에 민첩하게 대응 가능하다. 서비스 분리 결합이 비교적 자유롭다.

### 단점
* 개발 난이도가 높다. DB트랜잭션 사용이 어렵고, 사용시 정합성을 맞추기 어렵다.
* 데이터 통합을 위하여 표준화된 인터페이스를 사용해야 하고, 커넥션 맺는 비용이 비싸다. 네트워크는 신뢰도가 낮고, 지연이 발생한다.
* 커넥션 풀 설정시 반드시 connection timeout과 read timeout을 고려해야 한다. 직렬화/역직렬화에도 비용이 발생한다.
* 운영 난이도가 높다.