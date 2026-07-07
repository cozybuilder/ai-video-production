# Gates

> Gate는 실수를 막는다. (근거: [operating_philosophy.md](operating_philosophy.md) OP-004)

---

## 자동 연결 구조

```text
Rule → Gate
Asset → Gate
```

- 모든 Confirmed Rule은 **최소 하나 이상의 Gate와 연결**한다.
- Asset도 Gate와 연결해 잘못된 자산 사용을 막는다.

---

## Gate Register

| Gate ID | 연결 대상 (Rule/Asset) | 차단 조건 |
|---------|------------------------|-----------|
| _(등록 대기)_ | | |

관련: [operating_rules.md](operating_rules.md) · [asset_register.md](asset_register.md)
