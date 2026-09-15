# 장성재 | Backend Engineer

동시성·트랜잭션·DB 병목을 재현하고,  
데이터로 원인을 검증해 안정적인 백엔드 구조로 개선합니다.

Java / Spring Boot를 중심으로 백엔드를 개발하고 있습니다.  
기술을 많이 나열하기보다 **문제를 재현하고 → 원인을 분리하고 → 같은 조건에서 다시 측정하는 과정**을 중요하게 생각합니다.

<br>

## Tech

**Backend**  
`Java` `Spring Boot` `JPA/Hibernate` `MySQL` `Redis`

**Performance & Reliability**  
`k6` `Grafana` `Nginx`

**Also Used**  
`NestJS` `Node.js` `PostgreSQL/PostGIS` `Railway`

<br>

## Projects

### FANDROPS
**오픈런 트래픽에서 결제 정합성과 대기열 안정성을 다룬 팬덤 커머스 플랫폼**

5인 팀에서 **Payment / Event 영역 백엔드**를 담당했습니다.

- Redis ZSET + Lua 기반 대기열 / Rate Limiter 구현
- 외부 PG 호출과 DB 트랜잭션 경계를 분리해 커넥션 점유와 락 경합 완화
- 결제 승인·웹훅·상태 전이 흐름 구현 및 실패 시나리오 검토
- k6 부하 시나리오에서 상품 목록 **P95 16.35ms / 약 299 RPS** 측정
- 동시 주문 테스트에서 **오버셀 및 5xx 미발생 확인**
- 주요 아키텍처 의사결정을 ADR로 문서화

[Backend Repository](https://github.com/prgrms-aibe-devcourse/AIBE5_FinalProject_Team6_BE)  
[Architecture / ADR](https://github.com/jjang0617/fandrops-docs)

---

### LocalGuest
**현지인 가이드와 여행자를 연결하는 로컬 여행 매칭 플랫폼**

5인 팀 프로젝트에서 백엔드 성능과 데이터 정합성 개선을 중심으로 작업했습니다.

- VU 기반 부하 테스트의 변동성을 확인하고 `constant-arrival-rate`로 조건 고정
- `Page → Slice`, Count Query 제거, DTO Projection 적용
- 동일 조건 재측정에서 **p99 473ms → 350ms** 개선
- 복합 Unique 제약과 `ddl-auto=validate`로 DB 무결성 강화
- 멀티모듈 환경의 RedisTemplate 직렬화 충돌을 `@Qualifier` 기반 빈 격리로 해결

[Repository](https://github.com/changhyunmoon/LocalGuest)

---

### StarChaser
**현재 위치와 날씨를 기반으로 별 관측 가능성을 계산하는 사이드 프로젝트**

공공 기상·대기 데이터와 천문 알고리즘을 결합해  
별 관측 조건을 **Star-Index**로 제공합니다.

- `NestJS + PostgreSQL/PostGIS` 기반 백엔드 개발
- 외부 API 타임아웃과 **Stale Cache Fallback**으로 장애 전파 방지
- `ST_DWithin + GiST` 기반 위치 주변 관측 명소 탐색
- 단순 가중합의 한계를 확인하고 관측 불가 조건에 **0/1 Gate** 적용
- Railway + Supabase 환경에 테스터용 서버 배포

[Repository](https://github.com/jjang0617/StarChaser)

---

### Readle
**기술 아티클을 AI 맞춤형 퀴즈와 피드백으로 변환하는 개발자 학습 플랫폼**

Programmers AI 인턴 프로그램 2기 팀 프로젝트에서  
**AI 서비스 · 퀴즈 엔진 백엔드**를 담당했습니다.

- Claude API 기반 퀴즈 생성·주관식 채점·오답 피드백 구현
- 퀴즈 생성 중복 요청에 대한 동시성 제어
- AI 채점용 실행 자원과 타임아웃을 분리해 외부 API 지연 영향 제한
- AI 응답 JSON 파싱 예외 처리 및 퀴즈 품질 검증 로직 구현
- 외부 AI 호출과 DB 작업의 트랜잭션 경계를 분리해 리소스 점유 최소화

[Backend Repository](https://github.com/Programmers-Intern-Program/INT2-Readle-Team02-BE)  

<br>

## What I Focus On

- **Concurrency & Consistency**  
  동시 요청 상황에서도 재고·결제·상태 전이가 깨지지 않도록 설계합니다.

- **Performance Analysis**  
  부하 조건을 먼저 고정하고, 병목을 분리한 뒤 동일 조건에서 다시 측정합니다.

- **External API Reliability**  
  PG·기상 API·LLM처럼 느리거나 실패할 수 있는 외부 시스템이 DB와 애플리케이션 리소스에 미치는 영향을 줄이는 데 관심이 있습니다.

<br>

## Education & Certification

**한남대학교 컴퓨터공학과**  
GPA **4.24 / 4.5**

**Programmers 생성형 AI 활용 백엔드 개발 데브코스 5기**

**Programmers AI 인턴 프로그램 2기**

**Certification**  
정보처리기사 · SQLD

<br>

## Contact

**Email**  
beomb28@gmail.com

**GitHub**  
https://github.com/jjang0617
