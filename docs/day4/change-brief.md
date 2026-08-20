# Repo-Ready Change Brief — HD-23

Change: fix the state machine so a comment/update from an agent on a ticket
in New status triggers a transition to In Progress. Currently only
assignment triggers that transition, so commented-on tickets can sit in
New indefinitely.

Source work item: HD-23, under the "Ticket Data & Workflow" epic —
logged as a bug during the Day 3 debugging investigation.

Purpose: make ticket status reflect real agent activity, so "stuck in
New" tickets stop being a visibility problem for managers.

Expected behavior: commenting on a New ticket moves it to In Progress;
any future case where no transition rule matches now logs/errors
explicitly instead of failing silently.

Files/modules likely affected: state machine module, comment/update
handler, state machine test file.

Evidence: a failing test that now passes, before/after logs showing the
transition firing, manual repro in dev confirming the ticket moves out
of New.
