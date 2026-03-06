# cgm-docs

**Claude Grand Master (클마)** 공식 문서 레포.
클마 운영 파일 전체를 단일 출처로 관리한다.

---

## 폴더 구조

```
cgm-docs/
├── /public/       클라이언트에게 공유하는 배포용 문서
├── /core/         클마 운영 핵심 파일 (시스템 프롬프트, 스킬)
├── /knowledge/    누적형 지식 파일 (lessons, case-log, patterns)
└── /handover/     세션 간 연속성 보장 (날짜별 보존)
```

---

## 현재 최신 버전

| 파일 | 버전 | 폴더 |
|------|------|------|
| CGM_SYSTEM_PROMPT | v2.3 | /core/ ← KB에만 존재, 레포 미반영 |
| cgm-audit-framework_SKILL | v1.9.1 | /core/ |
| cgm-deliverable-style_SKILL | v1.4 | /core/ |
| og-knowledge-system_SKILL | v1.2 | /core/ |
| og-consulting-style_SKILL | v1.2 | /core/ |
| CGM_표준_에스컬레이션_블록 | v1.0 | /core/ |
| CGM_운영가이드 | v1.1 | /core/ |
| cgm-lessons | v1.7 | /knowledge/ |
| cgm-case-log | v1.3 | /knowledge/ |
| cgm-prompt-patterns | v1.3 | /knowledge/ |

---

## /public 파일 목록 (클라이언트 배포용)

| 파일 | 용도 |
|------|------|
| CGM_introduction_v1.1.md | 클마 소개서 — 처음 접하는 사람용 |
| CGM_project_snapshot_template.md | 프로젝트 상태 제출 양식 |
| CGM_클라이언트_의뢰서_요청가이드.md | 심사 전 제출 항목 안내 |
| claude-project-operations-guide_v1.0.md | 클로드 프로젝트 운영 마스터 가이드 |

---

## 클마 web_fetch 활용법

GitHub MCP가 claude.ai 웹에서 미지원인 현재,
클마가 파일을 직접 읽으려면 아래 Raw URL 패턴을 사용한다.

```
https://raw.githubusercontent.com/littlebero/cgm-docs/main/[폴더]/[파일명]
```

예시:
```
https://raw.githubusercontent.com/littlebero/cgm-docs/main/knowledge/cgm-lessons_v1.7.md
https://raw.githubusercontent.com/littlebero/cgm-docs/main/handover/CGM_핸드오버_2026-03-05.md
https://raw.githubusercontent.com/littlebero/cgm-docs/main/core/cgm-audit-framework_SKILL_v1_9_1.md
```

> 레포가 Public이면 파일 첨부 없이 클마가 URL만으로 읽을 수 있다.

---

## 동기화 루틴

### 클마가 파일을 업데이트할 때

```
1. 클마가 새 버전 파일 생성
2. 세로씨가 다운로드
3. GitHub 해당 폴더에 커밋
4. claude.ai KB에서 구버전 교체
```

### 세션 종료 시 (핸드오버)

```
1. 클마가 CGM_핸드오버_YYYY-MM-DD.md 생성
2. /handover/ 폴더에 커밋 (날짜별 보존)
3. 다음 세션 시작 시 해당 파일 첨부
```

### 커밋 메시지 규칙

```
[파일명] v[버전]: [변경 내용 한 줄]

예:
  cgm-lessons v1.8: 교훈 015-016 추가
  CGM_핸드오버_2026-03-06: 세션 종료 핸드오버
  cgm-audit-framework v1.9.2: GitHub 커넥터 상태 업데이트
```

---

## 업데이트 이력

| 날짜 | 변경 내용 |
|------|----------|
| 2026-03-05 | 레포 구조 전면 재편: /public, /core, /knowledge, /handover 4폴더 분리 |
| 2026-03-05 | 클마 KB 핵심 파일 전부 레포에 초기 동기화 |
| 2026-03-05 | web_fetch Raw URL 활용법 추가 |
| 2026-03-03 | 파일명 한글 → 영어 변경 (URL 공유 문제 해결) |
| 2026-03-03 | 레포 최초 생성 |

---

*Claude Grand Master | cgm-docs | 2026-03-05*
