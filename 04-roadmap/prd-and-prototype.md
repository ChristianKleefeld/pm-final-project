# Plain explainer for why income is asked and how it is used, Simplified PRD (Riverty BU Collection, A Fair Way Forward)

**Scenario:** Riverty BU Collection, A Fair Way Forward

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** Consumers with multiple open claims and variable income, who cannot pay a claim in one go

## 1. The Big Picture
- **Vision:** Every consumer with several claims and an unpredictable income knows exactly what income number to enter, why Riverty asks for it and what happens to it, so she carries on to a plan instead of closing the page.
- **Press release:** Riverty makes the income question clear, so more people will start a payment plan they can keep
- **Success metric:** Agreement rate (started journeys that end in an agreed plan)
- **Guardrail:** Missed payment rate must not increase versus baseline

## 2. The Details
### User stories
- As a consumer with variable income, I want to know exactly which income number to enter when setting up an instalment plan, so that I can answer without fearing it’s the wrong one.
### Screens to build
- 1. Entry point: “Let’s set up your plan”. A static summary (“You have 3 open claims”, synthetic) and one button, “Continue”. It is context only and does no combined-plan logic (that’s B1).
- 2. Feature core: the income step. This is the only screen under test:
- the reworded question with its helper text;
- the one-sentence “why we ask”;
- the three-line “how it is used”;
- a numeric income field;
- a visible “Not sure what to enter? Contact us” link;
- a Continue button.
- 3. Success/confirmation: “Thanks, we’ve got your figure”. It shows the entered figure back and says the next step is plan options. It makes no promise about affordability, because B3 isn’t live, and it says nothing about being able to change the figure later. It repeats the contact link.
### Functional requirements
- Functional requirements
- #	Rule	Measure
- FR1	The question names one figure: “the amount you can count on in most months, not your best month”.	The phrase is on screen 2 for every user, with no branching on any answer.
- FR2	Helper text, “why we ask” and “how it is used” are visible without any tap or expand.	All three are in the viewport on a 360 px wide screen with at most one scroll.
- FR3	“Why we ask” is one sentence and describes only what the figure does today.	One sentence, 25 words or fewer, with no promise of affordable options.
- FR4	“How it is used” has exactly three lines: who sees it, how long it is kept, link to the full notice.	Three lines. The retention period and the access list are marked “[TBC with data owner]” until confirmed.
- FR5	The field accepts any whole number from 0 upwards and ignores currency symbols, spaces and thousands separators.	“1.400”, “€1400” and “1 400” all read as 1400. Entering 0 is allowed and continues.
- FR6	A contact link is visible on screen 2 and screen 3, and opens a placeholder panel without leaving the flow.	The link shows on both screens with no scrolling past the Continue button, and the entered figure is kept when the panel closes.
- FR7	Every sentence in the explainer is short and plain.	No sentence over 20 words, and no legal or collections jargon (to be checked by a reader outside the team).
- FR8	All wording sits in one config object at the top of the file.	Changing one string in the config changes it everywhere it appears.
### Smart behaviors (Situation → Outcome)
- If the field is empty when the consumer taps Continue, then stay on screen 2 and show “Enter a number to continue”, with the field focused.
- If the entry is not a number (letters, negative, decimals), then show “Use numbers only, for example 1400” and keep the entry.
- If the consumer enters 0, then accept it, continue, and show the contact link more prominently on screen 3 as the support path.
- If the consumer enters a currency symbol, spaces or separators, then strip them silently and read the number.
- If the consumer taps the contact link, then open a placeholder panel and keep the figure in the field.
- If the consumer taps Back from screen 3, then return to screen 2 with the figure still filled in. This is a prototype convenience only, because the real flow may not allow editing.
- If the consumer taps Continue on screen 2 with a valid figure, then log income_step_completed to the console only. No storage, no external call.
- If a different figure is entered, then change nothing in the wording. No copy depends on the value, because there is no affordability logic in B2.
### Technical constraints
- One HTML file with inline CSS and JS. No frameworks and no external requests, fonts or images.
- No APIs, no database and no browser storage. Entered values live in memory and disappear on reload.
- No real consumer data. Claims shown on screen 1 and every test scenario are synthetic.
- No affordability calculation, no plan options and no multi-claim logic (B3, B1).
- No model, AI or chat. All copy is static.
- No “my income varies” selector and no new attribute about the consumer.
- No identity check, login, document upload or income verification.
- No real analytics. Console logging only, as above.
- No unconfirmed facts shown as final. Retention, access list and contact details stay marked “[TBC]” until the data owner and operations confirm them.
- No promise that the figure can be changed later, unless engineering confirms it.
- Mobile-first at 360 px, with labelled inputs and keyboard focus visible. No animation needed.

## 3. The Logistics
### Features out
- Any affordability calculation or plan options (B3).
- Multi-claim plan logic or explanation (B1).
- A chat or conversational explainer (B8).
- Income verification, open banking or document upload (B5).
- A “my income varies” selector or any new attribute about the consumer, because of proxy-discrimination risk.
- Any automated or model-generated decision or copy based on income.
- New data fields, or longer retention of income than today.
- Agent handoff changes (B4).
- Changes to plan ordering or defaults (B7).
- A redesign of the wider journey.
### Edge cases & safety guard
- never invent income numbers or create a payment plan that hasn't been accepted by the user
### Decision log
- Decision 1: one income field with a helper shown to everyone	Decision 2: copy describes only what the flow does today
- Choice	A single field asking for “the amount you can count on in most months”. No “my income varies” selector and no separate low-month and normal-month fields.	“Why we ask” and “how it is used” state only current facts. No promise of affordability-based options until B3 ships.
- Alternatives rejected	Two fields (clearer for variable earners, but needs a rule in B3). An income range (needs matching logic). A branching selector (collects a new attribute about the consumer).	Copy promising “plans you can afford” (appealing, but untrue until B3 is live). Holding B2 until B3 is ready (loses the early lift at the income step).
- Why this protects scope	It adds no new data, no branching and no dependency on B3. It stays a copy-and-UI change of a few days. It also avoids a proxy-discrimination risk.	B2 and B3 can ship independently, and the legal and data-owner review covers only facts that are true on launch day.
- Cost accepted	A variable earner with a very uneven income gets less precise guidance than two fields would give.	The copy is less persuasive than it will be once B3 exists.
- Revisit when	The comprehension test shows variable earners still enter inconsistent figures, or B3 needs a second figure.	B3 ships. Then rewrite M2 to promise affordability-based options.
### Evals
- Decision 1: one income field with a helper shown to everyone	Decision 2: copy describes only what the flow does today
- Choice	A single field asking for “the amount you can count on in most months”. No “my income varies” selector and no separate low-month and normal-month fields.	“Why we ask” and “how it is used” state only current facts. No promise of affordability-based options until B3 ships.
- Alternatives rejected	Two fields (clearer for variable earners, but needs a rule in B3). An income range (needs matching logic). A branching selector (collects a new attribute about the consumer).	Copy promising “plans you can afford” (appealing, but untrue until B3 is live). Holding B2 until B3 is ready (loses the early lift at the income step).
- Why this protects scope	It adds no new data, no branching and no dependency on B3. It stays a copy-and-UI change of a few days. It also avoids a proxy-discrimination risk.	B2 and B3 can ship independently, and the legal and data-owner review covers only facts that are true on launch day.
- Cost accepted	A variable earner with a very uneven income gets less precise guidance than two fields would give.	The copy is less persuasive than it will be once B3 exists.
- Revisit when	The comprehension test shows variable earners still enter inconsistent figures, or B3 needs a second figure.	B3 ships. Then rewrite M2 to promise affordability-based options.

## MoSCoW scope
- **Must:** M1: income question (label and helper, shown to everyone, visible without a tap); How much money do you usually have coming in each month?; Include pay, benefits and other regular money. If it changes from month to month, enter the amount you can count on in most months. Not your best month, not your worst. A rough number is fine.; M2: why we ask (one sentence, kept modest because B3 is not live yet); We ask so your plan is based on what you can realistically pay each month.; M3: how it is used (facts in brackets must come from the data owner, not from me); We use this only for your payment plan. [Who sees it: e.g. our collection team.] We keep it for [retention period]. Details are in our [privacy notice link].; Not sure what to enter? [Contact channel and hours.]; .
- **Should:** Inline placement. The text sits on the same step as the income field, visible without a tap, and is readable on mobile; A worked example for variable income, such as “enter what you can count on in a low month”.; A short expandable FAQ of 3 to 4 questions: what if my income changes, does anyone check this, who sees it.; Three analytics events: explainer viewed or expanded, income step exit, income step completed for data review.; Copy held in a content config, with reusable text blocks and the client or country legal wording (retention period, notice link) as settings. Doing this from day one is cheap and protects scalability.; An accessibility pass: plain-language reading level, screen-reader labels, contrast.
- **Could:** Personalised line using the number of open claims, once B1 exists.; A two-field input (“typical month” and “low month”).; A preview of the affordable range based on the entered income, once B3 exists.; Copy A/B variants.; A short illustration or video.
- **Won't (now):** Any affordability calculation or plan options (B3).; Multi-claim plan logic or explanation (B1).; A chat or conversational explainer (B8).; Income verification, open banking or document upload (B5).; Any automated or model-generated decision, or generated copy, based on income.; New data fields, or longer retention of income than the current flow has.; Agent handoff changes (B4).; Changes to plan ordering or defaults (B7).; A redesign of the wider journey.

