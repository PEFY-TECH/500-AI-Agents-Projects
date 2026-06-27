# PEA-CORE™ Security & Governance Guardrails

PEA-CORE™ is founder-centric and evidence-first. Its agent layer must remain controlled, auditable and non-destructive.

## Security baseline

| Domain | Minimum control |
|---|---|
| Authentication | Strong password, MFA-ready, token expiry. |
| Authorization | RBAC with Super Founder, Executive Assistant, Project Manager, Finance/Admin, Legal/Compliance, Auditor and Viewer. |
| Sensitive actions | Human approval mandatory. |
| Evidence | SHA-256 hash, immutable flag, role-restricted download. |
| Logs | Audit trail for login, create/update, gate review, agent routing, exports and evidence downloads. |
| Webhooks | Token-protected n8n endpoints. |
| Rate limiting | Local MVP limiter, Redis for pilot/production. |
| Storage | Local for dev; MinIO/Nextcloud-ready for pilot. |
| External integrations | No integration before security review. |

## Human-gated actions

The following actions must always require human validation:

- external email sending;
- file sharing;
- partner onboarding;
- contract or MOU approval;
- payment validation;
- deleting or modifying critical evidence;
- creating external user access;
- publishing or exporting sensitive documents;
- enabling autonomous workflow execution.

## Evidence-first rule

Every critical business action must produce or link evidence:

```text
Request -> Classification -> Gate Review -> Action -> Evidence -> Decision -> Audit Log
```

## Founder protection checks

Every partnership or external work request must check:

- NDA;
- MOU/contract;
- payment/mandate;
- IP ownership;
- confidentiality;
- non-circumvention;
- revenue/control clarity;
- exit clause;
- evidence availability.

## Public repository warning

Do not commit:

- private PEFY-GG strategy;
- client information;
- personal information;
- credentials or `.env` files;
- unpublished legal drafts;
- sensitive evidence;
- production database dumps;
- proprietary source code not approved for public release.

Use this repository only as an agent-pattern and learning reference. Keep the executable PEA-CORE™ product in a private repository unless public release is explicitly approved.
