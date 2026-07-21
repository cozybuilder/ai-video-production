# H4 Keyframe Sequence — 상세 이력 (Asset 상세 SSOT)

> 자산명: **H4 Keyframe Sequence** · Layer: **Output / Keyframe** · 현재 상태: **candidate**
> 이 문서가 H4 키프레임 이력의 SSOT다. 상위 [asset_register.md](asset_register.md)에는 요약행 + 본 문서 링크만 둔다(중복 금지).
> 관련: [DL-004 이미지 승인 전 영상 생성 금지](decision_log.md) · [identity_rules](../characters/harin/identity_rules.md) · [camera_language](../patterns/camera_language.md)

## 상태 정의

- **candidate**: 원본 확보·검증 전 승인 후보(현재 단계).
- **freeze**: 원본 확보·무결성 확인·픽셀 검증·최종 승인 완료.
- **Rebuild**: 재제작 대상.

## 정식 freeze 전제 (미완)

원본 파일 확보 → 파일명·해상도·무결성 확인 → 픽셀 1:1 검증 → 최종 승인. **네 단계 모두 미완**이므로 freeze 아님.

## 현재 승인 근거·제한

- 승인 근거: 브라우저(Chrome) **원본 화면**과 **비교 몽타주(S1↔S2, 5컷 전체)** 육안 검수 + 코비 컷별 검수.
- 제한: 원본 PNG의 **저장소 확보 미완(CDN 403)**, 픽셀 1:1 검증·정식 freeze 미완료.

## 확정 후보 5컷

기준: HARIN 얼굴·긴 생머리(풀림)·크림 립드 니트 고정축 유지 / 웜 앰버 톤 / 9:16 / Element `HARIN_S1_SOULID_V1` (b6ded67b) · 모델 Nano Banana Pro 2k.
연속성 기준: 현관 S1=S2, 거실 S3=S4=S5.

| Scene ID | Job ID | 해상도 | 승인 상태 | 원본 확보 | 검증 범위 | 연속성 기준 | 후속 보정 |
|----------|--------|--------|-----------|-----------|-----------|-------------|-----------|
| S1 | e9114f7c-fe32-4ee3-9b99-acc96d43c6b8 | 1536×2752 | candidate(승인) | 미확보 | Chrome 원본 육안 | 현관 기준본 | 없음 |
| S2 | fabaa6f9-4f0a-4658-b4cd-421c217ba3b7 | 1536×2752 | candidate(승인) | 미확보 | Chrome 원본 육안+비교몽타주 | 현관 S1과 일치 | 없음 |
| S3 | eb457af9-9581-498b-9ee2-9d842fb0ac7d | 1536×2752 | candidate(승인) | 미확보 | Chrome 원본 육안 | 거실 기준본 | 없음 |
| S4 | 0b265e39-bd70-46d5-b233-9c164df74652 | 1536×2752 | candidate(승인) | 미확보 | Chrome 원본 육안 | 거실 S3와 일치 | **Motion 이후 앱 UI 합성 시 휴대폰 화면 코너핀·원근 보정 대상** |
| S5 | 353fac7c-28d5-45a8-8c2f-51e4812f0a2e | 1536×2752 | candidate(승인) | 미확보 | Chrome 원본 육안 | 거실 S3와 일치 | 없음 |

원본 CDN 접두: `https://d8j0ntlcm91z4.cloudfront.net/user_3FAPRoj6oqgUbGVQ2ZKNpzlkYJb/`
원본 파일명·체크섬·저장 경로: **미확보** (추정 기재 금지).

## 폐기 이력

| 폐기 Job ID | 사유 |
|-------------|------|
| 84514fa2-b628-42ab-b9fc-f35b3af00d56 (구 S2) | 헤어(묶은 번)·현관 세트 S1과 불일치 → S2 교정 재생성으로 대체 |
| 099fac33-b8cc-43fc-9351-6e15a0622d05 (구 S5) | 거실 세트(둥근 무드등+주방) S3와 불일치 → S5 교정 재생성으로 대체 |
| f9a0dc01-f9ce-450a-8a21-e21c4f3ca63f (S5 재시도 실패) | 폰이 무릎 중앙 아닌 소파 방석 위 배치 → 재시도로 대체 |

## 비용

- 누적 30.36cr / 확인 시점 잔액 1,806.61cr. (본 문서 반영 작업은 이미지·영상 생성 0회, 크레딧 0cr.)

## 다음 단계 (승인 후) — 병렬 2트랙

Motion 제작과 원본 확보는 **서로의 선행조건이 아니다**(병렬 진행 가능). Motion 입력은
아래 표에 등록된 **승인 Job ID만** 사용한다(image-to-video의 start_image = Job ID).
원본 PNG 확보·freeze는 자산 보존 트랙으로 분리한다.

### 트랙 A — Motion 제작 (Job ID 기반, 지금 진행 가능)
- 선행조건: 위 5컷이 candidate(승인) 상태일 것 (충족). 원본 PNG 확보·freeze는 선행조건 아님.
- 입력: 등록된 승인 Job ID만 사용(폐기 Job 사용 금지). DL-004(이미지 승인 전 영상 생성 금지) 충족.
- 착수안 SSOT: [motion-plan-h4.md](motion-plan-h4.md).
- S4는 Motion 이후 앱 화면 후반 합성(코너핀·원근) 대상 — 별도 승인·코지 제공 녹화본 필요.

### 트랙 B — 원본 확보·freeze (자산 보존, 후속 분리)
- 원본 파일 확보 → 파일명·해상도·SHA-256·무결성 → 픽셀 1:1 검증 → freeze 승격.
- 현재 candidate 유지. 원본 미확보 상태 유지. Motion 진행과 무관하게 별도로 완료한다.
- 확보 경로·저장 정책은 코지·코비 지시 대기(리포+LFS vs 외부 원본+문서 체크섬).
