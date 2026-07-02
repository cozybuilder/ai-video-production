# Studies INDEX — 학습 자료 색인

AI 영상제작 학습 자료의 색인입니다. 사용자가 제공한 학습용 영상을 분석하여
재사용 가능한 지식 자산으로 축적합니다.

## 상태 정의

- `TO_ANALYZE` — 등록됨, 전체 분석 대기
- `IN_PROGRESS` — 분석 진행 중
- `SEMI_MEDIA_ANALYZED` — 미디어(MP4/WAV/SRT) 기반 1차 분석 완료
- `NEEDS_DOC_UPDATE` — 규칙 추출됨, 운영 문서 반영 필요/진행 중
- `ANALYZED` — 분석 완료, patterns 반영됨

## Study 표준 입력

- 모든 Study의 표준 입력은 **URL + MP4 + WAV + SRT** 4종이다. (근거: [study-006.md](study-006.md))

---

## 목록

### [study-001.md](study-001.md)
- **상태:** `SEMI_MEDIA_ANALYZED` · `NEEDS_DOC_UPDATE`
- **주제:** Claude/클챗 중심 제작 · Scene ID 기반 제작 · MCP 반복 작업 절감

### [study-003.md](study-003.md)
- **상태:** `SEMI_MEDIA_ANALYZED` · `NEEDS_DOC_UPDATE`
- **주제:** Brand-First AI 광고 제작 시스템 (에셋 라이브러리 · 체크리스트 기반)

### [study-006.md](study-006.md)
- **상태:** `NEEDS_DOC_UPDATE`
- **주제:** 광고 제작 워크플로우(Assets → Shot List → Scene Generation) & HARIN cut 단위 연출

---

## TODO — 운영 문서 반영 후보 (NEEDS_DOC_UPDATE)

> 아래는 study-001 / study-003의 운영 문서 반영 후보다. 실제 pm_playbook / camera_language 등
> 운영 문서 반영은 **별도 `NEEDS_DOC_UPDATE` 게이트**로 분리해 처리한다.

### study-001 반영 후보
- ☐ Claude/클챗 = 중심 제작 문서
- ☐ Scene ID 기반 제작
- ☐ MCP = 반복 작업 절감
- ☐ 특정 Scene만 수정하는 방식
- ☐ HARIN 제작 템플릿

### study-003 반영 후보
- ☐ Brand First, Campaign Second
- ☐ Asset Library Before Content
- ☐ Campaign Kit Template
- ☐ One Asset System → Many Outputs
- ☐ HARIN Brand Kit / Campaign Kit 분리
