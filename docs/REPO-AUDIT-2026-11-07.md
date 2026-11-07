# Repository audit — 2026-11-07

Repository: `CKA-learning` · Agent: Codex

Audited source: [`52111f5`](https://github.com/110kc3/CKA-learning/commit/52111f52e09ccd90b93c9f30f8c0bc4929a9b383)

Evidence collected: 2026-11-06–2026-11-07. Chat item numbers: 33.

This dated report preserves the findings and feature suggestions already reported in chat.
The owner authorized recording, committing and pushing this documentation. The findings
remain unresolved, and the proposed features have not been selected for implementation.
This is an evidence report, not a second accepted work queue. Existing project decisions,
accepted tasks and owner-only blockers remain authoritative in [README.md](../README.md).

## Verification status

The evidence below describes the earlier audit, including its limitations. This documentation
change does not claim to fix the findings or repeat every runtime reproduction. No production
account, database or infrastructure was changed by those isolated reproductions.

Documentation push: CI verification pending. Check the exact resulting commit on the next
session using [Actions](https://github.com/110kc3/CKA-learning/actions?query=branch%3Amain);
no run was awaited for this documentation update. A repository without a workflow has no
CI result to claim.

## 33. Kubernetes training examples contain invalid fields

Type: Open finding — not fixed. Priority: Medium. Estimated effort: Small.

The ReplicationController example uses kind Replicationontroller; taint notes use NoSchedue; tolerations are nested under a container rather than the Pod specification.

**Evidence:** See [controller example](../templates/replicationcontroller-def.yaml), [taint notes](../notes-taints.yaml) and [official toleration examples](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/). No cluster changes were made.

**Suggested change:** Correct the spellings and nesting, and distinguish prose notes from apply-ready YAML examples.

**Acceptance if selected:** Manifest examples pass schema validation; taint examples use valid effects; tolerations appear under spec and match the intended taint.
