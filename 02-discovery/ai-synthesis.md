# AI Synthesis, Product Health & Insights Summary (Module 2)

## Responses
- **Assumption to validate #1:** Showing the total cost upfront increases commitment rather than scaring people off.
- **Assumption to validate #2:** Explaining affordability and missed-payment consequences makes consumers commit to plans they can keep, not just plans that get created.
- **Assumption to validate #3:** Uncertainty and trust, not affordability or process friction, is the main reason consumers drop out or call.
- **Moment of misery / red flag #1 (e.g., “user gave up after 3 tries”):** Stopped process because he did not know what income is meant
- **Moment of misery / red flag #2:** Chose a monthly amount that was too high to be kept
- **Moment of misery / red flag #3:** Has to repeat already provided information
- **Product Health & Insights Summary (Claude's output):** # Product Health & Insights Summary
**BU Collection: Digital Instalment Journey (German Portal)**
*Based on fictional sample data (illustrative, not Riverty research). Figures reflect Month 6 unless stated.*

## Executive Summary

The journey is technically functional and improving on its headline metrics: agreement rate rose from 43.1% to 46.0% and self-service resolution from 31.1% to 34.7% over six months. Those gains are partly illusory, because the same period saw missed payments within 60 days climb from 15.2% to 19.0%, which suggests the journey is closing more agreements without making them more sustainable. The core tension is that the product converts users who the experience does not adequately equip to succeed, and gaps in clarity, structure and agent visibility are pushing that cost onto consumers, agents and clients.

## Thematic Synthesis

### 1. Plan Design & Affordability Fit

The most consequential shift in the data is the Month 4 change to show the 6-month plan first. Agreement rate rose, but missed payments jumped from 15.6% to 18.4% in the same month and kept rising. Consumers describe selecting plans because they "looked right," not because they were affordable, and the affordability check sits after rather than before plan selection. Variable-income and shift-work users are hit hardest, with a 22.5% missed-payment rate against 17.4% for fixed-salary users and a lower agreement rate (41.6%).

- **Plan default raises short-term conversion but coincides with higher default risk** (6-month-first shown at Month 4; missed payments 15.6% → 18.4% → 19.0%). Severity: **Critical**
- **Plan options presented before affordability is established**, so users choose on perceived "correct answer" rather than ability to pay. Severity: **High**
- **Income question is ambiguous for irregular earners** (current month vs. typical month), and variable/shift users show the weakest outcomes. Severity: **High**
- **Payment dates are not aligned to pay day**, which is a plausible contributor to missed payments among shift and variable earners. Severity: **Medium**

### 2. Multi-Claim Handling

Consumers with multiple open claims face a structurally weaker journey. Agreement rate falls from 52.1% (one claim) to 37.7% (two) and 27.6% (three or more), while agent contact rises from 25.6% to 43.0%. The portal treats each claim in isolation, leaving users unsure whether paying one affects correspondence on another. Roughly 2,968 starters (about 35%) carry two or more claims, so this is a large segment rather than an edge case.

- **No ability to create a single plan across multiple claims**, with sharply lower conversion and self-service in this segment. Severity: **Critical**
- **No clarity on how paying one claim affects communication on others**; "can claims be combined" is the second-largest agent contact driver (17.3%). Severity: **High**

### 3. Technical Stability

Technical defects are concentrated in the document and data steps, where users who have already shown intent are lost or given wrong information. The income document step is the clearest friction point: 853 journeys in the sample month requested a document that never arrived, and 28% of uploads that do arrive need manual review. Mobile carries 79% of starters yet converts at 43.8% against 54.0% on desktop, consistent with the upload failures.

- **Income document upload times out on mobile with large photos** (853 journeys affected; 12.8% of agent contacts relate to upload problems; mobile/desktop agreement-rate gap of about 10 points). Severity: **Critical**
- **Portal amount differs from the letter** (531 journeys, 343 of them purchased portfolio); consumers in this situation withhold agreement until someone explains. Severity: **High**
- **Back button on plan review clears affordability answers**, forcing re-entry at a high-anxiety step. Severity: **Medium**
- **First-instalment reminder sometimes sent after the due date**, which may contribute to early missed payments. Severity: **High**

### 4. Trust & Clarity

Users approach the journey with fear of misuse of their financial information and uncertainty about consequences. Nothing in the portal explains why income is requested, how it is used, or how long it is retained, and consumers cannot see what happens after a missed payment. These gaps appear in qualitative interviews and in agent contact reasons: "what if I miss a payment" (18.6%) and "why is income asked" (16.2%) are the first and third most common.

- **No explanation of why income is collected or how long it is retained**; one consumer feared the data would be "used against" them. Severity: **High**
- **Consequences of a missed payment are not shown**, including by the chat assistant, which confirms plans without explaining them. Severity: **High**
- **Chat assistant lifts agreement (53.3% vs. 44.4%) but also correlates with higher missed payments (21.6% vs. 18.3%)**, indicating fast confirmation without informed commitment. Severity: **Medium**
- **Preference for human reassurance** among some consumers on cost implications, which the portal does not currently substitute for. Severity: **Low**

### 5. Support Load & Agent Enablement

Agents work without visibility into what consumers entered online or why a plan was offered, so calls begin with repeated data collection and plan failures cannot be diagnosed. Roughly 31% of starters contact an agent within seven days, and the top five contact reasons (all with handle times of 11 to 13 minutes) map directly onto journey gaps rather than genuine case complexity. This load also reaches clients: a rise in broken plans is visible in their reporting, and they weight complaint levels alongside recovery.

- **Agents cannot see consumer-entered data or plan rationale**, causing duplicate questioning and no root-cause view on failed plans. Severity: **High**
- **About 31% of starters contact an agent within seven days**, with most contact reasons attributable to portal clarity or structure. Severity: **High**
- **Rising broken-plan volume surfaces in client reporting**, creating complaint and commercial exposure. Severity: **Medium**

### 6. Data Quality & Governance

Purchased portfolios carry inconsistent data, including unreliable phone and address history, which complicates both amount reconciliation and contactability. Compliance requires that any plan decision be explainable to both consumer and agent, a standard the current journey does not meet because the offering logic is opaque to agents.

- **Inconsistent data across purchased portfolios** (contact and address history; contributes to amount mismatches). Severity: **Medium**
- **Plan offering logic is not explainable to agents or consumers**, creating compliance exposure. Severity: **High**

### Minor Technical Debt

Dispute or wrong-claim contacts (6.2%), unclassified "other" contacts (7.4%), minor differences in missed-payment rates across entry channels (letter/QR 20.3% vs. email 18.1%), and the unsegmented small cohort with undeclared income pattern.

---
*Caveat: all figures are fictional sample data. Severity ratings reflect volume, segment size, and downstream impact within this dataset; causal links (e.g., plan default and missed payments) are inferred from timing correlation, not controlled testing.*
- **Did the AI catch the specific moment of misery / pain point you found in Step 1?:** Mostly yes, but Trust & Clarity focused on why the income data is used (trust) not which data is meant such as average income vs. last months income (clarity)
- **Did it smooth over a critical frustration into a generic bullet point?:** Yes, there where no quotes which indicated particularly frustrated users or mood insights in general
- **Did the AI try to suggest features or a roadmap despite the constraints?:** No, just severity of the problem
- **Logic leak / hallucination #1 (e.g., “AI suggested a new search bar feature, roadmap leak”):** No
- **Logic leak / hallucination #2:** Just noticed that an issue with rather weak data was overstated in the initial summary and deprioritised when drilling deeper
