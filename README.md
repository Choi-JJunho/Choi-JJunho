## 🙋‍♂️ About Me

> **대용량 거래 데이터의 성능과 정합성을 다루며, 운영 중단 없이 구조를 개선해 온 백엔드 엔지니어입니다.**

200만 소상공인이 사용하는 금융 장부 서비스에서 100만+ 사업장 부가세 배치를 **19시간 41분 → 약 30분**으로 줄이고, 발송 이력 **2억 건을 무중단으로 이관**했으며, 대용량 데이터 API의 응답 레이턴시를 **p95 기준 80~84% 단축**했습니다. 운영 영향을 최소화하면서 구조를 바꾸고, 수치로 결과를 검증하는 데 강점이 있습니다.

| 항목 | 내용 |
|------|------|
| 💼 현직 | **한국신용데이터(캐시노트)** 장부팀 백엔드 엔지니어 (2025.01 ~ 현재)<br>∙ 데이터실 AI TF 겸직 (2025.04 ~ 2025.09) |
| 🏫 교육 | **우아한테크코스 백엔드 5기 수료** (2023.02 ~ 2023.11)<br>∙ 프레임워크 직접 구현을 통한 학습 (Spring MVC, Tomcat)<br>∙ 코드 리뷰, 페어 프로그래밍 중심 학습 |
| 💡 커뮤니티 & 활동 | **BCSDLab 동아리**<br>∙ 백엔드 트랙 리더 (백엔드 5명 리드, 2020.06 ~ 2024.12)<br>∙ 회장(2024), 교육 담당, 동아리 운영 자동화(Slack Bot·백오피스)<br><br>**Nexters**<br>∙ 25기 백엔드 개발자 · 26기 회장 |
| ✍️ 스터디 | 초록스터디 운영진 & 프로젝트 과정 팀장 (2024~2025)<br>초록스터디 멘토링 멘토 (2025.04 ~ 진행중) |
| 🧑‍🎓 학력 | 한국기술교육대학교 컴퓨터공학부 (2019.03 ~ 2026.02 졸업) |

---

## 🛠 Tech Stack

| 분류 | 기술 |
|------|------|
| **Languages** | Java · Kotlin · TypeScript |
| **Frameworks** | Spring Boot · Spring Batch · JPA |
| **Data** | PostgreSQL · MySQL · Redis · SQS |
| **Infrastructure** | AWS · Docker · Jenkins · Datadog |
| **AI** | Claude Agent SDK · Spring AI |

---

## 📂 Projects

> 거래 정합성, 대용량 처리, 무중단 이관을 중심으로 정리했습니다. 자세한 내용은 [포트폴리오](https://junogarden.com/portfolio)에서 볼 수 있습니다.

### 💳 한국신용데이터 (캐시노트) · 2025.01 ~ 현재

200만 소상공인이 사용하는 금융 장부 서비스에서 대용량 배치 성능 개선, 데이터 이관, 거래·지급 정합성 보장을 담당했습니다.

**🔁 리워드 중복 지급 방지 — Transactional Outbox** · 2026.05 ~ 2026.06  
`Kotlin` `Spring Batch` `PostgreSQL` `멱등성`
- 호출마다 발급되는 비멱등 외부 API에서도 중복 지급을 막는 멱등 지급 파이프라인 설계
- 자연키 복합 UNIQUE로 PENDING 선점 → 트랜잭션 밖에서 외부 호출 → 실패 시 relay 워커 재시도/DEAD 격리
- 평생 1회·일·주·월로 다른 멱등 주기를 하나의 규칙으로 처리

**⚡ 판매관리 핵심 API 성능 개선 (p95 80~84%↓)** · 2026.05 ~ 2026.06  
`Kotlin` `MySQL` `EXPLAIN ANALYZE` `Online DDL`
- 6.39억 행 POS 테이블 · 신규 인덱스 제한 환경에서 실행계획 기반 쿼리 재설계
- 시간축 버퍼로 파티션 프루닝 유도, 읽는 파티션 84개 → 약 7개로 축소
- 핵심 API p95 **80~84% 단축** (인기 메뉴 944.7ms → 185.7ms)

**📦 발송 이력 2억 건 무중단 이관** · 2025.11 ~ 2025.12  
`Kotlin` `PostgreSQL` `JDBC` `Dual Write` `Databricks`
- Dual Write + 범위 삭제 후 batch INSERT(3만 건 단위)로 OOM 회피
- 라이브 테이블에 영향 없이 두 DB에 흩어진 **2억 건을 단일 테이블로 통합**

**🧾 부가세 예상세액 배치 재설계 (19h 41m → 약 30m)** · 2025.06 ~ 2025.08  
`Kotlin` `Spring Batch` `Databricks` `PySpark`
- 계산을 OLTP 밖으로 이동 — Databricks 증분 집계 조회 + 매입세액 월별 분할로 OOM 해소
- 100만+ 사업장 처리 시간 **19시간 41분 → 약 30분**으로 단축

**🤖 AI 비서(캐시니) 실시간 스트리밍 백엔드 단독 구축** · 2025.04 ~ 2025.09  
`Kotlin` `SSE` `Spring AI` `MSA`
- 단방향 흐름에 맞춰 WebSocket 대신 SSE 채택, 토큰 단위 실시간 스트리밍 구현
- 채팅 API · 사용 한도 정책 엔진 · 유료 멤버십까지 백엔드 전 영역 단독 구축

---

### 🏫 [KOIN](https://koreatech.in) – 교내 커뮤니티 서비스

| 항목 | 내용 |
|------|------|
| 기간 | 2020.06 ~ 2024.12 |
| 사용자 | 교내 학생 및 교직원 75% 이상 |
| 역할 | 백엔드 트랙 리더 (백엔드 5명 리드) & 주요 아키텍처 개선 |
| 주요 성과 | ∙ Spring 3 레거시 → Spring Boot 100% 전환 (온보딩 6개월 → 1개월 단축)<br>∙ 코드 라인 50% 이상 감소 (42,326줄 → 20,365줄)<br>∙ Spring Event 기반 도메인 분리로 Slack 알림 트랜잭션 문제 해결<br>∙ Datadog APM 도입 → 장애 감지 시간 수 시간 → 수 분 단축<br>∙ AWS 인프라 재구성으로 월 서버비 30만원 → 10만원 (66% 절감) |

---

### 🪴 [Pium](https://pium.life) – 반려식물 관리 서비스

| 항목 | 내용 |
|------|------|
| 기간 | 2023.06 ~ 2023.11 (5개월) |
| 팀 | FE 3명, BE 4명 |
| 역할 | 백엔드 전반 개발 담당 (기획~운영) |
| 주요 성과 | ∙ HikariCP 커넥션 풀 최적화 (TPS 11%↑)<br>∙ 무중단 배포(Blue/Green), 세션 클러스터링 구축<br>∙ Jenkins 기반 CI/CD 파이프라인 구성<br>∙ RestDocs 도입 및 테스트 환경 분리<br>∙ fetch join, DB 튜닝으로 쿼리 85% 절감 |

---

## 🤖 AI Experience & Tech Sharing

> 일하는 과정에 숨어 있는 암묵지를 꺼내 생산성을 높이는 시도를 합니다. 직군을 넘어 조직 전체가 유기적으로 일하는 방법을 고민하고 실행합니다.

- **사내 코드리뷰봇** 단독 설계·구축 — 여러 저장소에 도입, 운영 830건 기준 **p50 2.6분 / 성공률 93.9%**, Critical 이슈 발생 시 변경 요청 자동 등록 품질 게이트 운영
- **카카오 알림톡 멀티모달 검수봇 MVP** — 규정 민감 항목(주류·광고 문구 등) 자동 검수 MVP를 **1시간 40분 만에 구축**해 수작업 검수 공수 제거
- **사내 근태관리 Desktop App** 제작 및 전사 배포로 구성원 반복 업무 절감
- **AI 앰버서더 2기** (개발자 7명 중 1인) — 사내 기술 공유 세션 3회 · AI 공유 세션 11회+ 운영, 비개발직군 멘토링

`Claude Code` `Codex` `Cursor` `Gemini`

---

## 🔧 Contributions

| 프로젝트 | 설명 |
|----------|------|
| [REST-assured Kotlin Extension PR #1800](https://github.com/rest-assured/rest-assured/pull/1800) | Jakarta UUID 관련 의존성 누락 이슈 해결 및 블로그 공유 |
| KOIN/Pium 기술블로그 | CI/CD, 테스트 초기화, 무중단 배포, RestDocs 세팅 등 노하우 공유<br>∙ [CI/CD with Jenkins](https://pium-official.github.io/jenkins-hook-by-label/)<br>∙ [RestDocs 설정기](https://pium-official.github.io/restdocs-start/)<br>∙ [인수 테스트 환경 설정기](https://pium-official.github.io/acceptance-test-resolve/) |

---

## 📝 Blog & Social

| 플랫폼 | 링크 |
|--------|------|
| Portfolio | [junogarden.com/portfolio](https://junogarden.com/portfolio) |
| Blog | [junogarden.com/blog](https://junogarden.com/blog) |
| Velog | [velog.io/@junho5336](https://velog.io/@junho5336) |
| LinkedIn | [linkedin.com/in/juno-world](https://www.linkedin.com/in/juno-world) |

---

## 🧠 Algorithm

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=junho5336)](https://solved.ac/junho5336/)

---

## 📫 Contact

| 이메일 | GitHub |
|--------|--------|
| junho5336@gmail.com | [github.com/Choi-JJunho](https://github.com/Choi-JJunho) |

---

> 꾸준히 성장하며 함께 일하고 싶은 개발자가 되기 위해 기록하고 공유합니다.  
> 방문해주셔서 감사합니다 😊
