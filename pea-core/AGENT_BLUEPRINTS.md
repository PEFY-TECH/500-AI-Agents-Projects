# PEA-CORE™ Agent Blueprint Matrix V0.7

This matrix maps useful agent patterns from the broader AI-agent landscape into PEA-CORE™ without losing control, auditability or founder protection.

## Agent portfolio

| Agent | Mission | Framework fit | Human gate | MVP action |
|---|---|---|---|---|
| Executive Brain Agent | Prioritize, arbitrate, reduce dispersion, recommend Kill/Keep/Scale. | LangGraph later; deterministic scoring now. | Yes | Recommend only. |
| Founder Protection Agent | Detect IP, NDA, MOU, non-circumvention and partnership risks. | LangGraph controlled gate + structured output. | Mandatory | Block/recommend. |
| Cash & Mandate Agent | Prevent heavy work without payment, mandate or strategic value. | Deterministic scoring + n8n follow-up. | Mandatory | Cash-first recommendation. |
| Meeting Preparation Agent | Prepare agendas, objectives, risks and post-meeting registers. | CrewAI Flow or n8n webhook. | No for internal briefs; yes for external send. | Generate internal brief. |
| Document Factory Agent | Draft, review, version and archive documents with evidence links. | CrewAI + LlamaIndex RAG. | Yes | Draft and quality-check. |
| Evidence Intelligence Agent | Classify proof, hash files, detect missing proof, link decisions. | LlamaIndex + PEA-CORE evidence store. | Yes | Classify/link. |
| Existing-First Research Agent | Benchmark before build and recommend adopt/adapt/integrate/build. | CrewAI / AutoGen research crew. | No for research; yes before procurement. | Benchmark report. |
| DevSecOps Code & QA Agent | Generate tests, inspect code, validate migrations, propose PRs. | AutoGen/Agent Framework in sandbox. | Mandatory | Suggest patch and test. |
| Cyber Risk & Compliance Agent | Review RBAC, MFA, audit logs, rate limits, evidence immutability. | Rule engine + LLM-assisted review. | Mandatory | Security review. |
| Workflow Orchestrator Agent | Route requests, enforce human gates, create automation runs. | n8n now; LangGraph later. | Yes | Route and log. |

## Routing logic

| Request type | Recommended agents |
|---|---|
| meeting | Meeting Preparation + Evidence Intelligence |
| email | Executive Brain + Cash & Mandate + Founder Protection |
| legal | Founder Protection + Evidence Intelligence + Document Factory |
| finance | Cash & Mandate + Executive Brain + Evidence Intelligence |
| project | Executive Brain + Workflow Orchestrator + DevSecOps QA |
| document | Document Factory + Evidence Intelligence + Founder Protection |
| research | Existing-First Research + Executive Brain |
| code | DevSecOps QA + Cyber Risk + Workflow Orchestrator |
| automation | Workflow Orchestrator + Cyber Risk + Executive Brain |
| security | Cyber Risk + Founder Protection + Evidence Intelligence |

## Safety boundaries

Agents must never autonomously:

- send sensitive emails;
- approve contracts;
- share confidential files;
- delete evidence;
- create external access;
- validate payments;
- modify legal registers;
- publish strategic documents;
- bypass human gates.

## Core output schema

Every agent result should include:

```json
{
  "classification": "meeting|legal|finance|project|document|research|code|automation|security",
  "recommended_agents": [],
  "risk_level": 0,
  "human_gate_required": true,
  "evidence_required": true,
  "decision_required": false,
  "next_action": "",
  "audit_note": ""
}
```
