---
name: short-form-app-ad
description: CozyBuilder 앱의 설치 전환용 9:16 숏폼 광고를 검증→기획→제작 설계→검수 순서로 만드는 오케스트레이션 Skill. 앱 광고, 설치 광고, 릴스/쇼츠/스토리 광고, UGC 광고, Shot List, Veo/Flow/Higgsfield 프롬프트 작성 요청 시 사용한다. Use when creating a short-form app-install ad (9:16 Reels/Shorts/Stories) for any CozyBuilder app.
---

# short-form-app-ad — 앱 설치 전환 숏폼 광고 Skill

모든 CozyBuilder 앱 광고에 공통 적용한다. 특정 앱 전용 프롬프트가 아니라
**검증 → 기획 → 제작 설계 → 검수**를 강제하는 오케스트레이션 절차다.

## SSOT와 우선순위

- 이 Skill은 **절차만 소유**한다. 아래 문서와 충돌하면 **항상 저장소 문서가 우선**한다.
- 프로젝트 입력 SSOT: [production_brief_v1.md](../../docs/templates/production_brief_v1.md) — Brief 승인 전 Scene Brief 금지.
- 역할: [role_division_v1.md](../../docs/operations/role_division_v1.md) — 창작은 Director(클챗), 반영은 Engineer(클로), 판단은 CEO.
- 훅 원칙: [hook_library.md](../../docs/patterns/hook_library.md) (DL-005 — 첫 0.5~1초 스크롤 멈춤).
- 완료 게이트: [00_START_HERE.md](../../00_START_HERE.md) §5·§6 — **이미지 승인 전 영상 생성 금지, 승인 없는 크레딧 사용 금지** (DL-004).
- 대상 앱의 사실 SSOT: 해당 앱 저장소의 README·docs/STATUS.md — 저장소명·브랜치는 `cozybuilder-ops/PROJECTS.md`에서 확인한다.

## 절차 — 14 게이트

각 게이트는 **통과 근거를 산출물에 기록**해야 다음 게이트로 진행할 수 있다.
게이트를 건너뛴 산출물은 미완료로 취급한다.

### Phase 0 — 사실 검증 (Fact Gate)

- **G1. GitHub 제품 문서 우선 확인** — `cozybuilder-ops/PROJECTS.md`에서 대상 앱의 실제 저장소·기본 브랜치를 확인하고, 그 저장소의 README·docs/STATUS.md·기능 문서를 **실제로 읽는다.** 기억·이전 대화 내용으로 기능을 확정하지 않는다.
- **G2. 실제 구현 기능 목록 확정** — 광고에 사용 가능한 기능 인벤토리를 작성한다. 각 기능마다 **근거(문서 경로 또는 소스 파일 경로)** 를 명기한다. 근거 없는 기능은 인벤토리에 넣지 않는다.
- **G3. 미구현 기능 차단** — G2 인벤토리에 없는 기능은 광고의 어떤 산출물(훅·카피·장면·프롬프트·자막)에도 등장할 수 없다. **구현되어 있어도 기본 OFF인 기능**(feature flag), 심사 대기·검증 대기 상태의 플랫폼은 "사용 불가"로 분류한다.

### Phase 1 — 기획 (Planning)

- **G4. 타깃·문제·욕구 정의** — 타깃 사용자 1문장, 그가 겪는 문제 1문장, 앱이 채우는 욕구 1문장. [templates/ad_input_brief.md](templates/ad_input_brief.md)에 기록한다.
- **G5. 훅 최소 3안** — 첫 1~3초 훅을 3안 이상 만든다. hook_library의 원칙(예쁨이 아니라 멈춤)을 따르고, 각 안에 "왜 스크롤이 멈추는가"를 1줄 붙인다.
- **G6. 문제 → 감정 → 해결 → CTA 구조** — 스토리 4단 구조를 고정한다. "해결" 구간의 화면은 반드시 G2 인벤토리의 기능 시연이어야 한다. CTA는 앱 설치 행동 1개로 단일화한다.
- **G7. 포맷 확정** — 9:16 기준. **15초 안을 우선 완성**하고, 30초 확장은 15초 안의 장면 확장 매핑으로만 설계한다(별도 신규 시나리오 금지).

### Phase 2 — 제작 설계 (Production Design)

- **G8. 장면별 Shot List** — [templates/shot_list.md](templates/shot_list.md) 양식으로 작성한다. 장면마다 사용 기능의 G2 근거를 연결한다.
- **G9. 자막·내레이션·효과음 설계** — Shot List의 열로 함께 작성한다. 자막은 화면당 1메시지, 음소거 시청만으로 이해 가능해야 한다.
- **G10. 모델별 프롬프트 분리** — Veo용 / Flow용 / Higgsfield용 프롬프트를 **별도 블록**으로 출력한다. 하나의 프롬프트를 복붙 공유하지 않는다. 모델별 강점(카메라 지시·연속성·캐릭터 일관성)에 맞춰 각각 작성한다.

### Phase 3 — 검증·승인 (Verification Gate)

- **G11. 설치 전환 자체 평가** — [templates/self_evaluation.md](templates/self_evaluation.md) 점수표를 채운다. 통과 기준 미달이면 Phase 1로 되돌아간다.
- **G12. 금지 표현 차단** — 아래 목록을 전 산출물(훅·카피·자막·내레이션·프롬프트)에 대해 검사한다. 발견 시 수정 후 재검사한다.
- **G13. 검수 체크리스트** — [templates/review_checklist.md](templates/review_checklist.md)를 전 항목 통과해야 "검수 대기" 상태가 된다.
- **G14. 승인 게이트** — CEO(코지) 승인 없이 다음 제작 단계(키프레임 생성·영상 생성·크레딧 사용·게시)로 진행하지 않는다. DL-004(이미지 승인 전 영상 생성 금지)와 함께 적용된다. 승인 요청은 산출물과 함께 명시적으로 올린다.

## G12 — 금지 표현 목록

정신건강 앱 계열(감사일기 등)에 특히 적용하며, 모든 앱 광고에 공통 적용한다.

| 분류 | 금지 | 대신 쓸 수 있는 사실 서술 예 |
|------|------|------------------------------|
| 치료 효과 단정 | "우울증이 낫는다/개선된다", "불안이 사라진다", "치료/완치/처방" | "감사한 순간을 기록한다", "하루를 돌아보는 습관" |
| 의학·과학 효능 | "과학적으로 증명된 정신건강 개선", 논문 인용으로 효능 보장 | 기능 사실만 서술 |
| 보장성 표현 | "100%", "누구나 반드시", "단 N일 만에 인생이 바뀐다" | "매일 3가지 감사를 기록해 보세요" |
| 미구현·비활성 기능 | G2 인벤토리 밖 기능, 기본 OFF 기능, 심사 대기 플랫폼을 가능한 것처럼 표현 | 구현·활성 기능만 |
| 비교 비방 | 타 앱 실명 비교·비방 | 자기 기능 서술 |

## 산출물 묶음 (한 광고 = 한 문서 세트)

1. 광고 입력 양식 (ad_input_brief) — G1~G4 결과 포함
2. 훅 3안 + 선택안
3. 15초 Shot List (+30초 확장 매핑)
4. 모델별 프롬프트 3블록 (Veo / Flow / Higgsfield)
5. 자체 평가표 (G11)
6. 검수 체크리스트 결과 (G13)
7. 승인 요청 (G14)

산출물 저장·commit/push는 Engineer(클로)가 수행한다. 사용 예시: [examples/gratitude-note-demo.md](examples/gratitude-note-demo.md) — **승인된 제작안이 아니라 양식 시연**이다.
