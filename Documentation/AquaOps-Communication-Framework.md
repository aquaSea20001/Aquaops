# AquaOps Communication Framework
### Open Access, Structured Commitment

## 1. Purpose

This framework exists to answer one question consistently: *when does a conversation become a commitment?*

The goal is to keep every relationship in this project — Client↔Developer, Developer↔Coordinator, Coordinator↔Client — genuinely open and low-friction, while ensuring nothing that affects scope, cost, or timeline lives only in someone's memory. Access to people stays unrestricted. Commitments get written down. That is the entire rule; everything below is the mechanics of applying it to three distinct relationships, plus one special case: prospect-facing sales conversations.

---

## 2. The Three Communication Channels

AquaOps has three distinct lines of communication, and each requires its own norms because each carries different risk.

| Channel | Primary Purpose | Risk If Unstructured |
|---|---|---|
| Client ↔ Developer | Technical decisions, architecture questions, business-critical calls | Verbal technical commitments made under time pressure, with no record of why a decision was made |
| Client ↔ Coordinator | Status updates, feature ideas, day-to-day questions | Scope creep — informal requests treated as agreed-upon work |
| Developer ↔ Coordinator | Internal sprint status, QA findings, blockers | Coordinator relaying inaccurate status to the client because internal sync was informal |

A fourth situation — feature requests surfaced through prospective pilot clients during sales conversations — carries a distinct risk profile of its own and is addressed separately in Section 4b, as it involves a third party outside the core team.

---

## 3. Channel 1 — Client ↔ Developer

### What Stays Fully Open

The client may reach the developer directly at any time for technical questions, architectural concerns, or anything requiring specialized expertise (security decisions, stack choices, timeline realities). This is intentional: the developer is the only party who can accurately answer these questions, and routing them through anyone else would slow the process without benefit.

### What Gets Documented

Any conversation that results in a technical decision, timeline shift, or scope change is documented by the developer within 24–48 hours, as a short written summary capturing:

- What was discussed
- What was decided
- What it affects (timeline, cost, or nothing)
- Where it is tracked (linked Trello card, if applicable)

### The Rule in Practice

A quick technical question (e.g., "why was Supabase chosen over Firebase?") is answered directly — this is access, not commitment, and requires no documentation. A request such as "can IoT sensor support be added to Phase 2?" is never answered with an immediate yes; the response is that the timeline impact will be assessed and a written follow-up provided, with the request entered into the intake system described below.

---

## 4. Channel 2 — Client ↔ Coordinator

This channel is the most exposed to scope creep, as it is the highest-frequency, most casual line of contact — which is precisely why it receives the most explicit structure.

### What Stays Fully Open

The client may contact the coordinator at any time — status questions, casual check-ins, feature ideas, or concerns. There is no gatekeeping on access. The coordinator does not deflect or delay any conversation.

### What Gets Documented — The Intake Template

Any time the client raises a new idea, request, or concern beyond a pure status question, it is entered into a shared "Ideas & Requests" log (a Trello list or shared document, using the same tool already used for sprint tracking). The entry is brief and low-friction, completed within minutes of the conversation:

| Field | What It Captures | Who Fills It In |
|---|---|---|
| Request | The client's idea, in their own words | Coordinator, verbatim, no rewriting |
| Problem it solves | The reasoning behind the request | Coordinator, clarified directly if unclear |
| Date raised | Timestamp | Coordinator |
| Initial classification | In scope / future phase / new scope | Developer only — never the coordinator, who flags rather than decides |
| Status | Under review / planned / not now / shipped | Updated by the developer as it progresses |

### The Coordinator's Standard Response

The coordinator does not approve or deny scope. Her standard response to any new idea is a warm, non-committal acknowledgment: *"That's a great idea — let me log it and we'll take a look at whether it fits current scope or needs its own conversation."* This keeps the interaction collaborative and affirming while ensuring nothing is verbally agreed to on the spot.

### Closing the Loop

Every logged item receives a visible status update, even when the outcome is "not right now." Unacknowledged requests are the single greatest risk to trust in this system; a visible, evolving log where the client can track the status of their own ideas — or receive a clear explanation when something is declined — is what makes the process feel collaborative rather than bureaucratic.

---

## 4b. Channel 2b — Prospect-Sourced Requests (Sales Conversations)

This is a distinct, higher-stakes variant of Channel 2 and warrants its own explicit protocol rather than being combined with client-originated ideas.

### Why This Is Different

When the client is conducting pilot intake or a sales conversation with a prospective facility, a third party is present, and the client operates under different pressures than in a casual conversation with the coordinator. This is precisely the scenario in which products and services are unintentionally overpromised — not through dishonesty, but because a person wants to appear capable and responsive to someone they are trying to close, making it easy to imply "we can build that" without fully weighing the cost. The nature of the request also differs: it is not the client's personal idea but a market-demand signal being relayed through the client, which carries value but must be tracked as its own category.

### The Sales-Specific Intake Template

Anything surfaced during a prospect or pilot conversation is entered into the same Ideas & Requests log, with two additional fields beyond the standard Channel 2 template:

| Field | What It Captures | Who Fills It In |
|---|---|---|
| Request | The feature or ask, in the prospect's words where possible | Coordinator, relayed from the client |
| Requested by | Prospect name/facility, not simply "the client" | Coordinator |
| What was said in the room | The exact wording of anything implied — "we can look into that" versus "yes, absolutely" | Coordinator, clarified directly with the client |
| Problem it solves | The underlying need driving the request | Coordinator |
| Classification | In scope / future phase / new scope | Developer only |
| Status | Under review / planned / not now / shipped | Updated by the developer |

The "what was said in the room" field is the critical addition: it indicates immediately whether an implied promise already exists with a real prospect requiring prompt attention, versus a neutral idea with no attached expectation.

### The Pre-Agreed Sales Script

This element is what actually prevents the underlying problem, and it must be established in advance rather than addressed after the fact. The client is provided a simple, safe response for use whenever a prospect requests something not already built:

> *"That's a great question — let me note that and get you a real answer on timeline rather than guess in the moment."*

This response allows the client to appear competent and responsive rather than evasive, while ensuring nothing is verbally promised to a prospect without prior review. The primary risk in this channel is not the relaying of ideas — it is the client inadvertently committing AquaOps to something in front of a client who then holds an expectation nobody has approved.

### Escalation Priority

Any entry where the client has already said something implying a promise is flagged urgent for developer review, since a live expectation now exists with a real prospect rather than an internal idea sitting in a backlog. All other entries in this channel follow the normal weekly review cadence.

---

## 5. Channel 3 — Developer ↔ Coordinator

This internal channel is what makes the other two function correctly. If developer-coordinator sync is informal, everything the coordinator communicates to the client is only as accurate as the most recent informal conversation.

### Structure

- A weekly check-in (15–20 minutes) in which the developer and coordinator review the current sprint board together before any client-facing reporting occurs.
- Any blocker, delay, or risk is flagged to the coordinator in writing (a Trello comment, a written message) rather than assumed to be understood — the coordinator cannot translate information she has not received.
- QA findings and UX notes flow from the coordinator to the developer through the same tracked system, rather than being communicated verbally and left undocumented.

### Why This Matters

This channel is invisible to the client, but it determines whether the broader "open and structured" system is genuine or merely nominal. If information is communicated verbally and never enters the tracked system, the framework breaks down silently — the coordinator either relays inaccurate status to the client or has nothing accurate to report.

---

## 6. Cadence Summary

| Interaction | Frequency | Format |
|---|---|---|
| Developer ↔ Coordinator sync | Weekly | Live check-in, reviewing shared board |
| Coordinator ↔ Client status update | Weekly | Written summary plus optional short call |
| Ideas & Requests review (Developer and Coordinator, then relayed to client) | Weekly or biweekly | Ten minutes reviewing new entries in the log |
| Prospect-sourced request review | As entries arrive; urgent items reviewed immediately | Flagged in the shared log, reviewed within the same week |
| Client ↔ Developer direct technical conversations | As needed, unrestricted | Any channel preferred, summarized in writing afterward if a decision results |

---

## 7. Core Policy Statement (For the Proposal/Contract)

> All parties may communicate freely and directly at any time. However, any discussion that proposes a new feature, changes scope, affects timeline, or affects cost is not considered agreed-upon until it has been logged in the shared Ideas & Requests system and classified by the developer. This applies equally to ideas raised internally and to requests surfaced through prospective client or pilot facility conversations. Verbal or informal agreement in conversation — including agreements implied during sales or pilot discussions — does not constitute a scope change. Every logged request will receive a status and a follow-up response; no request will go unacknowledged.

This statement is intended for direct inclusion in the governing agreement. It provides contractual protection, remains concise enough to avoid feeling bureaucratic, explicitly addresses the sales/prospect scenario to eliminate ambiguity, and establishes a clear, mutual standard — the commitment to close the loop applies to all parties equally.

---

## 8. Why This Builds Culture, Not Bureaucracy

The distinction underlying this framework is the same one disciplined product teams rely on: writing is not a barrier to openness, but what makes openness safe. The client may raise anything, at any time — including mid-conversation with a prospect — without fear of being deflected or told to "submit a ticket," and the developer may hear anything, at any time, without fear of it silently becoming an unpaid commitment or an unmanaged promise to an unknown third party. The documentation is what allows every party to remain relaxed in conversation, since no one relies on memory or assumption to determine what was actually agreed upon.
