# AI Video Study Standard v1

**One Video = One Reproducible Production Manual**

> Study의 유일한 목적은 **"이 영상이 어떻게 만들어졌는가"** 를 재현 가능한 수준으로 기록하는 것이다.
> 비즈니스·브랜딩·HARIN 적용·운영 철학은 이 표준의 범위가 아니다. (하단 [범위 제외](#명시적-제외-항목) 참조)

모든 Study는 아래 **8개 섹션을 필수**로 가진다.

---

## 1. Metadata

- **Study ID:**
- **Title:**
- **Creator:**
- **URL:**
- **Date:**
- **Analysis Level:** (택1)
  - `TEXT_ANALYZED` — 텍스트/자막 기반 분석
  - `SEMI_MEDIA_ANALYZED` — 미디어 일부 기반 분석
  - `FULL_MEDIA_ANALYZED` — 전체 미디어 기반 분석

**Source Set** (확보 여부 표기)
- URL
- MP4
- WAV
- SRT
- PDF
- Blog
- Notion

**자료 출처 구분**
- 직접 확인한 자료:
- 사용자 제공 자료:
- 접근 불가능했던 자료:

---

## 2. Story & Scenario

> **가장 중요한 섹션.** 목표: "이 광고를 그대로 다시 찍을 수 있을 정도"로 기록한다.

- 전체 시나리오:
- 컷 개수:
- 컷별 시나리오: (컷 번호별로 무슨 일이 일어나는지)
- 주인공 행동:
- 제품 등장 시점:
- 장소 변화:
- 감정선:
- Hook:
- Conflict:
- Resolution:
- Hero Shot:
- CTA:

---

## 3. Human → AI Instruction Patterns

> **분석 대상:** 사람이 실제로 AI에게 입력한 것만.

**포함**
- 짧은 지시 방식
- 역할 부여
- 출력 형식 요구
- 반복 수정 방식
- 체크리스트 사용
- Scene 단위 수정
- 도구 연결 방식

**제외**
- ❌ Claude가 생성한 최종 프롬프트
- ❌ AI 결과물을 그대로 복사하는 것

---

## 4. Tool & Menu Workflow

> 핵심 질문: **"어떤 AI를 썼는가"** 보다 **"어떤 메뉴를 어떤 순서로 눌렀는가"**.

**예시 흐름**

```text
Image → Character Sheet
Image → Wardrobe
Image → Shoes
Image → Props
Image → Locations
Seedance → Scene Generation
Edit → Final Video
```

**반드시 기록**
- 메뉴 이름
- 사용 순서
- 목적
- 입력 자산
- 출력 자산
- 실패 시 수정 위치

---

## 5. Required Assets

> 목표: "무엇을 먼저 만들어야 하는가"를 기록한다.

**Character** — 얼굴 / 헤어 / 표정 / 포즈
**Wardrobe** — 상의 / 하의 / 신발 / 액세서리
**Environment** — 장소 / 배경 / 조명 / 날씨
**Product** — 제품 / 패키지 / 로고 / 브랜드 컬러
**Props** — 컵 / 책 / 가방 / 차량 / 가구 / 반려동물 / 기타 소품

---

## 6. Asset Creation & Locking

**시트(Sheet) 기록**
- Character Sheet
- Product Sheet
- Wardrobe Sheet
- Background Sheet
- Props Sheet

**자산 운용 기록**
- 어떤 자산을 `locked asset` 으로 사용했는가
- 어떤 자산을 매 Scene마다 재사용했는가
- 어떤 자산을 새로 생성했는가

---

## 7. Drift Prevention

> 목표: "왜 드리프트가 발생했고, 어떻게 막았는가"를 기록한다.

- Locked Assets
- Character Sheet
- Product Sheet
- Wardrobe Sheet
- Single Face Rule
- Gray Background Rule
- Schematic Map
- Scene ID 기반 수정
- Reference Image 전략
- Best Few Seconds 전략

---

## 8. Camera / Lighting / Editing

> **추상 표현 금지.** ❌ cinematic / beautiful / cool → ✅ 50mm lens / eye-level / slow push-in

**Camera (Shot Size)**
- ECU / CU / MCU / MS / WS / OTS

**Lens**
- 35mm / 50mm / 85mm

**Movement**
- Push-in / Pull-out / Tracking / Orbit / Dolly

**Lighting**
- High-key / Low-key / Soft Light / Rim Light

**Editing**
- 자막 스타일
- 음악
- 컷 템포
- 전환 방식
- CTA 위치

---

## 명시적 제외 항목

STUDY_STANDARD 기본 범위에서 **제외**한다. (오직 "어떻게 제작되었는가"만 기록)

- ❌ HARIN 적용안
- ❌ 브랜드 전략
- ❌ 비즈니스 모델
- ❌ 수익화
- ❌ 운영 철학
- ❌ 왜 이 영상을 만들었는가
- ❌ 어떻게 활용할 것인가
- ❌ NEEDS_DOC_UPDATE 기준
- ❌ PM 운영 원칙
