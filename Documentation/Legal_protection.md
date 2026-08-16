

## Layer 1: Business Entity — Your Foundational Protection

Right now, if you're operating as a sole individual (no LLC), you have **zero structural liability protection** — your personal assets (savings, car, home) are directly exposed if you're sued, regardless of what your contract with Cam says.  Forming a single-member LLC creates a legal wall: creditors and plaintiffs can generally only pursue the LLC's assets, not your personal ones — this is often called the "corporate veil." [nchinc](https://nchinc.com/entities/limited-liability-company-llc/independent-contractor-vs-llc)

**This matters specifically for you, not equally for your girlfriend**, because:
- You're the one writing security-critical code (RLS policies, auth logic) — the actual highest-risk activity in this project
- She's doing QA/UX and coordination — lower risk, but not zero risk, which is why she still benefits from a lighter version of this protection

**Important caveat**: the veil isn't absolute. Courts can "pierce" it if you commingle personal and business funds, don't maintain a separate business bank account, or use the LLC to commit fraud.  To keep it intact: separate bank account, sign all contracts as your LLC (not your personal name), keep clean records. [unclekam](https://unclekam.com/tax-strategy-blog/independent-contractor-limitation-liability-2026-guide/)

## Layer 2: The Contract Itself — Indemnification and Limitation of Liability

These are two distinct clauses that do different jobs, and you want both, not just one:

**Limitation of liability** caps the *dollar amount* you could ever owe — typically capped at total fees paid under the contract.  This protects you from a scenario where Cam's business tries to recover, say, $500,000 in downstream losses from a project you were only paid $8,000 to build. [pactdraft](https://www.pactdraft.ai/blog/contractor-indemnification-clause)

**Indemnification** determines *who pays whose legal costs* when a third party (a facility, a guard, a parent) sues over something. A well-drafted independent contractor agreement typically includes **mutual indemnification** — you indemnify Cam's business for claims arising from *your* negligence or breach of the agreement, but Cam's business indemnifies you for claims arising from *their* misuse of your work product or their own failures.  One-sided indemnification (where only you carry the risk) is a red flag worth pushing back on. [sec](https://www.sec.gov/Archives/edgar/data/1440280/000107878211003387/f8ka7111811_ex10z3.htm)

**Specific carve-outs to insist on excluding from any liability cap** — meaning these situations should NOT be capped, because they represent genuine bad-faith conduct rather than honest mistakes:
- Gross negligence or willful misconduct [tcoe](https://www.tcoe.org/docs/default-source/human-resources/law-seminars/2023-2024/the-essentials-of-independent-contractor-agreements-handouts.pdf?sfvrsn=cc46672a_3)
- Confidentiality breaches (this connects directly back to your NDA)

**Specific exclusions to insist on adding** — situations where you should NOT be liable, even without a cap:
- Losses caused by Cam's own negligence (e.g., he mishandles credentials you gave him securely)
- Losses from modifications made to your code after delivery, by Cam or someone else
- Losses from Cam's business failing to implement security measures you recommended [pactdraft](https://www.pactdraft.ai/blog/contractor-indemnification-clause)

That last one is worth building into your actual working relationship, not just the contract — if you flag a security risk in writing and Cam's business chooses not to act on it, that written record is exactly what separates your exposure from theirs later.

## Layer 3: GDPR/CCPA-Style Processor Obligations — What Should Be IN Your Contract, Not Just Understood Informally

Since we established you're functionally a data processor, real regulatory frameworks (GDPR Article 28, which many US state laws mirror in spirit) specify exactly what a processor's contract with a controller should contain: [gdpr-info](https://gdpr-info.eu/art-28-gdpr/)

- You process data only on Cam's documented instructions, not on your own initiative
- You maintain confidentiality obligations for anyone with data access (this includes your girlfriend, since she'll have staging environment access)
- You implement "appropriate technical and organizational security measures" — this is your actual legal hook for why RLS, automated testing, and secrets management aren't optional extras, they're the specific standard a processor is expected to meet [ico.org](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/accountability-and-governance/contracts-and-liabilities-between-controllers-and-processors-multi/what-needs-to-be-included-in-the-contract/)
- You assist the controller (Cam's business) in responding to data breach notification obligations, rather than being silent or unreachable if something happens [ico.org](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/accountability-and-governance/contracts-and-liabilities-between-controllers-and-processors-multi/what-needs-to-be-included-in-the-contract/)
- At the end of the engagement, data/access is properly deleted or returned, not left lingering [gdpr-info](https://gdpr-info.eu/art-28-gdpr/)

California's CCPA has a nearly identical concept called "service provider," with the same core requirement: a written contract restricting what you can do with the data, specifically prohibiting you from using it for any purpose outside what the contract specifies.  Getting this into writing now, even informally, gives you a paper trail showing you operated within scope — which is directly protective if anything is ever questioned later. [sidley](https://www.sidley.com/en/sidley-pages/ccpa-text)

## Layer 4: Errors & Omissions (E&O) Insurance — Your Actual Financial Backstop

This is the piece that catches what contracts and LLCs can't fully cover: **the cost of defending yourself**, even in a claim you'd ultimately win. [moneygeek](https://www.moneygeek.com/insurance/business/tech-it/errors-and-omissions/)

Real 2026 pricing for a solo/small software developer:
- **Individual developer, under $100K revenue**: roughly $1,000–$3,000/year [casurance](https://casurance.com/resources/cost-guide/technology-companies)
- **Software development specifically**: averages $74/month ($888/year) for $1M/$2M coverage limits [moneygeek](https://www.moneygeek.com/insurance/business/tech-it/errors-and-omissions/)
- **Combined Tech E&O + Cyber liability bundle**: often cheaper than buying separately, averaging around $83/month ($990/year) [techinsurance](https://www.techinsurance.com/technology-business-insurance/software-development/cost)

Given AquaOps handles certification/liability-adjacent data, this is genuinely worth budgeting for once you have real paid pilot revenue — not because something will go wrong, but because it's the layer that protects you even from a *frivolous* claim, which an LLC and contract alone don't fully cover (they limit your liability; insurance covers your *legal defense costs* getting there).

## What Your Girlfriend Actually Needs — A Much Lighter Version

Her risk profile is genuinely different, so her protections should be proportionate, not identical:

| Protection | You Need | She Needs |
|---|---|---|
| LLC/business entity | Yes — you're the one writing security-critical code | Optional — lower risk activity, but still worth being named/covered under a written agreement rather than operating with zero paper trail |
| Confidentiality obligation | Covered by your existing NDA | Needs her own confidentiality commitment, since she'll have staging access and sees real (or test) certification data |
| Indemnification in her agreement | N/A (this is your contract with Cam) | A simple one-way protection stating she's not liable for security architecture decisions or production outcomes — her role is explicitly QA/UX and coordination, not engineering |
| E&O insurance | Worth it once revenue exists | Not necessary — her exposure doesn't come from professional errors causing financial loss the way a developer's does |
| Written scope boundaries | Your dev contract | Her job description already does this — the "What This Role Does Not Do" section is functionally her liability shield, since it establishes in writing that she has no decision-making authority over security or architecture |

The single most protective thing for her, practically speaking, is exactly what's already in her job description: an explicit, written statement that she does not make technical or security decisions and holds no production credentials. If her role is ever scrutinized after an incident, that document is what shows she operated squarely within a low-risk, clearly-bounded lane.

## The Practical Priority Order

Given your part-time bandwidth and the project's current stage, here's a reasonable sequence rather than trying to do everything before Phase 1 starts:

1. **Now**: Get the indemnification and limitation of liability clauses written into your agreement with Cam — this costs nothing but time and is the single highest-leverage protective step available immediately
2. **Before real pilot data enters the system (~Phase 3-4)**: Form an LLC if you haven't already — inexpensive, and this is the point where real facility data makes the exposure real rather than theoretical
3. **Once AquaOps has paying pilot revenue**: Get E&O/cyber liability insurance — this is the layer that scales with actual financial exposure, so it makes sense to add once there's real money and real data flowing, not necessarily before