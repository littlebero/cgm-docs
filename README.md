# cgm-docs

**Claude Grand Master (클마)** 공식 문서 레포.  
클마를 활용하는 모든 프로젝트의 온보딩 문서와 템플릿을 관리한다.

---

## 파일 목록

| 파일 | 용도 | 대상 |
|------|------|------|
| [CGM_introduction_v1.1.md](./CGM_introduction_v1.1.md) | 클마가 누구인지, 어떻게 접근하는지 | 처음 클마를 접하는 모든 프로젝트 |
| [CGM_project_snapshot_template.md](./CGM_project_snapshot_template.md) | 현재 프로젝트 상태를 채워서 클마에게 가져오는 양식 | 클마에게 검토 요청할 때 |
| [CGM_client_request_guide.md](./CGM_client_request_guide.md) | 클마가 심사 시작 전 클라이언트에게 요청하는 항목 상세 | 첫 의뢰 시 참고 |

---

## 사용 순서

1. 브라우저에서 **CGM_introduction** 열어서 읽기 → 에스컬레이션 블록 시스템 프롬프트에 삽입
2. 브라우저에서 **CGM_project_snapshot_template** 열기 → Raw 버튼 클릭 → 전체 복사 → 현재 상태 채우기
3. 채운 템플릿을 `.md` 파일로 저장 → `claude.ai` CGM 프로젝트에 파일로 첨부 → 대화 시작

> ⚠️ GitHub 링크를 클로드 대화창에 직접 붙여넣지 않는다. 클로드는 외부 URL을 fetch할 수 없다. 파일을 다운받아서 첨부하는 방식으로 사용한다.

---

## 업데이트 이력

| 날짜 | 변경 내용 |
|------|----------|
| 2026-03-03 | 사용 순서 수정 — GitHub 링크 fetch 불가, 파일 다운로드 후 첨부 방식으로 명시 |
| 2026-03-03 | 파일명 한글 → 영어 변경 (URL 공유 문제 해결) |
| 2026-03-03 | 레포 최초 생성 |

---

*Claude Grand Master | cgm-docs*
