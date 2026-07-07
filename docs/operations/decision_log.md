# Decision Log (DL)

공식 결정 기록입니다. 여기에 기록된 항목만이 확정된 운영 원칙입니다.
새 결정은 하단에 추가하고, 기존 결정을 바꿀 때는 새 DL로 대체 사실을 명시합니다.

> **역할 재정의:** Decision Log = **History**(결정의 역사). Register = **Current State**(현재 상태).
> 둘은 서로 역참조한다. Register: [operating_rules.md](operating_rules.md) · [pattern_register.md](../patterns/pattern_register.md) · [asset_register.md](asset_register.md) · [gates.md](gates.md)

| ID | 결정일 | 상태 | 제목 |
|----|--------|------|------|
| DL-001 | 2026-07-02 | 확정 | ai-video-production SSOT 확정 |
| DL-002 | 2026-07-02 | 확정 | 클챗/클로 역할 분리 |
| DL-003 | 2026-07-02 | 확정 | HARIN 고정축 원칙 |
| DL-004 | 2026-07-02 | 확정 | 이미지 승인 전 영상 생성 금지 |
| DL-005 | 2026-07-02 | 확정 | 첫 0.5~1초 훅 우선 원칙 |
| DL-006 | 2026-07-02 | 확정 | 완료 게이트 확정 |
| DL-007 | 2026-07-02 | 확정 | 학습 영상은 studies에 자산화 |
| DL-008 | 2026-07-02 | 확정 | F1/F2/F4는 공식 제작물 아님, 실패 회고로만 기록 |
| DL-009 | 2026-07-02 | 확정 | 코비 기준 관리자 및 4주체 운영 체계 확정 |
| DL-010 | 2026-07-02 | 확정 | Public GitHub 운영 및 코비 최종 검수 원칙 |
| DL-011 | 2026-07-02 | 확정 | Status 운영 및 세션 종료 원칙 |
| DL-012 | 2026-07-08 | 확정 | 운영 철학 정립 및 Register 체계 도입 |

---

## DL-001 — ai-video-production SSOT 확정
이 GitHub 저장소가 AI 영상제작의 단일 진실 원천(SSOT)이다. 채팅 합의는 임시 상태이며, commit/push 된 문서만이 공식 기준이다.

## DL-002 — 클챗/클로 역할 분리
클챗(Claude 챗봇)은 분석·프롬프트·문서 초안을 담당하고, 클로(Claude Code)는 실제 파일 수정·commit·push를 담당한다. 둘을 혼동하지 않는다.

## DL-003 — HARIN 고정축 원칙
하린은 변하지 않는다. 세상이 변한다. 고정축(얼굴·의상·헤어·실루엣·정체성)은 불변, 변화축(배경·카메라·자연현상·세계·조명·사운드)만 변화한다.

## DL-004 — 이미지 승인 전 영상 생성 금지
키프레임/이미지가 승인되기 전에는 영상을 생성하지 않는다. 승인 없는 크레딧 사용 금지. 프롬프트보다 승인된 이미지가 우선한다.

## DL-005 — 첫 0.5~1초 훅 우선 원칙
모든 영상은 첫 0.5~1초 안에 스크롤을 멈추게 해야 한다. 제작은 훅을 우선으로 설계한다.

## DL-006 — 완료 게이트 확정
완료 조건: ① 코비 지시 ② 사장님 전달 ③ 클로 실제 파일 수정 ④ commit ⑤ push ⑥ 완료보고 ⑦ 코비 검수. 미응답은 미완료다.

## DL-007 — 학습 영상은 studies에 자산화
학습용 MP4는 분석 후 docs/studies에 기록하고 patterns를 갱신하며 commit/push 한다. "봤다"가 아니라 "재사용 가능한 지식 자산으로 저장했다"가 완료 기준이다.

## DL-008 — F1/F2/F4는 공식 제작물 아님, 실패 회고로만 기록
기존에 만든 F1/F2/F4 영상은 공식 제작물로 취급하지 않는다. 실패 실험/교훈으로만 [retrospectives](../retrospectives/2026-07-01_f1_f2_f4_failures.md)에 기록하며, 제작은 문서 저장 이후 처음부터 다시 시작한다.

## DL-009 — 코비 기준 관리자 및 4주체 운영 체계 확정
2026-07-01 확정된 4주체 운영 체계를 공식화한다.

**확정 역할**

- **CEO** — 최종 승인, 방향 결정
- **코비** — 기준 관리자(PM)
- **클챗** — 실행 보조(분석/프롬프트)
- **클로** — 엔지니어(commit/push)

**운영 원칙**

- 코비가 기준을 잡는다.
- 클챗은 시키는 일만 한다.
- 클로는 승인된 내용만 저장한다.
- CEO는 최종 승인과 감사(Audit)를 수행한다.

상세 역할 정의: [00_START_HERE.md](../../00_START_HERE.md) · 관리자 원칙: [pm_playbook.md](pm_playbook.md)

## DL-010 — Public GitHub 운영 및 코비 최종 검수 원칙
- ai-video-production 저장소는 **Public**으로 운영한다.
- 클로가 실제 파일 수정 및 commit/push를 담당한다.
- 코비는 **Public GitHub 문서를 직접 확인하고 최종 승인**한다.
- **실문서 검수 전에는 DONE 선언을 하지 않는다.**

상세 절차: [pm_playbook.md](pm_playbook.md) §10

## DL-011 — Status 운영 및 세션 종료 원칙
- `status.md`는 상시 업데이트하지 않는다.
- 같은 채팅방 안에서는 코비가 맥락을 관리한다.
- 채팅방을 새로 만들 때만 status를 저장한다.
- 하루 작업 종료 시 status를 저장한다.
- 중간 진행상황은 GitHub에 기록하지 않는다.
- 영구 자산(결정/학습/패턴/회고)만 즉시 문서화한다.

상세 운영: [pm_playbook.md](pm_playbook.md) §11 · 대상 문서: [status.md](status.md)

## DL-012 — 운영 철학 정립 및 Register 체계 도입
토론 #001~002 합의를 반영해 운영 철학과 Register 체계를 도입한다. (AI Video Production 내부 문서 한정, OPS 미변경)

- **운영 철학:** [operating_philosophy.md](operating_philosophy.md) OP-001~007
- **문서화 정책:** [documentation_policy.md](documentation_policy.md)
- **Register 체계(Current State):** Rule([operating_rules.md](operating_rules.md)) · Pattern([pattern_register.md](../patterns/pattern_register.md)) · Asset([asset_register.md](asset_register.md)) · Gate([gates.md](gates.md))
- **Study 완료조건:** 테스트 가능한 가설 1개 이상 ([study_template.md](../studies/study_template.md))
- **회고 표준:** [retrospective_v1.md](../retrospectives/retrospective_v1.md)
- **용어 참조:** [glossary.md](glossary.md)
- **Decision Log 역할 재정의:** Decision = History, Register = Current State (상단 참조)
