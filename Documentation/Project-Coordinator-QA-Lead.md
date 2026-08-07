## Job Description: Project Coordinator & QA/UX Lead

**AquaOps**

**Reports to:** Lead Developer
**Employment type:** Part-time, retainer-based (contractor)
**Compensation:** Monthly retainer, billed separately from development costs; scope and rate adjust by project phase (see Section 5)

### Position Summary

The Project Coordinator & QA/UX Lead supports AquaOps's development by managing project timelines, client communication, quality assurance, and documentation across the product's six development phases. This role keeps the project organized, transparent to stakeholders, and usable by real end users — without writing or reviewing production code or making technical architecture decisions.

The scope of this role changes across the project timeline. Some responsibilities are active from the start of the engagement; others activate only once a testable user interface exists. Section 4 details exactly when each responsibility is active and why.

### Core Responsibilities

| Area | Duties | Tools/Platforms |
|---|---|---|
| Sprint & scope tracking | Break each development phase into weekly sprints; track completed, in-progress, and blocked work; identify and flag scope changes as soon as they appear | Trello (free tier) |
| Client communication & intake | Provide weekly status updates; log all client-raised ideas and requests — including those surfaced through sales or pilot conversations — into a shared intake system; escalate scope questions to the Lead Developer rather than approving them independently | Trello, email, shared "Ideas & Requests" log |
| Quality assurance | Test each feature across all user roles (manager, guard, parent) once a working interface exists, using structured test cases, boundary value analysis (testing at the edges of valid input, not just typical cases), and negative testing (deliberately attempting unauthorized actions to confirm they're correctly blocked) | Staging/pilot environment, Google Sheets test checklists |
| UX review | Identify confusing workflows, unclear labeling, and usability friction using heuristic evaluation (Nielsen's 10 usability heuristics) and cognitive walkthrough (simulating a first-time, untrained user); document each issue with enough context (what, where, why it matters, severity) for the developer to act on it | Staging environment, Trello comments, Loom screen recordings |
| Documentation | Maintain certification workflow documentation, pilot facility onboarding guides, and internal build notes to support future onboarding and knowledge transfer | Google Docs or Notion |

### QA/UX Methodology

This role does not rely on unstructured, ad hoc testing. Two complementary methodologies are used, chosen specifically because AquaOps involves certification and liability data where testing gaps carry real consequences beyond user annoyance.

**Quality Assurance** — Each feature is tested using structured test cases (unique ID, pre-conditions, steps, expected/actual result, pass/fail status), supplemented by two targeted techniques: boundary value analysis, which tests at the edges of valid conditions (e.g., a certification expiring in exactly one day, or with no expiration date entered) rather than only typical cases; and negative testing, which deliberately attempts unauthorized actions (e.g., a guard account trying to directly access a manager-only screen) to confirm the system correctly blocks them. This combination catches the edge cases and role-boundary failures most likely to hide from a simple "click through and see if it looks right" pass.

**UX Review** — Interface quality is assessed using two established usability inspection methods: heuristic evaluation, which checks each workflow against Nielsen's 10 usability heuristics (e.g., visibility of system status, error prevention, user control); and cognitive walkthrough, which simulates how a first-time, untrained user would navigate a task — directly relevant given that AquaOps's actual pilot users are non-technical facility staff, not developers. Findings are documented with a Loom recording, the specific heuristic or principle violated, and a severity rating, so issues are prioritized by real impact rather than treated as equally urgent.

### Communication Standards

This role operates under AquaOps's Communication Framework, which governs how information moves between the client, the developer, and this position. Key standards specific to this role:

- Access is unrestricted. The client may reach this role at any time for status updates, questions, or new ideas. No request is deflected or delayed.
- This role does not approve or deny scope. Any new idea, feature request, or change is logged and flagged for classification, but the decision to accept, defer, or decline it rests solely with the Lead Developer.
- All incoming ideas are logged, including those relayed by the client from prospective or pilot clients during sales conversations, using a standard, non-committal acknowledgment: "That's a great idea — let me log it and we'll take a look at whether it fits current scope or needs its own conversation."
- Every logged item receives a visible status and a follow-up response — under review, planned, not now, or shipped — regardless of outcome. No request goes unacknowledged.
- Internal reporting to the Lead Developer occurs weekly, prior to any client-facing status update, ensuring all external communication is grounded in verified project status.

### What This Role Does Not Do

- Write or review production code
- Make technical architecture, security, or infrastructure decisions
- Approve scope, cost, or timeline changes
- Hold access to production credentials, deployment pipelines, or source code repositories

### Scope by Project Phase

| Phase | Development Focus | Active Responsibilities | Rationale |
|---|---|---|---|
| Phase 1 — Data Foundation & Multi-Tenancy (Wks 1–8) | Database schema, Row Level Security, core authentication | Sprint tracking, client communication, intake logging | This phase produces no visible interface and carries the highest technical risk in the project. Consistent tracking and communication provide the client with continuous visibility and early warning of any delays during the least outwardly visible stretch of the build. |
| Phase 2 — Core Backend & API (Wks 6–13) | Backend hosting, API endpoints, billing integration | Sprint tracking, client communication, intake logging | Still pre-interface; the same visibility and communication rationale applies. |
| Phase 3 — Web Application Port (Wks 10–17) | Interface build, role-based access enforcement | Full scope activates: sprint tracking, communication, QA testing, UX review, documentation begins | This is the first phase where a testable interface exists. QA and UX responsibilities are not possible prior to this point, as there is nothing to evaluate. |
| Phase 4 — Guard App & Parent Portal (Wks 15–20) | Mobile application, parent-facing portal | Full scope; QA/UX workload increases | New interfaces require dedicated role-based testing across additional platforms. |
| Phase 5 — Notifications, File Storage & Payroll Export (Wks 17–22) | Notification systems, file storage, payroll export | Full scope; QA focused on delivery accuracy and edge cases | Verifying that time-sensitive alerts and exports function correctly requires structured, role-based testing. |
| Phase 6 — Testing, Hardening & Pilot Onboarding (Wks 22–26) | Security review, multi-tenancy isolation testing, pilot rollout | Full scope; documentation and coordination responsibilities intensify | Onboarding real pilot facilities requires finalized documentation and active coordination between the client and end users. |

### Compensation Structure

- Phases 1–2: Reduced monthly retainer, covering sprint tracking and client communication only. QA and UX line items are excluded from billing during this period, as they are not yet performable.
- Phases 3–6: Full monthly retainer, covering all responsibilities listed above.
- Billed separately from development costs at all times, so all parties can distinguish development spend from coordination/QA spend.
- Any month in which QA workload materially exceeds the retainer's expected scope (e.g., a concentrated pre-pilot testing period) is flagged in advance for review, rather than billed without prior notice.

### Success Criteria

- Sprint status is accurately tracked and communicated on a weekly basis without gaps.
- No client-raised idea or request goes unlogged or unacknowledged.
- QA testing produces documented, repeatable test cases — incorporating boundary value analysis and negative testing — covering all user roles for each shipped feature.
- UX findings are documented using heuristic evaluation and cognitive walkthrough methods, with severity ratings that allow the developer to prioritize fixes by real impact.
- Documentation is current and sufficient for a new pilot facility to onboard without requiring direct developer involvement.
- Scope changes are identified and flagged before they affect timeline or cost, not after.