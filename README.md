# 김석현 (Seokhyun Kim)

Java / Spring 백엔드 개발자를 준비하고 있습니다.
가설을 세우고, 실측으로 기각하고, 판단 근거를 남기는 것에 관심이 있습니다.

[![Blog](https://img.shields.io/badge/Blog-333446?style=flat-square&logo=notion&logoColor=white)](블로그_링크)
[![Resume](https://img.shields.io/badge/Resume-7F8CAA?style=flat-square&logo=readthedocs&logoColor=white)](이력서_링크)
[![Mail](https://img.shields.io/badge/meet--ksh@ddotg.dev-B8CFCE?style=flat-square&logo=gmail&logoColor=333446)](mailto:meet-ksh@ddotg.dev)

---

### Education & Activities


| 활동명 | 활동 기간 | 세부 활동 |
|---|---|---|
| **가톨릭대학교** | 2020.03 ~ 2027.02 | 컴퓨터정보공학부 · 졸업 예정 (학점 4.15 / 4.5) |
| **GDGoC on Campus CUK** | 2024.09 ~ 2026.06 | 3~6기 연속 활동 · 스터디 팀장 3회 (Spring / 1인 프로젝트 / 알고리즘 / 면접) |
| **UMC (University MakeUs Challenge)** | 2025.03 ~ 2026.02 | 8기·9기 Backend Team Leader · 프로젝트 개발 2회 |

---

### Project

**[DummyTalk](https://github.com/DummyTalk-Solo-Project/DummyTalk_BE)** 
`Java 21` `Spring Boot 3.5` `PostgreSQL` `Redis` `Elasticsearch`
> k6 부하 테스트로 HikariCP 커넥션 풀 고갈(Pending 38 / Pool 10)을 병목으로 규명하고, Prometheus + Grafana로 스레드 풀 포화 → 레이턴시 급증 인과를 지표로 추적했습니다.

> 동일 계정 연속 요청에서 트랜잭션만으로는 막지 못하는 Lost Update 14.7% 를 k6로 실측하고, 분산 락 → 인터셉터 선차단까지 3단계 동시성 전략을 비교해 전 구간 0%를 달성했습니다.

> 이후 남은 지연의 원인이 락이 아닌 Tomcat TaskQueue 임을 규명하고 Virtual Thread를 도입했으며, 커넥션 풀 2배 증설이 오히려 Pending을 463→789로 악화시킨다는 것을 확인해 증설안을 기각했습니다.


**[WithRun](https://github.com/jijysun/With_Run_BE_V2)** 
`Spring Boot` `MySQL` `AWS RDS` `Docker`
> 채팅 API 1회에 발생하던 **Redis 왕복 15회를 Lua Script + Pipeline으로 1회**로 줄이고, GET/INCR 분리 구조의 Race Condition을 원자 연산으로 해소했습니다. (Acquire Time 270→25ms)

> 개선 후 오히려 지연이 악화되는 현상에서 **병목이 DB에서 CPU로 이동했음**을 확인하고, 팬아웃 비율을 반영해 STOMP 채널을 분리 사이징 → 400VU 기준 **p90 -86%** 를 달성했습니다.


**[Lumo](https://github.com/jijysun/Lumo_Backend)** — AI 미션 알람 서비스 · Backend Team Leader
`Spring Boot` `MySQL` `Redis` `Nginx` `Docker Compose` `Loki/Promtail`

> 외부 SMTP 통신(3~5초)이 메인 스레드를 점유해 CPU 90%를 넘기던 인증 API를 **Redis Queue 기반 Producer/Worker 구조**로 개편, CPU 63.4%→40% · 처리 속도 약 15배를 확보했습니다.
> 배포 다운타임이 곧 알람 유실인 도메인 특성을 고려해 **Nginx 블루-그린 무중단 배포**를 구축했습니다.


---

### Tech Stack

**Language & Framework**

[![](https://skillicons.dev/icons?i=java,spring,hibernate,gradle)](https://skillicons.dev)

**Database & Search**

[![](https://skillicons.dev/icons?i=postgres,mysql,redis,elasticsearch)](https://skillicons.dev)

**Infra & CI/CD**

[![](https://skillicons.dev/icons?i=docker,aws,githubactions,nginx,linux)](https://skillicons.dev)

**Observability & Testing**

[![](https://skillicons.dev/icons?i=prometheus,grafana,postman)](https://skillicons.dev)

**Tools**

[![](https://skillicons.dev/icons?i=idea,git,notion,figma)](https://skillicons.dev)
