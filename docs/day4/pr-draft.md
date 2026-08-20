# Pull Request Draft

Title: Fix: ticket status doesn't advance when an agent comments on a
New ticket (HD-23)

Purpose: tickets were staying in New status even after an agent
responded, because only assignment triggered a status change. This made
active tickets look untouched on the manager dashboard.

Summary of changes: added the missing New -> In Progress transition on
comment/update events; replaced the silent no-op for unmatched
transitions with an explicit error + log; added test coverage for both.

Evidence: new test reproduces the original bug and now passes; manual
repro in dev confirms the ticket moves out of New after a comment; full
test suite and linter pass.

Reviewer focus: please check whether anything else in the codebase was
relying on the old silent-failure behavior.

Known risks: touches the core state machine, which future
ownership/assignment work will build on top of.

Intentionally left out: notifications on this transition (still blocked
on a channel decision), anything related to ownership/assignment.
