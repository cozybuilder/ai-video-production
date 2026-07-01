# ai-video-production

AI 영상제작 운영의 **단일 진실 원천(SSOT, Single Source of Truth)** 저장소입니다.

---

## 1. 저장소 목적

이 저장소는 HARIN 브랜드 AI 영상제작의 **모든 운영 원칙 · 제작 규칙 · 학습 자산 · 결정 기록**을 보관합니다.
개별 영상 결과물이 아니라, "어떻게 만드는가"에 대한 기준 문서를 관리하는 곳입니다.

## 2. SSOT 선언

> **GitHub 저장소에 반영된 문서만이 공식 기준입니다.**

- 채팅에서의 합의는 **임시 상태**입니다.
- 문서로 저장되어 commit / push 되기 전까지는 **공식 결정이 아닙니다.**
- 서로 다른 정보가 충돌하면, **항상 이 저장소의 최신 문서가 우선**합니다.

## 3. 주요 문서

| 문서 | 설명 |
|------|------|
| [00_START_HERE.md](00_START_HERE.md) | **가장 먼저 읽어야 하는 문서** |
| [docs/operations/pm_playbook.md](docs/operations/pm_playbook.md) | 코비 PM 운영 규칙 |
| [docs/operations/decision_log.md](docs/operations/decision_log.md) | 공식 결정 기록 (DL) |
| [docs/studies/INDEX.md](docs/studies/INDEX.md) | 학습 자료 색인 |
| [docs/patterns/hook_library.md](docs/patterns/hook_library.md) | 훅(Hook) 라이브러리 |
| [docs/patterns/camera_language.md](docs/patterns/camera_language.md) | 카메라 언어 규칙 |
| [docs/characters/harin/identity_rules.md](docs/characters/harin/identity_rules.md) | HARIN 정체성 규칙 |
| [docs/retrospectives/2026-07-01_f1_f2_f4_failures.md](docs/retrospectives/2026-07-01_f1_f2_f4_failures.md) | F1/F2/F4 실패 회고 |

## 4. 역할 구분

| 역할 | 주체 | 책임 |
|------|------|------|
| **CEO** | 사장님 | 최종 의사결정, 방향 확정 |
| **코비** | ChatGPT PM | 연출 · 검수 · 지시서 작성 |
| **클챗** | Claude 챗봇 | 분석 · 프롬프트 · 문서 **초안** |
| **클로** | Claude Code | 실제 파일 수정 · commit · push |

> ⚠️ **클챗(초안 작성)과 클로(실제 저장)를 혼동하지 않습니다.**

## 5. 완료 게이트 (요약)

작업은 아래 **7단계 모두**가 끝나야 완료입니다.

1. 코비 지시 → 2. 사장님 전달 → 3. 클로 실제 파일 수정 → 4. commit → 5. push → 6. 완료보고 → 7. 코비 검수

**미응답 = 미완료. 문서 미반영 = 미확정.**

## 6. HARIN 핵심 원칙 (요약)

> **하린은 변하지 않습니다. 세상이 변합니다.**

- **고정축(HARIN):** 얼굴 · 의상 · 헤어 · 실루엣 · 정체성
- **변화축(WORLD):** 배경 · 카메라 · 자연현상 · 세계 · 조명 · 사운드

제작 게이트: **승인된 이미지 없이는 영상 생성 금지.** 프롬프트보다 승인된 이미지가 우선.
