# Study 006 — 광고 제작 워크플로우 & Connected Shot List

- **상태:** `NEEDS_DOC_UPDATE`
- **주제:** AI 광고 제작 파이프라인 (Assets → Shot List → Scene Generation) 및 HARIN cut 단위 연출
- **표준 입력:** URL + MP4 + WAV + SRT

> ⚠️ 이 문서는 코비 저장 지시서의 **규칙 목록**을 근거로 작성되었습니다.
> 원본 학습 자료(URL / MP4 / WAV / SRT)가 첨부되면 상세 관찰을 보강하고
> 상태를 `ANALYZED` 로 승격합니다. (자세한 상태 정의: [INDEX.md](INDEX.md))

---

## 핵심 학습 (Extracted Rules)

### 1. Study 표준 입력
- 모든 Study의 표준 입력은 **URL + MP4 + WAV + SRT** 4종이다.
- 영상(MP4) 외에 음성(WAV)·자막(SRT)·출처(URL)를 함께 확보해야 완전한 자산이 된다.

### 2. 광고 제작 워크플로우
- 표준 흐름: **Assets → Shot List → Scene Generation.**
- 에셋을 먼저 확정하고, 샷 리스트를 짠 뒤, 장면을 생성한다. 순서를 건너뛰지 않는다.

### 3. Locked Asset 관리
- 에셋은 **먼저 생성/테스트한 후 `locked asset` 으로 관리**한다.
- 승인·고정된 에셋만 실제 장면 생성에 투입한다. (HARIN 고정축 원칙과 정합)

### 4. Connected Shot List Editor
- Claude / 클챗은 **단발 프롬프트 생성기가 아니다.**
- **connected shot list editor** 로 사용한다 — 샷 간 연결/일관성을 유지하며 편집한다.

### 5. Prompt ID 단위 수정
- Higgsfield / CDS 장면은 **prompt ID 단위로 수정**한다.
- 전체를 새로 만들지 않고, 문제 장면의 prompt ID만 지정해 수정/재생성한다.

### 6. HARIN cut 단위 명시
- HARIN 영상은 **추상 동작 금지.**
- **cut 단위로 동작 / 시선 / 카메라 / 제품 위치를 명시**한다.

### 7. Schematic Map
- 위치가 흔들리면 **schematic map(배치 도식)** 을 사용해 고정한다.

---

## 운영 문서 반영 (완료)

| 규칙 | 반영 위치 |
|------|-----------|
| 1 (표준 입력) | [pm_playbook.md](../operations/pm_playbook.md) §7, [INDEX.md](INDEX.md) |
| 2~5 (워크플로우/에셋/에디터/prompt ID) | [pm_playbook.md](../operations/pm_playbook.md) §12 |
| 6~7 (cut 명시/schematic map) | [camera_language.md](../patterns/camera_language.md) |

## 후속 조치
- 원본 입력(URL+MP4+WAV+SRT) 확보 시 상세 관찰 보강 → 상태 `ANALYZED`
- 검증된 조합은 `proven_recipes` 로 승격
