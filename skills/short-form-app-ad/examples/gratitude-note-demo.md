# 사용 예시 — gratitude-note (양식 시연)

> ⚠️ **승인된 제작안이 아니다.** Skill의 게이트·양식이 실제로 어떻게 채워지는지 보여주는 시연이며,
> 실제 감사일기 광고 제작은 CEO 승인 후 별도 배치로 진행한다 (G14).
> 사실 확인 기준일: 2026-07-21 (gratitude-note docs/STATUS.md v1.8.0).

## A. 대상 앱 사실 (G1)

- 앱 이름: 감사일기 (Gratitude Note)
- 저장소: `cozybuilder/gratitude-note` (cozybuilder-ops/PROJECTS.md 확인)
- 기본 브랜치: `master`
- 확인한 문서: README.md, docs/STATUS.md, docs/PROJECT_OVERVIEW.md (2026-07-21)
- 현재 버전 / 출시 상태: v1.8.0 / Play Console 제출 완료·심사 대기, 웹(Vercel) 운영 중

## B. 검증된 기능 인벤토리 (G2)

| # | 기능 | 근거 | 광고 사용 |
|---|------|------|-----------|
| 1 | 매일 3가지 감사 기록 작성 | README.md, src/hooks/useNotes.ts | ✅ 가능 |
| 2 | 연속 기록 streak (새벽 4시 날짜 경계) | src/utils/streak.ts, date.ts | ✅ 가능 |
| 3 | 배지(업적) 시스템 + 획득 축하 모달 | src/hooks/useAchievements.ts | ✅ 가능 |
| 4 | 공유 카드 이미지 생성 (QR/URL 포함) + 시스템 공유 | src/utils/shareCard.ts, ShareCardModal.tsx | ✅ 가능 |
| 5 | 저녁 18시/22시 로컬 알림 | src/utils/notification.ts, STATUS.md "실기기 발송 확인" | ✅ 가능 |
| 6 | 다크 모드 | src/hooks/useTheme.ts | ✅ 가능 |
| 7 | JSON 백업/복원 | src/utils/backup.ts | ✅ 가능 |
| 8 | 데이터 전부 기기 저장(localStorage), 서버 DB 없음 | PROJECT_OVERVIEW.md §4 | ✅ 가능 (프라이버시 소구) |
| 9 | AI 배지 축하 메시지 | ai.ts — `ENABLE_BADGE_AI_API = false` | ❌ 불가 (기본 OFF, G3) |
| 10 | iOS 앱 | STATUS.md — 실기기 검증 대기 | ❌ 불가 (미출시, G3) |
| 11 | AdMob 광고 제거 등 유료 기능 | 해당 기능 없음 | ❌ 불가 (미구현) |

## C. 타깃·문제·욕구 (G4)

- 타깃: 하루가 정신없이 지나가 버리는 20~30대 직장인.
- 문제: 잠들기 전 남는 건 피로와 걱정뿐, 오늘 뭐가 좋았는지 기억나지 않는다.
- 욕구: 하루 1분으로 오늘의 좋았던 순간을 붙잡아 두고 싶다.

## E. 훅 후보 (G5)

| 안 | 첫 1~3초 훅 | 왜 멈추는가 |
|----|-------------|-------------|
| 1 | 침대에 누워 스크롤하는 손 위로 자막 "오늘 뭐가 좋았는지 하나라도 기억나요?" | 시청자의 지금 행동(침대 스크롤)을 그대로 지목 |
| 2 | streak 숫자가 1→30으로 빠르게 차오르는 화면 클로즈업 | 숫자 상승 모션 + "나도 쌓고 싶다"는 수집 욕구 |
| 3 | 어두운 방, 알림 "오늘의 감사 3가지를 남길 시간이에요" 도착 화면 | 실제 앱 알림 UI 재현 — 내 폰에 온 알림처럼 착각 |
| 선택 | 1안 | 문제 제기형이 4단 구조(G6)와 가장 자연스럽게 연결 |

## 15초 Shot List 발췌 (G8·G9)

| Scene | 구간 | 단계 | 화면 | 자막 | 효과음 | 사용 기능 |
|-------|------|------|------|------|--------|-----------|
| S1 | 0–3 | 훅/문제 | 침대 스크롤 손, 지친 얼굴 | "오늘 뭐가 좋았는지 기억나요?" | 무음→심장박동 1회 | — |
| S2 | 3–6 | 감정 | 한숨, 어두운 천장 | "매일 이렇게 끝나는 하루" | 낮은 앰비언트 | — |
| S3 | 6–9 | 해결 | 앱 열고 감사 3줄 입력 | "하루 1분, 감사 3가지" | 타이핑음 | 기능 1 |
| S4 | 9–12 | 해결 | streak 숫자·배지 획득 모달 | "쌓일수록 보이는 나의 기록" | 청량한 획득음 | 기능 2·3 |
| S5 | 12–15 | CTA | 앱 아이콘 + 스토어 버튼 | "감사일기 — 지금 설치" | 로고 사운드 | — |

## 모델별 프롬프트 예 (G10 — S1만 발췌)

### S1 — Veo
```
Vertical 9:16. Dim bedroom at night, a young adult lying in bed, face lit only by
phone glow, thumb slowly scrolling. Slow push-in from above, shallow depth of field,
muted cool tones. One event only: the scrolling stops as text overlay appears.
```

### S1 — Flow
```
9:16 vertical, scene 1 of 5. Night bedroom, phone-lit face, endless scroll gesture.
Hold continuity anchors for next scene: same room, same lighting, same wardrobe.
End frame: thumb freezes mid-scroll (transition point to S2 sigh).
```

### S1 — Higgsfield
```
9:16. Consistent character (20s office worker, casual t-shirt) reclining in dark
bedroom, phone glow on face. Subtle handheld feel, slow push-in preset. Emotion:
drained but restless. Single action: doomscrolling, then a pause.
```

## 자체 평가 (G11 — 시연 채점)

| 항목 | 점수 | 근거 |
|------|------|------|
| 훅 강도 | 4 | 시청자 행동 지목형, 단 실사 연출 품질에 의존 |
| 문제 공감 | 5 | 타깃의 밤 루틴 그대로 |
| 해결 설득력 | 4 | 실제 기능(기록·streak·배지) 시연 |
| CTA 명확성 | 5 | 설치 단일 행동 |
| 타깃 적합성 | 4 | 릴스/쇼츠 톤 부합 |
| 사실성 | 5 | 전 장면 G2 인벤토리 내, G12 통과 |

- 총점 27/30, 3점 미만 없음 → **통과**

## G12·G13 확인

- 금지 표현 검사: "정신건강 개선"류 표현 없음 — "하루 1분 기록" 사실 서술만 사용 ✅
- 검수 체크리스트: 시연 기준 전 항목 ✅ (실제 제작 시 재검사)
- G14: 본 예시는 승인 요청 대상이 아님. 실제 제작은 CEO 승인 후 시작.
