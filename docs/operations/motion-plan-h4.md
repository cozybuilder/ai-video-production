# H4 Motion 착수안 (Motion Plan SSOT)

> H4 「귀가」 15초 광고의 image-to-video(Motion) 제작 계획. 입력은 [asset-keyframes-h4.md](asset-keyframes-h4.md)에 등록된 **승인 Job ID(start_image)만** 사용한다.
> 상태: **CEO 승인 대기 — 이번 배치 실제 생성 0건·크레딧 0.** 관련: [DL-004 이미지 승인 전 영상 생성 금지](decision_log.md) · [00_START_HERE §5](../../00_START_HERE.md).

## 공통 원칙

- 입력: 컷별 승인 Job ID를 i2v의 start_image로 사용(원본 PNG 파일 불요). 폐기 Job(84514fa2/099fac33/f9a0dc01) 사용 금지.
- 사운드: **off**(BGM·내레이션 없음, 자연 효과음은 후반 편집에서 추가) → 크레딧 절감.
- 비율 9:16. 컷 목표 길이는 15초 편집 기준이며, i2v 최소 길이(3초) 이상 생성 후 편집에서 트림.
- 자막·텍스트·워터마크·가짜 UI 생성 금지. 정면 응시 전환 금지. 과장 표정 금지.
- 후반 자막·음성·BGM·CTA는 코지가 편집에서 추가(생성 원본에 미포함).

## i2v 모델 후보 (계정 실측 단가)

| 모델 | 강점 | start_image | 9:16 | 사운드 | 실측/카탈로그 단가 |
|------|------|-------------|------|--------|--------------------|
| Kling 3.0 Turbo | 저비용·빠름, 자연 모션 | ✅ | ✅ | on/off | 계정 실측 ~7.5cr/클립 |
| Kling v3.0 (std) | 시네마틱·물리, 안정 | ✅(start/end) | ✅ | on/off | 계정 실측 ~10cr/클립 |
| Seedance 2.0 | 레퍼런스 기반 정체성 | ✅ | ✅ | 옵션 | 미측정(생성 직전 preflight) |
| Veo 3 | 신뢰도 높은 시네마틱 | ✅ | ✅ | 옵션 | 미측정 |

> 정확 단가는 **생성 직전 get_cost 프리플라이트로 확정**한다(위 값은 이력 기준 추정).

## 컷별 Motion 설계

| 컷 | 승인 Job ID(start_image) | 목표 길이 | 의도 | 인물 동작(미세) | 카메라 | 금지·연속성 위험 |
|----|--------------------------|-----------|------|------------------|--------|-------------------|
| S1 | e9114f7c | ~3.0s | 귀가 직후 안착, 훅 | 어깨 내려가는 호흡 1회, 시선이 문→실내로 아주 천천히 | locked 또는 아주 느린 push-in | 문 여닫는 큰 동작 금지 / 벽에 댄 손 morph / 정면 응시 전환 금지 |
| S2 | fabaa6f9 | ~3.0s | 가방 내려놓기 마무리 | 상체가 내려가며 가방이 바닥에 닿고 손을 놓음 | locked | 손가락 개수 변화 / 가방 형태 붕괴 / 과한 허리 굽힘 |
| S3 | eb457af9 | ~3.0s | 폰으로 손 뻗음 | 손이 폰 향해 계속 내려가 닿기 직전에서 정지 | gentle push-in | 폰 화면 발광·UI 출현 금지 / 손-폰 근접 morph / 폰 집어 얼굴로 가져오는 동작(다음 컷 영역) 금지 |
| S4 | 0b265e39 | ~3.0s | 입력 동작 | 검지가 화면을 1~2회 가볍게 탭 | locked | **화면 무발광 유지 필수**(후반 합성) / 텍스트·UI 생성 금지 / 손가락 다수화 / 폰 기울기 급변(합성 원근 안정) |
| S5 | 353fac7c | ~3.0s | 긴장 이완, 마무리 | 아주 미세한 호흡·어깨 이완, 눈 감은 채 정지에 가까움 | 아주 느린 dolly back 또는 locked | 눈 크게 뜨기·큰 미소 금지 / 폰이 무릎에서 미끄러짐 금지 |

## 첫 Motion 테스트 1컷 (전체 동시 생성 금지)

- **추천: S1 (Job e9114f7c)**
- 선정 근거: ① 훅 컷이라 첫인상 검증 가치 최고 ② 모션이 통제 가능(호흡·시선 미세)해 실패 위험 낮음 ③ HARIN 정체성·웜 앰버 톤·i2v 파이프라인 적합성을 대표적으로 1회에 검증. 유일 리스크(벽에 댄 손)는 손 동작이 거의 없어 낮음.
- 대안(초저위험 확인용): S5(거의 정지) — 정체성 유지만 최소 비용으로 확인하고 싶을 때.
- 제외(첫 테스트 부적합): S3·S4(손-폰 상호작용 morph 위험 최고) — 파이프라인 안정 확인 후로 미룸.

### 첫 테스트 생성 설정(안)
- 모델: Kling 3.0 Turbo(저비용 우선) 또는 Kling v3.0 std / start_image=e9114f7c / 9:16 / sound=off / duration 3~5s
- 예상 비용: Turbo ~7.5cr(또는 v3.0 ~10cr), 생성 직전 preflight 확정. 재시도 포함 상한은 별도 승인.
- 프롬프트(초안): `From the start frame, keep her identity, hairstyle, cream knit and the warm amber entryway unchanged. Subtle natural motion only: one soft breath as her shoulders ease down, her gaze drifting slowly from the door into the room. Locked camera or very slow push-in. She never turns to face the camera. Hands and fingers stay stable. No subtitles, no captions, no on-screen text, no interface, no watermark. Quiet, warm, realistic; not eerie.`

### 성공 / 실패 판정 기준
- 성공: ① 얼굴·헤어·의상 정체성 전 프레임 유지 ② 웜 앰버 톤·현관 세트 유지 ③ 정면 응시로 돌지 않음 ④ 손·손가락 형태 유지 ⑤ 자연스러운 미세 모션(공포·기괴 없음) ⑥ 텍스트·워터마크·화면 발광 오염 없음.
- 실패: 위 중 하나라도 위반(특히 얼굴 정체성 붕괴·정면 응시·손 morph·화면 발광). 실패 시 원인 1줄 특정 후 설정 조정하여 상한 내 재시도.

## 예상 크레딧 (참고 — 실제 생성은 별도 승인)

- 첫 테스트 1컷: ~7.5cr(Turbo) / ~10cr(v3.0)
- 5컷 파이널(v3.0 std, sound off, 이력 기준): ~10cr × 5 = ~50cr + 재시도 여유 → 상한은 별도 승인
- 이번 배치(문서화): 생성 0회 / 크레딧 0cr

## 이번 배치에서 하지 않는 것

이미지 재생성 · Motion 실제 생성 · 크레딧 사용 · 승인 Job ID 교체 · candidate→freeze 승격 · 폐기 Job 사용 · S4 앱 UI 합성 · 실기기 녹화 요구 · 원본 PNG 확보 요구.
