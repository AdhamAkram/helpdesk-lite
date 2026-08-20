# Merge and Release Checklist

Before merge:
- at least one reviewer approval
- every required-change comment addressed
- CI green: linter + full test suite including new tests
- no unresolved review threads
- branch up to date with main

Before release / production use:
- approved, merged, deployed, released are separate checkpoints
- merged = code in main, not live anywhere yet
- deployed = running in staging/prod, verify under real-ish volume
- released = actually active for real users — confirm with team since
  this touches shared state-machine logic future work builds on
- confirm logging/monitoring would actually surface a similar silent
  failure in the future, not just in this one code path
