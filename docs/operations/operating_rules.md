# Operating Rules — Rule Register

> Register = 현재 상태(Current State). 규칙의 생애를 단계로 관리한다.
> Rule은 실패에서 성장한다. (근거: [operating_philosophy.md](operating_philosophy.md) OP-007)

---

## Rule Lifecycle

```text
H  Hypothesis
↓
T  Testing
↓
C  Confirmed
↓
P  Principle
↓
R  Retired
```

## Confirmed 조건

- 표본 수(n)만으로 확정하지 않는다.
- **조건 명시** — 어떤 상황에서 성립하는지 기록.
- **Director Review** — 코비 검수 통과.

## Rule 필수 항목

모든 Rule은 반드시 다음을 가진다.

- **Gate Mapping** — 연결된 Gate ([gates.md](gates.md))
- **Decision Log 역참조** — 근거 결정 ([decision_log.md](decision_log.md))

## 변경 원칙

- Rule은 **변경이 발생했을 때만** 수정한다.
- 회고에서는 **Register Action**을 반드시 기록한다 — `변경없음`도 명시한다.

---

## Register

| Rule ID | 단계 | 조건 | Gate Mapping | Decision Log | Register Action |
|---------|------|------|--------------|--------------|-----------------|
| _(등록 대기)_ | | | | | |

관련: [pattern_register.md](../patterns/pattern_register.md) · [gates.md](gates.md)
