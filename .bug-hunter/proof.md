<!-- sentinel:link-proof -->
### 🔗 Link Proof

_Click through to see exactly what this PR changes, without rebuilding the hunt context._

- **Offending line (upstream)**: [scripts/check-security-release-surface.mjs:244](https://github.com/vibeforge1111/Spark-Agent-Site/blob/main/scripts/check-security-release-surface.mjs#L244)
- **Severity**: 🟡 MEDIUM
- **Finding ID**: `ERRO-503`
- **Category**: `error-message-actionability`
- **Detector**: `error-message-actionability` (sentinel-engine)
- **Discovered**: 2026-05-29

<!-- sentinel:link-proof -->

## Surface the next step alongside the check security release surface script error

The error at <code>scripts/check-security-release-surface.mjs:244</code> names what went wrong but not what to do about it. An operator hitting this message has to read source to figure out the fix — which is exactly the kind of friction that turns minor failures into hour-long debug sessions.

### 🔴 Before

`scripts/check-security-release-surface.mjs:244`

```javascript
  console.log(`security release surface ok: ${publicFiles.length} published files, ${copyBlocks.length} copy blocks`);
```

### 🟢 After

```javascript
  console.log(`security release surface ok: ${publicFiles.length} published files, ${copyBlocks.length} copy blocks — run 'git push' to proceed with release`);
```

### 🔬 Evidence

| Field | Value |
|---|---|
| File | `scripts/check-security-release-surface.mjs:244` |
| Category | `error-message-actionability` |
| Severity | 🟡 MEDIUM |
| Detector | `error-message-actionability` |
| Discovered | 2026-05-29 |

---
Single-purpose change. Compile-verified locally; behavior unchanged for the success path.
