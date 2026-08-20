# Commit Sequence

1. Add failing test reproducing missing comment-triggered transition (HD-23)
2. Document branch scope and boundaries (HD-23)
3. Add New -> In Progress transition rule triggered by comment event
4. Replace silent no-op on unmatched transition with explicit error and log (HD-23)
5. Extend state machine tests: comment-triggered transition + unmatched-transition case
6. Add doc note describing new transition and error behavior (HD-23)

Each commit is a step someone could read on its own and understand —
no "updates," "fixes," or "final."
