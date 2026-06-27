# PEA-CORE™ V0.7 Implementation Sprint

## Sprint objective

Transform PEA-CORE™ V0.6 into a repository-ready, agent-orchestrated Web + Mobile/PWA pilot while keeping the production application separate from this public benchmark repository.

## Deliverables

1. Agent registry reinforced.
2. Routing matrix documented.
3. Human-gate policy documented.
4. GitHub integration plan documented.
5. n8n workflow blueprint aligned with agent routing.
6. CI smoke-check added for repository documentation hygiene.
7. Backlog for executable private product repository prepared.

## Workstreams

### WS1 — Application product repository

Recommended private repo name:

```text
PEFY-TECH/pea-core-executive-os
```

Tasks:

- import V0.6/V0.7 app package;
- preserve FastAPI backend;
- preserve PWA frontend;
- run smoke tests;
- validate Docker Compose;
- validate PostgreSQL;
- validate MinIO;
- validate n8n;
- prepare release tag `v0.7.0-agent-hub`.

### WS2 — Agent intelligence layer

Tasks:

- convert `AGENT_BLUEPRINTS.md` into JSON registry;
- add endpoint `/api/agents/route` if not already present;
- create `automation_run` on every route recommendation;
- require human approval for high-risk routes;
- store audit logs for agent decisions.

### WS3 — Security and governance

Tasks:

- enforce MFA for Super Founder and admin roles;
- add Redis rate limiting in Docker profile;
- add evidence immutability policy;
- implement admin-visible security events;
- run role-based endpoint tests.

### WS4 — Integrations

Tasks:

- keep Gmail/Calendar/Drive integration optional;
- prepare Nextcloud/MinIO storage validation;
- import n8n webhook workflows;
- add webhook token rotation procedure.

### WS5 — UX Web + Mobile

Tasks:

- improve project detail view;
- improve mobile navigation;
- add agent recommendation panel;
- add evidence missing badges;
- add cash/protection warning badges;
- add offline-friendly PWA shell.

## Acceptance criteria

| Criterion | Required result |
|---|---|
| App launches locally | Pass |
| Smoke test | Pass |
| PWA manifest | Pass |
| Auth/RBAC | Pass |
| MFA-ready | Pass |
| Evidence upload + SHA-256 | Pass |
| Agent route recommendation | Pass |
| High-risk route human-gated | Pass |
| n8n webhook protected | Pass |
| Audit logs visible | Pass |
| Docker Compose validates | Pass on developer machine |

## Next release target

```text
V0.7.0-agent-hub-integration
```

This release should be treated as an internal pilot baseline, not a production certification.
