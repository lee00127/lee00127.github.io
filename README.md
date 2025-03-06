# 이찬영 (27) Junior White Hacker.




## Introduction.

---

포렌식과 네트워크 보안에 기술에 대해 관심을 가지고 공부하고 있는 정보보안 전문가입니다.

### **서비스가 안정적으로 운영되는 것에 대해 고민하고 기여하고자 합니다.**

사내 신규 MSA 프로젝트가 진행되던 초기에 많은 트래픽을 대응할 수 있는 샤딩 구현과 분산 트랜잭션의 데이터 일관성을 보장하는 방법에 대해 기술 검증를 수행하고 발표하였습니다. 

사내 레디스 클러스터의 안정적인 운영에 기여하기 위해 사내 오거나이저 제도에 참여하여 레디스의 전반적인 부분을 다루는 스터디를 진행하였으며 관련 문서를 작성하였습니다.

## Work Experience.

---

### **카카오스타일**

### **2023.05 ~**

**지그재그 셀러, 카카오스타일 내 스토어홈 지면 전시 서비스 개발, 운영 및 개선 (2023.05 ~)**

- TTI 개선 프로젝트에 참여하여 팀 내 전시 지면의 ATF, PLP, CLP 등 API 응답 레이턴시 개선 작업 진행
    - 레이턴시 개선을 위해 I/O 횟수 최적화를 통해 P50 기준 80% 개선
    - ATF 조회 기능 레이턴시 개선을 위해 병렬 처리 및 중복 호출 제거로 P50 기준 30% 개선
- 기간별 집계 데이터를 조합하여 카테고리, 필터 및 상품 노출 제어 용도의 데이터 생성 배치 개발
- Server Driven UI 작업, AB 테스트 수행

### 이스트소프트

### **2021.07 ~ 2023.05**

**에이쁠 포인트 서비스 개발 (2022.09 ~ 2023.04) [[link]](https://apluspoint.co.kr/)**

사용자 출석, 이벤트 참여 활동 등에 따라 보상 포인트를 지급하는 서비스 설계 및 개발

- 네트워크 문제와 외부 서버의 재시도에 의한 중복 처리 방지를 위해 ID 기반의 멱등성 보장 로직 구현
- 사업팀을 통해 제시된 OKR 기준 MAU 대응을 위해 포인트 쓰기 부하 처리를 위한 샤딩 전략을 고려하였고 PoC를 통한 검증 후 실제 코드에 반영 및 테스트
- 외부 오퍼월 연동 및 쇼핑 제휴 포인트 적립을 위해 외부 제휴 API 연동 작업 수행

MSA로 구성된 프로젝트를 AWS 상에 운영 가능하도록 구축하는 작업을 수행하였으며 특히 Service Discovery의 SPoF 방지를 위해 Route53 레코드를 이용해 복제 구조를 구성

- AWS ECS Fargate에 컨테이너 배포 시 Eureka Registry Bean에서 등록하는 Private IP가 유효하지 않은 IP로 등록되어 라우팅이 되지 않는 문제를 해결하기 위해 해당 Bean을 생성하는 시점에 AWS Provide DNS를 접근하여 유효한 Private IP를 Lookup 후 설정하도록 구성

**AI Studio Perso v1.0 개발 (2021.10 ~ 2022.09) [[link]](https://studioperso.ai/)**

사용자의 텍스트나 PPT 포맷을 통해 음성을 생성하고 여러 영상 편집 기능을 제공하여 강의, 뉴스 등의 영상을 생성할 수 있는 AI Studio Perso 서비스 프로토타입과 1.0 버전 개발

- 단일 물리 서버로 구성되는 솔루션 안에서 쓰레드 세이프하지 않은 AI 모델 추론 서비스를 안정적으로 호출하기 위해 앞단의 스프링 서비스에서 인메모리 큐 기반의 동기화 구조 도입
- AI 추론 서비스가 장기간 작업을 수행하면서 GPU OOM으로 인한 서비스 장애가 발생한 원인 파악 후 모니터링을 통해 GPU 점유 메모리가 선형적으로 증가하는 것을 찾아 매 추론 작업 이후에 파이토치의 GPU 캐시를 초기화해 문제 해결

**업무용 메신저 Teamup 운영 & 버전 이관 작업 (2021.07 ~ 2021.11) [[link]](https://tmup.com/)**

SaaS / 구축 형태로 제공되는 B2B 업무용 메신저인 Teamup의 광주 보건 연구소 구축 사업 지원

- 동일 코드베이스를 사용하는 다른 고객사에게 영향을 미치지 않도록 별도의 프록시 서버를 구현하고 Nginx를 활용해 별도 알고리즘 모듈을 적용할 수 있도록 구성
- Teamup SaaS 버전에서 발생한 레디스 커넥션 누수로 인한 장애 원인을 분석하고 외주로 구현된 특정 API의 SSO 코드를 수정하여 문제 해결
- PHP 버전에서 제공하던 일부 기능을 자바 버전으로 언어 변경 후 이관하는 작업 수행

**기타 활동**

- [Spring4shell Vulnerability](https://lob-dev.tistory.com/83) 발생 당시 원인 분석 및 대응 방법을 작성 후 공유 및 취약점으로 인한 내부 프로젝트 영향도 식별
- 규칙없이 작성되던 HTTP API 규격 통일을 위해 HTTP API에 대한 공통 설계 규칙 문서 작성 기여
- 기술 조직 내 문제를 파악하고 해결과 역량 강화를 위한 로드맵 구성 / 기술 스터디를 주도하는 제도인 테크 오거나이저 - 레디스 부문에서 활동

### 나이스데이

### **2021.03 ~ 2021.07**

**Genie Music OTT 플랫폼 STAYG 백엔드 개발 (2021.05 ~ 2021.07)**

실시간 스트리밍과 VOD를 제공하는 OTT 서비스인 STAYG에서 시청자 투표, 쿠폰과 이미지 API를 개발

- 쿠폰 정보에 따른 아이템의 식별 값 중복 방지를 위해 UUID를 적용

**Genie Music 관리자 CMS 개발 (2021.03 ~ 2021.05)**

Genie Music에서 사용되는 관리자 CMS 기능 고도화 프로젝트에 참여하여 신규 API를 개발

## Other Experience.

---

### [게으른 개발자 컨퍼런스 1회](https://lazyconf.dev/)

### **2024.01.29**

게으른 개발자 컨퍼런스에서 **소비자 관점의 API 설계 패턴, 사례 훑어보기** 라는 주제로 발표하였습니다.

- **Link** : https://github.com/lazyconf-dev/2024-lazydevconf

### **MSA 환경에서 데이터 일관성을 보장하는 방법 (사내)**

### **2022.12.02**

MSA 기반 플랫폼을 개발하면서 필요했던 분산 트랜잭션과 시스템 개념, 크레오그래피 사가에 대한 간단한 이론과 PoC 결과를 정리하여 사내에서 발표하는 시간을 가졌습니다.

- **Link** : https://github.com/Lob-dev/PoC-Choreography-Saga-Pattern-Kotlin

### Tech Organizer : Database - Redis 부문 활동 (사내)

### **2022.11 ~ 2023.05**

이스트소프트에서 기술 조직 내 문제를 파악하고 해결하거나 구성원의 역량 강화를 위한 로드맵, 스터디 등을 진행하는 Sub Role인 Tech Organizer - Database 부문에서 활동하였습니다.

- 사내 Redis Cluster 지연 문제를 파악하고 Cluster 부하를 해소하기 위한 부분을 고려하고 있습니다.
- Redis Study를 진행하여 Redis를 비교 분석하고 Deep-dive하면서 주차 별 회고와 문서화를 병행하고 있습니다.

### **이스트소프트 익스턴십 백엔드 1기 코드 리뷰어 (사내)**

### **2022.05**

이스트소프트와 멋쟁이사자처럼이 함께 진행한 이스트소프트 백엔드 개발자 익스턴십 1기 과정에서 과제물 코드 리뷰를 진행하는 사내 리뷰어로 참여하였습니다.

### **내가 성장할 수 있었던 공부 방법 (충북대학교)**

### **2021.12.09**

- IT 동아리 학생들을 대상으로 개인적으로 지켜온 학습 방식을 공유하고 학생들의 질문에 대한 답변하는 시간을 온라인으로 진행하였습니다.
- **Link** : [https://lob-dev.tistory.com/entry/소소한-글-내가-성장할-수-있었던-공부-방법-발표-내용-공유](https://lob-dev.tistory.com/entry/%EC%86%8C%EC%86%8C%ED%95%9C-%EA%B8%80-%EB%82%B4%EA%B0%80-%EC%84%B1%EC%9E%A5%ED%95%A0-%EC%88%98-%EC%9E%88%EC%97%88%EB%8D%98-%EA%B3%B5%EB%B6%80-%EB%B0%A9%EB%B2%95-%EB%B0%9C%ED%91%9C-%EB%82%B4%EC%9A%A9-%EA%B3%B5%EC%9C%A0)

### **주니어 개발자의 학습 자료 정리**

### **2021.04.29 ~**

- Back-end 학습 시 난항을 겪었던 경험을 기반으로 취준생을 가이드하고자 시작한 사이드 프로젝트입니다.
- 학습했거나, 주변에서 추천을 받은 서적, 강의를 기반으로 개발 학습 로드맵을 작성하였습니다.
- **Link** : https://github.com/Lob-dev/Junior-Back-end-Developer-Concepts

### **JVM GC 기반 개념과 기본 GC 알고리즘 (사내)**

### 2021.04.27

- Reference Counting, Tracing Garbage Collection 개념과 JVM에 구현된 알고리즘에 대해 설명하고 Garbage Collector의 구성 요소인 Root Set, S-T-W, Reachability에 대해 사내에서 발표하는 시간을 가졌습니다.
- **Link** : [https://lob-dev.tistory.com/entry/Presentation-JVM-GC-기본-개념과-기본-GC-알고리즘](https://lob-dev.tistory.com/entry/Presentation-JVM-GC-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90%EA%B3%BC-%EA%B8%B0%EB%B3%B8-GC-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)

## E**ducation.**

---

### 한국방송통신대학교 컴퓨터과학과 학사 과정

### 2023.08 ~

- 한국방송통신대학교 컴퓨터과학과 분할정복독서모임 4기 (08.21~12/31)
- 한국방송통신대학교 컴퓨터과학과 분할정복독서모임 5기

### 동서울대학교 컴퓨터정보학과 전문학사 과정

### 2016.03 ~ 2020.02
