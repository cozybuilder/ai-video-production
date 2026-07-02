# Study 006 — 3-Step Workflow To Make Ultra-Realistic AI Ads

- URL: https://youtu.be/3rDs6FhFoUQ
- Source files: MP4 / WAV / SRT provided
- Study focus: AI 광고 제작 워크플로우, 사람→AI 지시 방식, Higgsfield/CDS 2.0 장면 생성 운영법
- 분석 원칙: 사람이 Claude/AI에게 입력하는 지시 방식만 학습한다. Claude가 생성한 최종 프롬프트 문장 자체는 학습 대상으로 삼지 않는다.

---

## 1. 핵심 요약

이 영상은 하나의 헤드폰 광고를 AI로 제작하는 전체 과정을 3단계로 설명한다.

1. **Asset 제작**  
   제품, 캐릭터, 장소, 소품을 먼저 만들고 테스트한 뒤, 움직임까지 버티는 에셋만 잠근다.

2. **Claude Skill 기반 Shot List 생성**  
   수작업으로 장면 프롬프트를 하나씩 쓰지 않고, Claude에 스크립트와 잠긴 에셋을 넣어 연결된 shot list를 만든다.

3. **CDS 2.0 / C Dance 장면 생성과 반복 수정**  
   첫 결과를 그대로 쓰지 않고, 깨지는 부분을 진단한 뒤 Claude에게 특정 프롬프트/특정 장면만 수정시킨다.

핵심은 “한 번에 완성”이 아니라 **에셋 테스트 → 고정 → 프롬프트 시스템화 → 장면별 실패 수정 → 좋은 몇 초만 편집**이다.

---

## 2. 3-Step Workflow

### Step 1. Assets — 먼저 만들고, 테스트하고, 잠근다

영상 제작자는 바로 영상을 만들지 않는다. 먼저 아래 에셋을 생성한다.

- 제품: 헤드폰 product sheet
- 주인공: character sheet
- 보스: side character sheet
- 장소: kitchen, stadium, street corner, office
- 소품: moka pot, mug, sneakers 등

중요한 방식은 다음과 같다.

- 제품은 한 장이 아니라 여러 각도 product sheet로 만든다.
- 주인공은 얼굴 close-up과 full-body를 함께 만든다.
- 배경은 gray background가 win rate가 높다고 설명한다.
- 캐릭터는 한 장만 고르지 않고 여러 후보를 실제 영상으로 테스트한다.
- 장소도 still image만 보고 결정하지 않고, 같은 프롬프트로 테스트해서 움직임까지 확인한다.
- 테스트할 때는 한 번에 하나만 바꾼다. 예: 같은 hero, 다른 kitchen / 같은 kitchen, 다른 hero.
- 테스트에서 이긴 에셋만 canvas 상단에 올려 “locked asset”으로 관리한다.

### Step 2. Shot List — Claude를 프롬프트 작가가 아니라 편집 가능한 시스템으로 쓴다

제작자는 Claude에 다음 3가지를 넣는다.

1. 광고 script
2. locked asset 전체
3. 각 에셋의 이름

그리고 Claude Skill을 사용해 C Dance 2.0용 shot list를 만든다.

중요한 점은 결과를 “분리된 프롬프트 묶음”으로 보지 않고, 하나의 연결된 문서로 본다는 것이다.

- 상단에는 전체 스타일 prefix가 있다.
- lighting, camera, color 같은 공통 룩을 한 번에 바꿀 수 있다.
- 각 prompt에는 1A, 1B, 2A 같은 이름이 붙어 있다.
- 사용자는 Claude에게 “edit prompt 1A only”처럼 특정 프롬프트만 수정시킨다.

이 방식의 장점은 20개의 느슨한 채팅을 관리하지 않고, 하나의 광고 문서를 편집하듯 운영할 수 있다는 점이다.

### Step 3. Scene Generation — 첫 결과는 깨진다고 보고, 문제를 좁혀 고친다

장면 생성 단계에서는 첫 결과를 바로 쓰지 않는다. 결과를 보고 다음을 점검한다.

- 조명이 광고 톤에 맞는가
- 카메라가 움직이는가
- 한 컷 안에 너무 많은 액션이 들어갔는가
- 소품이 컷마다 바뀌지 않는가
- 캐릭터 의상/얼굴이 유지되는가
- 장면 전환 match cut이 맞는가
- 동작이 “춤춘다”처럼 뭉개져 있지 않은가

수정은 Claude에게 다시 요청한다. 단, 전체를 갈아엎는 게 아니라 특정 prompt 또는 특정 cut만 수정한다.

---

## 3. 사람이 AI에게 입력한 핵심 지시 패턴

아래 문장들은 SRT에서 확인된 사람의 지시 구조를 의미 중심으로 정리한 것이다. Claude가 생성한 최종 프롬프트가 아니라, 제작자가 AI에게 어떤 방식으로 요청했는지만 기록한다.

### 3.1 제품 기준 정보 만들기

- “제품 이미지를 front와 three-quarter perspective가 있는 product sheet로 만들어라.”
- 목적: 모델이 제품을 여러 각도에서 이해하도록 해서 hallucination을 줄임.

패턴:
```text
제품 1장 → 여러 각도 product sheet 생성 → 이후 모든 영상 생성에서 기준 이미지로 사용
```

### 3.2 캐릭터 시트 만들기

- “젊은 남성 캐릭터 시트 프롬프트를 만들어라. close-up과 full body front/back, gray background.”
- 목적: 얼굴과 체형을 동시에 고정.

패턴:
```text
캐릭터 = 얼굴 기준 + 전신 기준 + 회색 배경 + 여러 후보 생성 + 영상 테스트 후 잠금
```

### 3.3 보조 캐릭터는 과투자하지 않기

- “50대 사무실 보스, 배 나온 남자, suit, 화난 인상.”
- 목적: 주인공만큼 리소스를 쓰지 않고 빠르게 기능성 캐릭터 확보.

패턴:
```text
주인공은 정밀하게 / 보조 인물은 역할만 선명하게
```

### 3.4 장소 생성 지시

- “modern apartment kitchen, three-quarter angle, bright clean daylight, high-end commercial look.”
- “running track, three-quarter view, sunny day.”

패턴:
```text
장소 프롬프트 = 공간 종류 + 3/4 angle + 빛 + 광고 톤
```

핵심은 flat front view보다 3/4 angle이 영상 모델의 카메라 이동을 버티기 좋다는 점이다.

### 3.5 에셋 테스트 지시

- “hero walks into the kitchen, headphones on, dances a little.”
- “he runs along the track in headphones.”

패턴:
```text
같은 짧은 테스트 프롬프트를 반복 사용하고, 에셋만 바꿔서 승자를 찾는다.
```

이는 프롬프트 실험이 아니라 에셋 실험이다. 한 번에 여러 변수를 바꾸지 않는다.

### 3.6 장소 이미지 편집 지시

- “kitchen island를 비워라.”
- “left counter에 gas stove를 추가해라.”
- “right wall의 TV를 제거하고 door를 넣어라.”
- “나머지는 그대로 유지해라.”

패턴:
```text
이미 좋은 장소는 새로 만들지 않고, 필요한 기능만 정확히 편집한다.
```

### 3.7 캐릭터 시트 오류 수정

- “오른쪽 full body panel에서 얼굴을 지워라.”

목적: 한 이미지 안에 얼굴이 여러 개 있으면 영상 모델이 어느 얼굴을 따라야 할지 헷갈리므로, 얼굴 기준을 하나로 줄인다.

패턴:
```text
영상 모델용 reference는 얼굴 기준을 하나로 만든다.
```

### 3.8 의상 아이디어 요청

- “이 캐릭터에게 어울리는 casual outfit 10개를 프롬프트로 써라.”
- “두 번째 룩의 shirt를 pink로 바꾸고, 첫 번째 룩의 jeans를 결합해라.”

패턴:
```text
Claude에게 스타일 후보를 많이 만들게 한 뒤, 마음에 드는 요소를 조합한다.
```

### 3.9 Shot List 생성 지시

- script, locked asset, asset name을 Claude에 넣고 C Dance 2.0용 shot list를 요청한다.

패턴:
```text
Claude 입력 = 완성된 script + 잠긴 에셋 전체 + 에셋 이름
Claude 출력 = 장면별 shot list + 공통 style prefix + 개별 prompt ID
```

### 3.10 공통 스타일 prefix 수정

- “전체 shot list의 style prefix를 바꿔라.”
- “contre jour와 shadow side framing을 제거하라.”
- “camera side에서 오는 soft even daylight, bright clean 룩으로 바꿔라.”
- “모든 prompt에 적용하라.”

패턴:
```text
전체 룩 문제는 scene마다 고치지 말고 prefix에서 한 번에 고친다.
```

### 3.11 특정 프롬프트만 수정

- “prompt 1A만 수정해라.”
- “shot이 뒤에서 시작해 profile로 돌아가게 하라.”
- “static wide를 없애라.”
- “coffee 동작은 짧게 줄여라.”

패턴:
```text
전체 문서를 유지한 채, 특정 prompt ID만 surgical edit한다.
```

### 3.12 복잡한 액션은 별도 prompt로 분리

coffee making이 한 컷에 들어가면 rushed/flat해지므로 1B로 분리한다.

패턴:
```text
한 컷에 액션이 너무 많으면 새 prompt로 분리한다.
```

### 3.13 소품 고정

- “moka pot과 mug가 kitchen에 맞는 prompt를 만들어라.”
- “mocha cream과 mug cream을 exact reference로 lock하라.”

패턴:
```text
클로즈업에 나오는 소품은 반드시 별도 reference로 잠근다.
```

### 3.14 추상 동작 금지, 움직임을 쪼개서 지시

- “he dances”라고 하지 않는다.
- “two head nods, shoulder roll, knee dip, finger snap, quarter spin”처럼 동작을 순서대로 쓴다.

패턴:
```text
추상동사 금지 → 동작을 beat 단위로 쪼개기
```

### 3.15 캐릭터 상태 변화는 reference를 분리

운동 전/후처럼 캐릭터 상태가 바뀌면 dry hero와 wet hero를 별도 sheet로 만든다.

패턴:
```text
한 reference에 상태 변화를 말로 강요하지 말고, 상태별 reference를 만든다.
```

### 3.16 scene별 lighting override

공통 prefix는 kitchen에는 맞았지만 stadium에는 맞지 않았으므로, stadium scene만 bright sunny midday로 override한다.

패턴:
```text
공통 prefix를 기본값으로 쓰되, scene 고유 룩이 필요하면 해당 scene만 override한다.
```

### 3.17 Match Cut 수정

- “2A opening tap을 1C closing tap과 정확히 맞춰라.”
- “same hand, same motion.”

패턴:
```text
장면 연결부는 마지막 동작과 다음 첫 동작을 같은 pose/motion으로 맞춘다.
```

### 3.18 제품 전용 shot 만들기

- “middle을 body rig / snorricam shot으로 바꿔라.”
- “right ear cup이 dead center에 고정되고 배경만 motion blur로 지나가게 하라.”

패턴:
```text
광고에서는 제품만 보이는 hero product shot을 반드시 별도로 만든다.
```

### 3.19 위치 고정을 위한 schematic map

street scene에서 hero 방향과 sky dancer 위치가 계속 바뀌자, 텍스트만으로 해결하지 않고 schematic map을 만든다.

- “fire hydrant를 표시하고, sky dancer를 오른쪽에 고정하라.”
- “sky dancer는 사람 키의 두 배, 같은 라인에 위치.”

패턴:
```text
공간 배치가 계속 깨지면 말로 설명하지 말고 map/reference image로 고정한다.
```

### 3.20 음악을 입력으로 넣어 beat에 맞추기

- “music track을 input으로 넣고, hero가 beat에 맞춰 춤추게 하라.”

패턴:
```text
음악 기반 영상은 음악 파일을 입력으로 넣고, 동작을 beat에 맞춘다고 명시한다.
```

---

## 4. 영상에서 배울 운영 원칙

### 4.1 에셋이 프롬프트보다 먼저다

처음부터 장면을 생성하면 실패 비용이 커진다. 먼저 캐릭터/장소/제품/소품을 만들고, 움직임 테스트를 통과한 것만 사용한다.

### 4.2 Still image가 좋아도 영상에서 무너지면 탈락

좋은 이미지가 좋은 영상 에셋이라는 보장은 없다. 반드시 짧은 테스트 영상을 돌려야 한다.

### 4.3 한 번에 하나만 바꾼다

hero와 kitchen을 동시에 바꾸면 무엇이 문제인지 모른다. 같은 prompt에 하나의 변수만 바꿔야 원인이 보인다.

### 4.4 Claude는 “프롬프트 생성기”가 아니라 “연결된 광고 문서 편집기”로 써야 한다

개별 prompt를 매번 새로 쓰는 게 아니라 shot list, prefix, prompt ID를 가진 하나의 시스템으로 운영한다.

### 4.5 추상어는 실패한다

“dance”, “cinematic”, “dynamic”만 쓰면 움직임이 뭉개진다. 실제 동작, 카메라 위치, cut 순서, 손/몸/발의 움직임을 지정해야 한다.

### 4.6 텍스트로 안 잡히는 것은 이미지 reference로 잡는다

위치, 크기, 방향, 동선이 흔들리면 schematic map을 만든다.

### 4.7 좋은 광고는 한 번의 생성물이 아니라 수많은 실패 중 좋은 몇 초를 이어붙인 결과다

영상 마지막에서 제작자는 “finished ad is just the best few seconds out of 100 tries cut together”라고 설명한다. 핵심 기술은 iteration이다.

---

## 5. HARIN 프로젝트 적용안

### 5.1 HARIN 광고형 영상 제작 표준 구조

HARIN 영상도 바로 Higgsfield에 장면 프롬프트를 넣지 않는다.

1. HARIN locked reference 준비
   - 얼굴 close-up
   - full body
   - outfit sheet
   - 표정 sheet
   - 손/포즈 reference 필요 시 별도

2. 장소 locked reference 준비
   - 스튜디오
   - 카페
   - 거리
   - 제품 촬영 공간
   - 각 장소는 3/4 angle 우선

3. 테스트 영상 생성
   - 같은 prompt로 HARIN reference 후보만 바꿔 테스트
   - 같은 HARIN으로 장소만 바꿔 테스트
   - 움직임이 무너지면 탈락

4. Claude/클챗에 shot list 요청
   - script
   - locked assets
   - asset names
   - platform: Instagram Reels / Shorts
   - duration: 15~40s
   - output: prompt IDs + common style prefix

5. Higgsfield/CDS 생성
   - scene별 생성
   - 실패 원인별 수정
   - 좋은 2~4초만 편집

### 5.2 HARIN 프롬프트 작성 원칙

- “하린이가 예쁘게 걷는다” 금지
- “하린이가 제품을 소개한다” 금지
- “광고처럼”만 쓰는 것 금지

대신:

```text
cut 1: close-up, HARIN turns her head slightly toward camera, soft smile, eyes lock to lens
cut 2: medium shot, she lifts the product with right hand, left hand supports the bottom
cut 3: over-the-shoulder product shot, camera pushes in, product label dead center
cut 4: close-up, she taps the product once, smiles, then looks back to camera
```

처럼 cut 단위, 손/시선/몸/카메라를 명시한다.

### 5.3 HARIN 광고 영상에서 반드시 만들 에셋

- HARIN main face reference
- HARIN full body reference
- HARIN outfit reference
- 제품 product sheet
- 장소 reference
- 소품 reference
- 필요 시 layout map
- 음악 파일 또는 beat description

### 5.4 쇼츠/릴스용 추가 규칙

- 제품 shot을 반드시 1개 이상 넣는다.
- 얼굴 shot과 제품 shot을 분리한다.
- 움직임이 큰 장면은 2~3초 단위로 쪼갠다.
- 마지막 1~2초는 업로드용 루프/CTA로 설계한다.

---

## 6. NEEDS DOC UPDATE 판단

NEEDS DOC UPDATE.

이 Study는 단순 참고가 아니라 AI 영상제작 운영 방식에 반영해야 할 규칙을 포함한다.

문서 반영 대상:

1. Study 입력 표준
   - URL + MP4 + WAV + SRT

2. AI 광고 제작 표준 워크플로우
   - Assets → Shot List → Scene Generation

3. 에셋 잠금 원칙
   - 제품/캐릭터/장소/소품을 먼저 만들고 테스트 후 locked asset으로 관리

4. Claude/클챗 사용 원칙
   - 단발 프롬프트 생성기가 아니라 connected shot list editor로 사용

5. Higgsfield/CDS 장면 생성 원칙
   - scene별 실패 진단 후 prompt ID 단위로 수정

6. HARIN 적용 규칙
   - 추상 동작 금지
   - 동작/카메라/시선/손/제품 위치를 cut 단위로 작성
   - 위치가 흔들리면 schematic map 사용

---

## 7. 클로 저장 지시 필요

파일 저장 위치 제안:

- `docs/studies/study-006.md`
- 필요 시 `docs/playbooks/ai-ad-workflow.md` 또는 기존 AI 영상제작 플레이북 문서에 핵심 규칙 반영

클로 작업 범위:

1. `docs/studies/study-006.md` 신규 저장
2. AI 영상제작 운영 문서에 Study 입력 표준 반영
3. 광고 제작 플레이북에 3-Step workflow 반영
4. commit/push
5. Public GitHub 실문서 확인 대상 보고
