# CGM 운영가이드 v1.1

클마 시스템을 운영하고 유지보수하는 사람이 읽는 문서.
**클로드가 읽는 파일이 아니다.**

---

## 1. 운영 환경 설정

### 현재 환경: 파일 첨부 방식 (기본값)

매 대화 시작 시 아래 파일을 첨부한다.

**필수 첨부 파일 (5개):**
```
CGM_SYSTEM_PROMPT_v2.3.md              ← 시스템 프롬프트 (붙여넣기)
cgm-audit-framework_SKILL_v1.9.1.md
cgm-deliverable-style_SKILL_v1.4.md
cgm-lessons_v1.6.md
og-knowledge-system_SKILL_v1.2.md
```

**참조 문서 (필요 시 첨부):**
```
og-consulting-style_SKILL_v1.2.md      ← 컨설팅 원칙 상세 참조용
CGM_클라이언트_의뢰서_요청가이드.md    ← 클라이언트 접수 시
cgm-case-log.md                        ← 케이스 기록 확인/업데이트 시
cgm-prompt-patterns_v1.3.md            ← 패턴 참조/업데이트 시
```

### 클로드 프로젝트 환경으로 전환 시

1. claude.ai에서 새 프로젝트 생성
2. Project Instructions에 `CGM_SYSTEM_PROMPT_v2.3.md` 내용 붙여넣기
3. Project Knowledge에 필수 스킬 파일 5개 업로드
4. 시스템 프롬프트의 전제 환경 섹션을 아래 1줄로 교체:

```
이 시스템은 클로드 프로젝트로 운영된다.
스킬 파일은 Project Knowledge에 자동 주입되어 있다.
```

---

## 2. Knowledge Base 파일 수 관리

**12개 이하 유지 원칙.**

파일 수가 13개를 초과하면 토큰 수와 무관하게 RAG가 조기 활성화될 수 있다.
RAG 모드에서는 파일 간 크로스 참조 품질이 저하된다.

```
현재 필수 파일: 9개 (안전권)
  CGM_SYSTEM_PROMPT, cgm-audit-framework, cgm-deliverable-style,
  og-knowledge-system, og-consulting-style,
  CGM_클라이언트_의뢰서_요청가이드, cgm-prompt-patterns,
  cgm-case-log, cgm-lessons
```

12개 임박 시: 미참조 파일 정리 또는 파일 병합 검토.
분기별 1회 파일 수 점검 권장.

---

## 3. 버전 관리 이력

| 파일 | 현재 버전 | 주요 변경 |
|------|----------|----------|
| CGM_SYSTEM_PROMPT | v2.3 | GitHub 레포 관리 추가 |
| cgm-audit-framework | v1.9.1 | Effort Level, Memory Tool 분리, Skills 실전 데이터, MCP 서버 한계, 다중 에이전트 비용 경고 |
| cgm-deliverable-style | v1.4 | Artifacts 산출물 기준 추가 (신규 등록) |
| cgm-lessons | v1.6 | 교훈 005~009 추가 |
| cgm-prompt-patterns | v1.3 | AP-07(Prefilling), AP-08(보안 설계 부재) 추가 |
| og-knowledge-system | v1.2 | KB 12개 원칙 추가 |
| og-consulting-style | v1.2 | 참조 문서로 역할 전환 |
| CGM_운영가이드 | v1.1 | cgm-deliverable-style 필수 파일 목록 추가, 버전 이력 업데이트 |

---

## 4. 첫 외부 케이스 완료 후 점검 루틴

첫 외부 클라이언트 검토가 완료되면 아래를 순서대로 점검한다.

```
□ case-log에 정상 기록됐는가
□ lessons.md에 승격 대상 교훈이 있는가
□ prompt-patterns에 새 AP가 필요한가
□ 5축 Level 판정 기준이 예상과 다르게 작동한 구간이 있는가
□ description 트리거가 실전에서 올바르게 작동했는가
```

케이스 3건 이상 누적 후: 5축 Level 판정 기준 보정 1회 실시.

---

## 5. 배포용 문서 관리

클라이언트에게 배포하는 문서는 GitHub 단일 출처로 관리:
```
https://github.com/littlebero/cgm-docs

포함 파일:
  CGM_소개서_v1.1.md
  CGM_프로젝트_스냅샷_템플릿.md
  CGM_클라이언트_의뢰서_요청가이드.md
```

파일 업데이트 시 → 레포에 직접 반영. 링크 공유로 자동 최신화.

---

<!--
  CGM_운영가이드 v1.1
  작성: 클마 (Claude Grand Master)
  날짜: 2026-03-04
  v1.0 대비 주요 변경:
    - 필수 첨부 파일 목록에 cgm-deliverable-style_SKILL_v1.4.md 추가
      (이유: v1.4 신규 등록. 산출물 형식 스킬은 심사와 동급 필수 파일)
    - cgm-lessons v1.6, cgm-prompt-patterns v1.3 버전 업데이트 반영
    - 버전 관리 이력 전체 업데이트
    - 섹션 5: 배포용 문서 GitHub 관리 원칙 추가
-->

*CGM_운영가이드 v1.1 | Claude Grand Master | 2026-03-04*
