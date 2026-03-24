# The 4Ds: A Guide to AI-Facilitated Consensus

*A practical guide to running deliberative assemblies using AI-facilitated asynchronous consensus.*

## Contents

- [How the foundation makes decisions](#how-the-foundation-makes-decisions)
- [Why we needed to move faster](#why-we-needed-to-move-faster)
- [What is an assembly](#what-is-an-assembly)
- [The 4Ds at a glance](#the-4ds-at-a-glance)
- [Phase 1: DESIGN](#phase-1-design)
- [Phase 2: DISCOVER](#phase-2-discover)
- [Phase 3: DELIBERATE](#phase-3-deliberate)
- [Phase 4: DECIDE](#phase-4-decide)
- [Cheat sheet](#cheat-sheet)
- [Practical guidance and tooling](#practical-guidance-and-tooling)
- [Appendix: Prompts](#appendix-prompts)

---

## How the foundation makes decisions

The Green Software Foundation is a consortium of 70+ member organisations developing standards, tooling, and best practices for software with zero harmful environmental effects. Standards are different to open source in one critical way: in open source, if there's a disagreement, you fork the project, implement your changes, and let adoption decide the winner. That's fine. But in standards, a fork is a disaster. If a portion of the group disagrees and creates their own version, you don't have two standards. You have zero standards. The entire value of a standard is that everyone agrees to use it.

So the foundation's consensus process is designed to get genuine agreement, not just majority approval. Here's roughly how it works.

We work on documents. We decide what document needs to be created and what sections it should contain. Section by section, we have conversations (typically in meetings), and once we believe through the deliberation process that we're ready to commit something concrete, someone creates a pull request.

Every decision is essentially: do we accept this change or not?

That pull request goes through a consensus process. It's given time for feedback, adjustments happen as we go, and once we reach the right stage, participants vote using three terms:

**Endorse** means you publicly support the change. You're putting your name behind it.

**Consent** means you're not going to block it, but you're not actively endorsing it either. There are plenty of good reasons to consent rather than endorse. Maybe you feel strongly about other issues and want to focus your energy there. Maybe you understand that the process is collaborative and if you objected to everything, everybody might object to your changes. Maybe you just don't want to be on record endorsing this particular thing. Consent is a valid and important signal.

**Object** is a powerful word and it's used deliberately. An objection means you don't want the change to go forward. And in the foundation, even a single objection stops the pull request from being merged.

But objecting comes with responsibility. You need to explain what would need to change for your objection to be removed. If you object and then don't participate in the conversation about how to move forward, that's not good practice, and your objection is unlikely to stand. The group works hard to resolve objections. The objector provides the conditions for resolution, and if the group agrees, the change is made and consensus is attempted again.

If an objection genuinely can't be resolved after multiple attempts, the group can move to a vote. But it's not a simple majority. It requires a supermajority (66%) to override an objection, and that bar is there to ensure this isn't a minor point being steamrolled. These decisions are made carefully and judiciously by the chair of the standards project.

The chair's role is worth explaining. A chair nurtures the consensus process. In an ideal situation, a chair won't even express their own opinion unless it serves as a tiebreaker. Their purpose is to facilitate the decision-making, work through objections, and ultimately decide when (and whether) to move to a vote.

This process works. We've been running it for years. But it takes a long time, which is the nature of standards. Thorough deliberation is slow.

---

## Why we needed to move faster

In early 2025, we realised something had changed. AI was moving so fast that our standards development process couldn't keep pace. If we spent three years developing a standard (which is normal), it would already be out of date by the time it was published.

We started exploring using AI to help with the facilitation process itself. This is actually a well-researched field of study. It sits within social choice theory, and more specifically within what's now called generative social choice theory, which looks at how AI can assist in aggregating preferences and finding consensus positions across groups.

We combined AI facilitation with a new format we call **assemblies**, and the result was a significant evolution in how standards can be developed. The 4Ds process is the result of a year of running these AI-facilitated assemblies.

This guide documents the current best knowledge we have about the process. It's written to be technology-agnostic. It's not locked into any particular AI model or platform. We have our own tooling and may release it in the future, but the most important thing right now is to release the process itself so that anyone who wants to mirror it can do so.

We're still in the early days. Some of what's in here will very likely change as we run more assemblies and learn more. But this is the current best-efforts guide, and we're sharing it so others can build on it.

---

## What is an assembly

An assembly is the container in which the 4Ds process runs. It's different to the typical standards conversation, which is given plenty of room to breathe and meander over months or years. An assembly is **time-boxed**. We bring experts around the table, ask for a limited number of weeks of their time, and commit to delivering a concrete output at the end. They're designed to move fast.

The output of an assembly is a document. The 4Ds is the process that gets the group to agree on that document.

### Asynchronous and email-based

Assemblies run asynchronously. This is a bigger deal than it might sound. Standards have traditionally been created through meetings, and that mechanism hasn't evolved much. Meetings are hard to schedule across time zones. It's nearly impossible to get everyone in the same room (or the same call), and splitting into separate sessions means people don't hear each other's arguments. Async-first solves this. Everyone contributes on their own schedule, and the AI synthesises everything together.

We recommend email as the medium. We work with a lot of organisations, many of which block external tools like GitHub. Banking and financial institutions in particular have deep requirements around conformance, tracking, and retaining records of all communications (often for seven years). Email is the one technology that every organisation has access to and every employee has permission to use. Questions go out, answers come back, responses are fed into an AI, and synthesis reports are distributed. It's as simple as replying to an email.

### AI facilitation

AI processes participant responses, surfaces areas of agreement and disagreement, and proposes candidate consensus statements. But (and this is important) the decision-making is still entirely human. AI is there to handle the volume of text and streamline the process of identifying what needs to be discussed and what everyone seems to agree on. It doesn't decide anything. The facilitator reviews all AI outputs before they go to participants.

### Roles

**Facilitator** (required). Runs the process. Designs the assembly, crafts questions, manages the AI synthesis, decides when to progress between phases and rounds, and is responsible for the overall integrity of the assembly. The facilitator does not need to be a domain expert — they need to be an expert on the assembly process itself. In an ideal situation (similar to the chair role in the foundation's standards process), the facilitator focuses on nurturing the consensus process rather than advocating for a particular outcome.

**Lead** (one or more, recommended). The person who wants the assembly to happen. They're subject matter experts with a real stake in the outcome. They co-design the assembly with the facilitator, review synthesis outputs, and take ownership of the deliverable after the assembly concludes. Separating the lead from the facilitator is important because it means the facilitator can focus on process while the lead focuses on substance. It also grows someone who can carry the work forward once the assembly is complete.

**Participants** (minimum 3, ideal up to 20). Respond to prompts, review candidates, rate them, and vote. They need domain knowledge relevant to the topic but no process expertise. They don't need to install anything or learn any tools. They just reply to emails.

**AI synthesis agent** (required). Analyses participant responses, generates synthesis reports, creates candidate text, and calculates consensus metrics. Any large language model with a sufficient context window (32k+ tokens recommended) can fill this role. The AI doesn't make decisions. It processes text and surfaces patterns. The facilitator reviews everything before distribution.

### Timing and quorum

Each round within each phase is allocated a fixed time window (we typically use one week per round). When the window closes, one of two things happens:

- **Quorum was reached.** The minimum number of participants have responded (even if not everyone has). The round closes and synthesis begins. The assembly moves forward.
- **Quorum was not reached.** The deadline extends automatically by a few days. If quorum still isn't met, the facilitator makes a judgment call.

Quorum is set by the facilitator in the assembly document and depends on the context. For smaller, curated assemblies where participants have been invited and spaces are limited, quorum should be higher (participants are expected to engage). For larger public assemblies where many people may have signed up but not all will engage on every round, quorum can be lower. If the assembly has a tight deadline and can't risk delays, set quorum lower. If broad participation matters more than speed, set it higher.

Good defaults are 33% or 66% of participants for Discover and Deliberate. The Green Software Foundation's rules require a minimum of three participating organisations, but your assembly may need different thresholds. Decide quorum is typically set higher (up to 100%) since the final vote carries more weight.

This means participants need to understand that the process will move forward with or without them. If you don't respond by the deadline and quorum is met, your input won't be included in that round's synthesis. You can still participate in future rounds, but you've missed your window for this one.

### Participation and the right to object

In the foundation's standards process, there is a rule: you can only object if you've participated in at least two of the last four meetings. This prevents people from disengaging and then blocking progress at the last minute.

To mirror this in an asynchronous workflow focused on speed of delivery: **if you don't participate in the Discover phase for a section, you cannot participate in any subsequent phase for that section.** You must engage in Discover to engage in Deliberate. You must engage in Deliberate to engage in Decide. If you miss a phase, you've lost your right to engage in that section's remaining phases. You can re-engage when the group moves to the next section.

This rule exists because the 4Ds is a forward-only process. Sections are not revisited. If someone who hasn't engaged in the exploration and deliberation shows up at the last minute to object, they're blocking a decision they didn't participate in forming. That's not fair to the participants who invested time in every round.

Participants always have the right to object in principle, but if they haven't participated in the prior phases, their objection is not counted in the fallback vote should one be needed. Make this rule clear during the kickoff call.

### Forward only

Once a section achieves consensus in Decide, it's done. The group moves to the next section. There is no mechanism to reopen a settled section.

This is a deliberate constraint, not an oversight. Assemblies are time-boxed, and allowing the group to revisit previous decisions would make it nearly impossible to finish on schedule. It would also undermine the commitment that participants make when they endorse or consent. Their vote means something precisely because it's final.

The forward-only rule also changes how people participate. When participants know they can't revisit a decision later, they engage more seriously in each round. They raise concerns during Deliberate rather than saving them. They object in Decide rather than consenting and hoping to fix it later.

This is one of the features that makes assemblies fundamentally different from an open-ended standards process (where discussions can and do circle back for months). It trades some flexibility for pace and commitment.

---

## The 4Ds at a glance

The 4Ds is the process that runs inside an assembly. It has four phases. Before getting into the details, here's the terminology used throughout this guide:

- A **section** is a part of the target document. The assembly works through one section at a time.
- A **phase** is one of the three stages each section passes through: Discover, Deliberate, Decide.
- A **round** is a single cycle within a phase (questions go out, responses come back, synthesis happens). Each phase can have multiple rounds.

**DESIGN** happens once, at the start. The facilitator and leads create the **assembly document** (a template of the target document with frontmatter defining the rules, constraints, and section definitions). This is the most important phase. Everything that follows depends on it.

**DISCOVER → DELIBERATE → DECIDE** then runs for each section of the document, in sequence. Within each phase, there can be multiple rounds. And once a section achieves consensus in Decide, the group moves on to the next section.

```text
DESIGN (once)
│  Create the assembly document
│
├─ Section 1
│   ├─ DISCOVER (1+ rounds, private)
│   │   Participants explore the topic individually,
│   │   forming their own thinking through guided questions.
│   │
│   ├─ DELIBERATE (1+ rounds, public)
│   │   Participants debate candidate preferences as a group,
│   │   rating, challenging, and refining them together.
│   │
│   └─ DECIDE (1-3 rounds)
│       Participants vote Endorse / Consent / Object on a
│       single proposed preference. Objections are resolved.
│
├─ Section 2 (same process)
├─ Section 3 ...
│
└─ All sections complete → Assembly report
```

What each phase does:

**DESIGN** → Structure the assembly. Define the target document, its sections, constraints, and rules (quorum, timelines, thresholds). The output is the assembly document. This happens before participants engage.

**DISCOVER** → Participants don't walk into a topic with fully formed opinions. In traditional standards work, much of the time people spend in those long, meandering conversations is actually spent discovering what they themselves think. Discover makes this explicit. Through a series of questions (generated by the AI from the section definition), participants explore the topic space and find the edges of their own thinking. There can be multiple rounds if there are more areas to explore. Each round's synthesis builds cumulatively, and the AI generates emerging candidate preferences (three positions representing different directions the group might take). These develop through each round and become the starting candidates for Deliberate.

**DELIBERATE** → This is where things become public. Up until now, participants have been responding privately. In Deliberate, everyone sees everyone else's positions for the first time. It's a public debate. The three candidate preferences from Discover are presented to the group and every participant must engage with all of them, rating each one and explaining what they like, what they don't like, and how they'd want it changed. This isn't voting or selection. It's deliberation. One of the biggest indicators that it's working is watching minds change. The rounds continue, with the AI refining candidates based on feedback, until there's confidence that a single candidate preference could be proposed that everyone would endorse or consent to.

**DECIDE** → The conversation narrows. A single candidate preference (the **proposed preference** from the final Deliberate round) is put to a vote. Participants respond with Endorse / Consent / Object. If there are objections, the objector must explain what needs to change. There is discussion around the objection, and the AI generates a revised candidate that attempts to resolve it. That revised candidate goes through another Decide round (you stay in Decide, you don't go back to Deliberate). If objections persist after multiple rounds, the facilitator uses the accumulated Endorse / Consent / Object data across all Decide rounds to select the preference with the broadest acceptance.

---

## Phase 1: DESIGN

### Purpose

Structure the assembly before anyone participates. Of the four phases, this one has the highest leverage. A well-designed assembly converges quickly. A poorly designed one produces unfocused deliberation and unclear outcomes.

### What happens

The facilitator and lead create an **assembly document**. This is a single document (typically markdown) that contains everything needed to run the process. Creating it *is* the design process.

The assembly document defines several things, but the most important by far is the **document outline**.

### The document outline

Here's the key insight we learned the hard way: it is very, very difficult to get 20 people to agree on a document if you start with a blank sheet of paper. Even with AI facilitation.

The facilitator and lead need to define the structure of the target document before the assembly begins. That means deciding on the sections, their sequence, and for each section, providing enough scaffolding that participants know what they're aiming for without dictating the answer.

For each section, we recommend defining:

- **Purpose.** What is this section for? What question does it answer?
- **What this section contains.** Bullet points describing the kind of content expected.
- **What this section does NOT contain.** Equally important. This prevents scope creep and keeps sections focused.
- **Constraints.** Non-negotiable requirements (prior decisions, policy boundaries, technical requirements) that the consensus must satisfy.
- **Why this matters.** Context for participants on why this section exists.
- **Connection to other sections.** How this section relates to what comes before and after. This helps participants understand the dependencies.
- **Word count target.** A target range for the final consensus text (e.g. 150-200 words). This forces prioritisation and prevents the AI from generating sprawling consensus statements that try to include everything. See "Why section size matters" below.

If there's prior art (an existing document that's similar to what you're trying to create), use it as a source. It gives participants a concrete reference point rather than an abstraction.

### Why section size matters

Keep each section short. No more than a couple of paragraphs of eventual consensus text.

This is a deliberate design choice, not a formatting preference. When sections are large, something counterproductive happens: rather than genuinely deliberating about what's important enough to include, participants just put everything they want in. There's enough space, so the AI synthesises everyone's contributions into a document that's a mishmash of everyone's opinions rather than a genuinely agreed position. Nobody had to make trade-offs, so nobody really deliberated.

Restricting section size forces participants to prioritise. It forces them to disagree about what matters most. It forces the kind of real deliberation that produces a document people actually stand behind.

### Sequencing sections

The order of sections matters and should be deliberate. There's a pedagogy here. Often, you can't meaningfully discuss section 3 until the group has reached consensus on section 2 because later sections build on earlier decisions.

For example, in an assembly we ran to define the SCI for Web specification, the sections were sequenced as:

1. **Scope Definition** (what counts as a "web application"?)
2. **Target Personas** (who will use this specification?)
3. **Behavioural Incentives** (what behaviours should the specification encourage and discourage?)
4. **Evaluation Criteria** (what makes this specification credible and worth implementing?)
5. **Comparative Analysis** (how does this compare to existing approaches?)

Each section depended on the ones before it. You can't define who uses the spec until you've defined what it covers. You can't design incentives until you know who you're incentivising. You can't evaluate the spec until you've agreed on what good looks like. Getting this sequence right is part of the design work.

### Questions

Initial questions for each section are generated during the Discover phase, not during Design. The [Discover prompt](prompts/01-discover.md) generates questions from the section definition when run without participant responses. This is better than pre-designing all questions at the start because later sections benefit from the context of earlier decisions.

That said, the facilitator should think about the kinds of questions that will surface useful material. Here's what we know:

- **Work backwards from the section definition.** If you know what the section should contain, you can derive the questions that will elicit that information.
- **Mix question types.** Scene-setting ("what's your current role related to this topic?"), exploration ("what are the main challenges in this area?"), opinion-gathering ("what principles should guide this?"), and boundary-testing ("what should NOT be included?").
- **Aim for 3 to 7 questions per round.** Fewer feels thin. More causes fatigue.
- **Be flexible with follow-up rounds.** The AI will suggest follow-up questions based on each round's synthesis. The facilitator can use them as-is, modify them, or write their own. Follow-up questions should go deeper, explore disagreements, or cover new dimensions (**never repeat a question participants have already answered**). This is genuinely frustrating for participants. The AI already has their earlier answers and will incorporate them into future synthesis.

### Other design decisions

Beyond the document outline, the assembly document also captures:

- **Quorum requirements.** What percentage of participants must respond for a round to be valid?
- **Timelines.** How long does each round stay open?
- **Maximum rounds.** How many Discover and Deliberate rounds before you accept that consensus might not be reachable on this section?

### What comes out

A complete assembly document that the facilitator, lead, and AI can use to run every subsequent phase. Think of it as the constitution for the assembly.

### Template: assembly document

Below is a template you can use as a starting point. Adapt it to your context.

```markdown
---
title: "[Assembly Topic]"
facilitator: "[name and email]"
lead: "[name and email]"
participants: "[list or path to participants list]"
status: design | discover | deliberate | decide | complete

# Rules
discover_quorum: "66%"
deliberate_quorum: "66%"
decide_quorum: "100%"
round_duration: "1 week"
max_discover_rounds: [number]
max_deliberate_rounds: [number]
max_decide_rounds: 3
---

## Deliverable

What artifact will this assembly produce? Be specific about format
and where it will live.

**Example:** "A 'Target Personas' section for the SCI-Web specification
report, identifying professional roles, their decision-making power,
and how they'll use the specification."

## Constraints

Non-negotiable requirements the deliverable must satisfy.

- **[Constraint name]** ([technical | policy | prior_decision | scope]):
  [Description]. Source: [reference document or authority].

## Section Sequence

1. **[Section name]** — depends on: [none | previous sections]
   - **Purpose:** [what this section is for]
   - **Contains:** [bullet points of expected content]
   - **Does NOT contain:** [what to exclude]
   - **Constraints:** [section-specific constraints]
   - **Why this matters:** [context for participants]
   - **Connection to other sections:** [dependencies]
   - **Word count target:** [target range, e.g. 150-200 words]

2. **[Section name]** — depends on: [Section 1]
   [same structure as above]
```

See [examples/assembly-document.md](examples/assembly-document.md) for a complete example assembly document.

### Generating initial questions

You don't need to design all questions upfront. Run the [Discover prompt](prompts/01-discover.md) with the assembly document but no participant responses, and it will generate initial questions for the current section. This is better than designing questions at the start of the assembly because by the time you reach a later section, earlier sections will have been filled in with consensus text, and the questions can account for those decisions.

### The facilitator's mindset

Think of yourself less as a chairperson running a vote and more as a teacher using the Socratic method. You're carefully planning a sequence of questions to bring understanding to a group of people. The questions aren't just collecting opinions. They're helping participants *form* their opinions through structured reflection.

---

## Phase 2: DISCOVER

### Purpose

Participants don't walk into a topic with fully formed opinions. In traditional standards work, much of the time people spend in those long, meandering conversations is actually spent discovering what they themselves think. Discover makes this explicit. Through a series of carefully designed questions, participants explore the topic space and find the edges of their own thinking, their positions, their preferences, and where they're uncertain.

### What happens

1. The facilitator sends the Discover questions for this section to all participants by email
2. Participants respond individually. No peer interaction at this stage.
3. Once the deadline passes (or quorum is reached, whichever comes first), the facilitator runs the AI synthesis prompt
4. The facilitator reviews the synthesis and decides: has the topic been explored enough, or should we run another round with follow-up questions?
5. Repeat until the facilitator is satisfied the area has been sufficiently explored
6. Send the latest synthesis to participants (see below for what gets shared and what doesn't)

There can be multiple rounds of Discover for a single section. If the synthesis indicates areas that haven't been explored, or disagreements that haven't been examined in depth, the facilitator designs follow-up questions (with AI assistance or manually) and runs another round.

One of the most valuable aspects of this process is surfacing areas of strong agreement early. In a traditional standards process, it can take significant time just to establish what everyone already agrees on. Here, if the synthesis shows clear agreement on a topic, you don't need to spend further time on it. The only things you really need to dig into are the areas of disagreement and uncertainty. This alone saves substantial time.

### What gets shared with participants

The full AI synthesis is primarily a tool for the facilitator. It helps design follow-up questions and assess whether the topic has been sufficiently explored. Not everything in it should go to participants.

What to share: areas of strong agreement, areas of disagreement, areas of uncertainty, and individual viewpoint summaries (anonymised).

What NOT to share: candidate preferences (those come later in Deliberate) and the readiness assessment (that's for the facilitator's eyes only).

> [!TIP]
> **Speech-to-text.** Encourage participants to use speech-to-text and respond informally, talking rather than writing. We found qualitatively better results because the AI infers more from unedited, natural responses than from polished written text. When people talk, they reveal more of what they actually think.

### The Discover synthesis prompt

After collecting responses, run the [Discover prompt](prompts/01-discover.md) with the assembly document and all cumulative participant responses for this section. The same prompt is used every round (each run includes all previous rounds' responses so that the synthesis builds cumulatively).

The prompt produces a synthesis report that includes: areas of agreement, disagreement, and uncertainty; anonymised viewpoint summaries; emerging candidate preferences (three positions representing different directions the group might take; see Deliberate for how these are used); suggested follow-up questions; and a readiness assessment.

The emerging candidate preferences develop through each round. In early rounds they are rough signals. By the final round they should be well-developed positions ready to serve as the starting candidates for Deliberate.

If the readiness assessment returns BORDERLINE or NOT READY, the prompt will suggest follow-up questions targeting underexplored areas. The facilitator can use these as-is, modify them, or write their own.

> [!NOTE]
> This prompt is still evolving. We're actively refining it based on what we learn from running assemblies. If you find it doesn't produce useful results in your context, adapt it.

### When to move on

At the current stage, the decision to progress from Discover to Deliberate is a **qualitative judgment by the facilitator**, informed by the AI's readiness assessment. There is no hard metric that triggers the transition. The facilitator reads the synthesis, considers whether the main areas of agreement and disagreement have been sufficiently mapped, and makes the call.

The readiness assessment from the AI helps, but it's advisory. The facilitator knows the domain, the participants, and the timeline constraints in ways the AI doesn't.

### Experimental metrics

As we evolve this process, we're exploring quantitative methods that might help the facilitator assess where things stand during Discover. These are experimental. We don't yet have enough real-world data to know which of these are genuinely useful, and some may turn out not to be. We're sharing them here so others can experiment alongside us.

**Diameter.** Each participant's responses can be converted into semantic embeddings (a mathematical representation of meaning). The diameter is the maximum distance between any two participants in this space. The thesis is that if diameter shrinks across rounds, the conversation is converging. However, there's an open question about whether this metric works as intended: as you ask participants more questions across rounds, they produce more text, which creates more semantic content. It's unclear whether the diameter is measuring convergence of opinion or simply expansion of the topic. We plan to research this more.

**Cluster count.** Clustering of semantic positions tells you whether factions are forming in the group. This is potentially useful, but only if you're embedding the aggregate of all a participant's responses (not just their latest response, which might be short or contextless). The number of clusters and whether that's "good" or "bad" depends entirely on the topic and the stage of discussion. We don't yet have confident thresholds for what these numbers mean.

**Response depth.** Simpler indicators like average word count and tokens per person can tell you how deeply participants are engaging. You want rich, detailed responses in Discover. Short, perfunctory answers suggest either bad questions or participant fatigue.

These are KPIs to monitor, not decision triggers. The transition decision remains qualitative.

---

## Phase 3: DELIBERATE

### Purpose

Deliberation is about changing minds. That's what distinguishes it from everything that came before.

In Discover, participants were exploring privately, forming their own thinking. Deliberate is where things go public. Everyone sees everyone else's positions for the first time. It's a conversation, and the goal of that conversation is for people to take each other on a journey towards a shared preference.

This isn't about throwing a few options out there and picking the one most people prefer. It's about adjusting preferences over time, over multiple iterations, learning what people care about and what they don't, so that eventually the group can consolidate into a single preference that everyone can endorse or consent to.

### What happens

**1. Candidate preferences from Discover are sent out.** The final Discover synthesis includes three candidate preferences that emerged from the exploration. These represent different directions the group might take:

- **The consensus preference** is designed to be the version that the least satisfied person can still live with. It sits at the geometric median of the group's positions, the floor-raiser.
- **The popular preference** optimises for the highest average satisfaction. It's what most people would prefer, though it might leave some behind.
- **The anti-consensus preference** deliberately amplifies under-represented viewpoints and challenges the emerging agreement. It's meant to be provocative.

The anti-consensus preference deserves extra attention because it's the most counterintuitive choice. Why deliberately introduce something designed to *challenge* consensus? Because it forces participants to articulate what they reject, not just what they accept. In our experience, this is the single best mechanism for stimulating genuine deliberation in an async process. People who might write "looks good" about the consensus preference will write paragraphs explaining why the anti-consensus preference is wrong. And in doing so, they reveal what they actually care about.

> [!IMPORTANT]
> These initial candidate preferences don't have to mirror the exact language that will end up in the final document. Especially if the section involves precise or technical wording, it can be more productive to start with shorter preferences that capture the overall sentiment and direction. As the rounds progress, the preferences should get closer to the final language. But the early rounds are about direction, not wordsmithing.

**2. Preferences are sent to participants.** The facilitator sends each candidate preference out to all participants, typically as a separate email thread per preference. This means participants can see each other's responses and respond to each other. This is critical. The whole point is to create a space for conversation, not just individual feedback.

**3. Participants engage with ALL preferences.** This is non-negotiable. You can't just comment on the one you like. Every participant must rate (0-10) and comment on each and every candidate preference. Understanding someone's reasoning *against* something is just as important as understanding their reasoning *for* something. This is how you find the edges and boundaries of what the group can accept.

> [!TIP]
> **Rating calibration.** Ratings are subjective. One person's 5 might be another person's 7. To make ratings more comparable, it helps to synchronise expectations upfront. We recommend framing the scale as: 0 means you fundamentally object, 5 means you'd probably accept it (it would likely get through a Decide vote), and 10 means you fully endorse it. This maps roughly to the Endorse / Consent / Object spectrum used in the final Decide phase.

**4. Participants respond to each other.** Rating and commenting on the preferences is the floor, not the ceiling. What makes deliberation actually work is when participants engage with *each other's* commentary. In a face-to-face meeting, you wouldn't present text on a screen and have each person give their opinion in isolation. There would be an actual conversation. People would respond to each other, challenge each other, build on each other's ideas.

That's what we're trying to replicate here. The AI has helped us capture a few options to discuss, but the discussion itself is still very much the responsibility of the participants. The more they engage with each other's positions, the better the deliberation.

**5. The facilitator encourages deliberation.** The facilitator should never express an opinion on the substance. Their role is to encourage more conversation. This might mean:

- Asking provocative follow-up questions to draw out positions
- Pointing out areas where participants seem to agree or disagree but haven't directly engaged with each other
- Asking someone to clarify their position more fully (to generate more useful tokens for the AI)
- Summarising a position and asking participants to verify ("it sounds like you're saying X, is that right?")
- Bringing in metaphors or reframings that might help bridge different communication styles
- Encouraging deliberation between specific participants who seem to hold opposing views

The facilitator's involvement should be limited to encouraging deliberation, not steering it.

**6. The round closes and the AI synthesises.** When the time limit is reached (typically a few days to a week), the facilitator runs the Deliberate prompt (see **Appendix: Prompts**) with all cumulative Deliberate activity for this section. The prompt produces four outputs:

- **Three revised candidate preferences** (consensus, popular, anti-consensus) incorporating the feedback from this round. These remain meaningfully distinct from each other (the prompt is designed to prevent them from converging into variations of the same position).
- **A proposed preference** (a fourth output that draws freely from all three candidates, unconstrained by needing to stay distinct from any of them). This is the version the AI would propose for a Decide vote if the facilitator decided to move forward right now. It's optimised for consent (minimising objections rather than maximising endorsements).

The proposed preference is produced every round, not just when the AI thinks the group is ready. The facilitator can inspect it at any point and decide whether it's strong enough to take to Decide.

**7. If not ready, run another round.** The three revised candidates go to participants for the next round of deliberation. Each round incorporates the ratings and feedback from all previous rounds.

Repeat until the facilitator and lead are confident in the proposed preference. The goal of Deliberate is to generate enough deliberation (enough tokens of people expressing their ideas, demonstrating the edges of their thinking, engaging with each other's positions) that the proposed preference genuinely reflects a position everyone could consent to.

When the facilitator decides to move to Decide, they take the proposed preference from the latest round as the Decide candidate. No separate prompt is needed.

### The real signal: are minds changing?

This is the most important thing to watch for, and it's fundamentally qualitative.

There are two kinds of mind-changing to look for, and one is a much stronger signal than the other.

**Within a round** (the strongest signal). If a participant gives a preference a rating and then, after engaging in conversation with other participants, adjusts that rating within the same round, that's a very strong indication that deliberation is working. Someone read another person's argument and it shifted their thinking. This is the game of deliberation: participants are trying to persuade each other, and when you see ratings move mid-conversation, it means the persuasion is landing. Watch for this closely.

**Between rounds** (useful but harder to interpret). Each round typically has different candidate preferences, so comparing ratings across rounds isn't straightforward. If a preference in round 2 carries a similar position to one in round 1 and a participant's rating has shifted, that's suggestive. But the rest of the text has likely changed too, so it's not an exact science. The qualitative signals matter more here: feedback that references another participant's argument, positions softening, people writing things like "I hadn't considered that, but now I can see how..."

In practice, what typically happens is that one particularly provocative piece of feedback drives most of the conversation in a round. It's rarely the case that everyone comments on everything equally. One person says something that sparks a reaction, and the deliberation clusters around that point. This is normal and healthy.

If nothing is moving (same positions, same arguments, no rating adjustments within rounds), the deliberation isn't working. At that point you have options:

- Surface triggering questions to provoke deeper engagement
- Consider a **synchronous call**. Sometimes async conversations get stuck in ways that a face-to-face conversation can unlock. People often engage differently when they can hear tone of voice and respond in real time. This is an optional tool, but a useful one when the written conversation isn't moving.
- Accept that the group may have genuinely incompatible views on this section and let the Decide mechanism (with its objection and supermajority fallback) handle it.

### Experimental metrics

As with Discover, we're exploring quantitative metrics that might help the facilitator assess where things stand. These are experimental and should be treated as informational, not as decision triggers.

**Minmax.** The lowest rating any participant gave the leading preference. If it's below 5, someone is significantly dissatisfied. Above 5 suggests the preference might be viable. But remember, ratings are subjective, so this is indicative rather than definitive.

**Average rating and median rating.** General satisfaction indicators. Useful for comparing preferences against each other. If the median and average are far apart, you've got an outlier situation worth investigating. The gap between median and average also tells you something: are some participants rating very differently from the rest?

**Support distribution.** How ratings spread across bands (9-10, 7-8, 5-6, 3-4, 0-2). Two preferences can have identical averages but very different distributions. The distribution shows you whether you have lukewarm consensus or a polarised group.

**Gini coefficient.** A measure of inequality in ratings (0 means everyone rated identically, 1 means maximum inequality). High Gini with a decent average means polarisation.

**Engagement depth.** Total and average tokens generated per person per round. You want to see people producing a lot of deliberation, giving detailed feedback. If engagement is dropping across rounds, that may indicate fatigue. Also worth looking at the distribution: are some people contributing a lot while others are barely engaging? This tells you whether the deliberation is genuinely broad or being driven by a vocal subset.

These metrics have not been extensively tested in live assemblies. The real decision to progress remains a qualitative judgment by the facilitator and lead, with the most important signal being whether minds are visibly changing within rounds.

### The Deliberate synthesis prompt

After each Deliberate round closes, run the [Deliberate prompt](prompts/02-deliberate.md) with the Discover stage synthesis and all cumulative Deliberate activity (candidates, ratings, comments, participant-to-participant conversations). The same prompt is used every round, with activity accumulating across rounds.

---

## Phase 4: DECIDE

### Purpose

Narrow down to a single candidate preference and get formal commitment from the group. This is the make-or-break moment.

By the time you reach Decide, there should ideally be broad consensus from the Deliberate phase about roughly where the group is heading. The Decide phase is less about fundamental debate and more about tightening the language, wordsmithing, figuring out whether things should be "shall" or "should" or "must" or "may," and getting everyone to formally commit.

If you're still having fundamental disagreements about the direction at this stage, it may mean you haven't achieved enough convergence in Deliberate and should consider going back.

### Generating the Decide candidate

The Decide candidate comes from the **proposed preference** produced by the final Deliberate round. This is the synthesis that draws from all three deliberation candidates, optimised for consent (the version most people would at least accept, even if it's not everyone's first choice). The key instruction behind it: minimise objections, not maximise endorsements. That's a subtle but important distinction.

The facilitator doesn't need a separate prompt to generate the Decide candidate. It's been produced every Deliberate round and has been improving as the deliberation deepened. The facilitator simply takes the latest one.

We work one preference at a time in Decide. This isn't a comparison exercise anymore. The group examines a single preference and decides: can we accept this?

### The Decide prompt

A single prompt (the [Decide prompt](prompts/03-decide.md)) handles the entire Decide phase. It adapts based on what's happened: if there are no objections, it confirms consensus and reproduces the final text verbatim. If there are objections, it analyses them and generates a revised candidate. The same prompt is used for every Decide round, with activity accumulating across rounds.

### What happens

**1. The facilitator sends the candidate preference to all participants.** Everyone must respond with one of three terms:

**ENDORSE** → "I actively support this. I'm putting my name behind it." No additional text required (but you can provide it).

**CONSENT** → "I can live with this. I'm not blocking it." No additional text required (but you can provide it).

**OBJECT** → "I cannot accept this. Here is specifically what needs to change." Additional text is **required**. You cannot just say "I object." You must explain what would need to change for your objection to move to at least a consent. You can (and ideally should) propose the exact text you'd be happy with.

**2. If there are no objections**, the section is accepted as consensus. The text is inserted into the document and the group moves to the next section.

**3. If there are any objections**, there can be (and should be) discussion around those objections. An objection might stem from a lack of shared understanding (in which case the text just needs to be clearer), or a specific change that needs to be made (in which case the group discusses what wording would work), or a fundamental disagreement (which is harder but still needs to be worked through).

The facilitator takes the Decide candidate preference plus all the feedback from the objections and uses an AI prompt to generate a revised version. If an objector has proposed specific text they'd accept, that text should be incorporated directly. The revised candidate goes through another Endorse / Consent / Object round.

### Silence is consent

This is an important and deliberate design choice. If a participant does not respond to a Decide round within the deadline, their response is recorded as **consent by default**.

There is no ability to abstain.

This might seem harsh, but there are practical reasons for it. Assemblies are time-boxed and the group needs to move forward. In standards organisations without timeout rules, non-response is regularly used as a tactic to delay or block progress. It's unfair to the rest of the group to spend weeks chasing someone for a response while everyone else has moved on.

But this makes it all the more important that participants understand the stakes. Before the assembly begins (ideally during a kickoff call), make it very clear: if you don't respond, your name will be associated with a consent. If you don't like something, you **must** object. Silence will be taken as acceptance.

### Teaching people to object

Objection is the most important skill in this process, and paradoxically, it's the one people are most reluctant to use. Many participants see "I object" as confrontational or harsh. They'd rather stay quiet and hope things get fixed later.

This is a problem, because in a forward-only process, there is no "later." Once a section passes Decide, it's done. Objection is the only mechanism for making changes at this stage.

We've found it helps to practice. In kickoff calls, we run lighthearted exercises where participants practice endorsing, consenting, and objecting to trivial questions (like "what is the best way to cook eggs?"). The goal is to normalise objection. It's not a dramatic act. It can be for something small (a word choice) or something big (a fundamental direction). But it has to happen now, because it can't happen later.

### The fatigue problem

Here's an honest challenge we've observed. The first Decide round typically gets the most engagement. People read the candidate carefully, think about it, and respond with genuine endorses, consents, and objections. But if there's an objection and a second round is needed, engagement drops. By a third round, you often see mostly default consents (people not responding) with very few active responses.

This creates a problematic dynamic. The first candidate tends to "win" not because it's necessarily the best, but because it got the most active engagement. Later rounds may pass with broad default consent from people who've stopped paying attention, which means something could get accepted that people don't actually support.

**Our recommendation: limit Decide to a maximum of three rounds.** Beyond that, fatigue makes the process unreliable. If you're seeing a lot of default consents (people not responding), that's a signal that the process has run its course and you should move to a fallback vote.

### When consensus can't be reached: the fallback vote

If objections persist after the maximum number of Decide rounds, the facilitator doesn't need to run a separate vote. The participants have already effectively voted through their Endorse / Consent / Object responses across all the Decide rounds. The facilitator uses that existing data:

**Step 1.** Look at all the candidate preferences that went through Decide rounds. Each one has a full set of votes from all participants (including default consents from non-respondents). Every round has the same total number of votes.

**Step 2.** Select the preference with the most endorsements and consents combined (default consents count as consents). Since each round has the same total, this is effectively selecting the one with the fewest objections. A round with many default consents will naturally have fewer active endorsements, which dampens its strength without excluding it.

**Step 3.** If two or more preferences are tied on total endorsements plus consents, select the one with the most endorsements.

**Step 4.** If still tied, select the one with the most active responses (active endorsements plus active consents, excluding default consents). This favours the round where people were genuinely engaged.

**Step 5.** If still tied, send those remaining tied preferences to participants and ask them to rate each on a 0-10 scale (the same scale used in Deliberate). Pick the one with the highest minmax score (the one where the lowest individual rating is the highest). This ensures the final selection raises the bar for the least satisfied person.

#### Worked example

An assembly has 10 participants. After three Decide rounds, no preference has achieved zero objections. Here's the voting record:

| | Round 1 | Round 2 | Round 3 |
| --- | --- | --- | --- |
| Active endorsements | 4 | 2 | 1 |
| Active consents | 3 | 3 | 2 |
| Default consents | 1 | 4 | 6 |
| Objections | 2 | 1 | 1 |
| **Total** | **10** | **10** | **10** |

**Step 2: Most endorsements + consents (including defaults).**

- Round 1: 4 + 3 + 1 = 8
- Round 2: 2 + 3 + 4 = 9 ✓
- Round 3: 1 + 2 + 6 = 9 ✓

Round 1 is eliminated. Rounds 2 and 3 are tied at 9.

**Step 3: Most endorsements out of the tied set.**

- Round 2: 2 endorsements ✓
- Round 3: 1 endorsement

**Round 2 wins.** More people actively put their name behind it, even though Round 3 had fewer objections-equivalent (same number of objections, but far fewer active responses).

If Rounds 2 and 3 had also been tied on endorsements, we'd move to Step 4 (most active responses: Round 2 has 5 active vs Round 3 has 3 active, so Round 2 would still win). And if *that* were tied, we'd send both to participants for a 0-10 rating and pick the one with the highest minmax.

This fallback is a last resort and should be rare. If Discover and Deliberate have done their job, most sections should resolve in the first or second Decide round. But having a clear fallback prevents the process from stalling indefinitely.

### When a section achieves consensus

The accepted text is inserted into the target document, and the group moves to the next section. Forward only, no going back.

### Assembly completion

Once all sections have achieved consensus, the facilitator generates a final assembly report. This is encouraged to include information such as how many rounds each section required, participation rates, how the final text connects back to input from the Discover phase, any minority positions that were considered but not adopted, and any sections that required the fallback vote. The exact contents will depend on the assembly and the audience, but the goal is to provide a transparent record of the process and its outcomes.

This report is sent to all participants for informational purposes.

---

## Cheat sheet

A quick reference for each phase: what to watch, what's healthy, what's not, and when to move on.

---

### Design

| What good looks like | Warning signs |
| --- | --- |
| Clear, specific deliverable with defined sections | Vague deliverable ("let's discuss X") |
| Each section has purpose, contains, does not contain, constraints | Sections that are too large (invites kitchen-sink consensus) |
| Sections sequenced with dependencies in mind | No thought given to ordering |
| 3-7 questions per section, mixing types | All questions are the same type |
| Prior art used as a reference point | Starting from a blank sheet |

---

### Discover

**When to move on:** Qualitative judgment by the facilitator, informed by the AI's readiness assessment. The topic space has been sufficiently explored and participants have had enough prompting to form their positions.

| What good looks like | Warning signs |
| --- | --- |
| Long, detailed responses with examples and reasoning | Short, perfunctory responses ("I agree", "sounds fine") |
| Participants engage deeply with questions | Declining response length across rounds (fatigue) |
| Rich, diverse viewpoints surfaced across participants | All responses say essentially the same thing (may indicate shallow questions) |
| Response depth increasing as participants warm up | Participants repeating themselves across rounds |

**Experimental metrics** (informational, not decision triggers):

| Metric | What it might tell you |
| --- | --- |
| Diameter over rounds | Whether the conversation is converging or diverging (caveat: more questions = more text, so diameter may always increase) |
| Cluster count | Whether factions are forming (only meaningful across aggregate of all responses) |
| Response depth (avg tokens per person) | How deeply participants are engaging |

---

### Deliberate

**When to move on:** Qualitative judgment by the facilitator. There's enough deliberation material (enough tokens of people expressing preferences, demonstrating edges, engaging with each other) to confidently generate a single Decide candidate. You don't have to narrow to one preference during Deliberate.

| What good looks like | Warning signs |
| --- | --- |
| Minds visibly changing (especially within rounds) | Positions locked and unchanging across rounds |
| Disagreements emerge and get explored between participants | Universal agreement on everything (>80%), suspicious |
| Participants responding to each other's commentary | People only commenting on preferences, not each other |
| Anti-consensus preference provokes genuine engagement | Everyone writes "looks good" on everything |
| Ratings shift after conversation within a round | Same ratings, same arguments, round after round |
| One provocative comment sparks a rich discussion thread | Silence, or only the facilitator driving conversation |

**Experimental metrics** (informational, not decision triggers):

| Metric | What it might tell you |
| --- | --- |
| Within-round rating changes | Strongest signal: someone changed their mind mid-conversation |
| Minmax (lowest rating on leading preference) | Whether anyone is significantly dissatisfied (≥5 suggests viable, <5 suggests concerns) |
| Average vs median rating | Whether outliers are skewing things |
| Support distribution | Whether you have lukewarm consensus or polarisation |
| Gini coefficient | How unequal the ratings are |
| Engagement depth (tokens per person per round) | Whether engagement is broad or driven by a vocal subset |

---

### Decide

**When it's done:** No objections, or the fallback vote has been applied.

| What good looks like | Warning signs |
| --- | --- |
| Most participants actively endorse or consent | Mostly default consents (people not responding) |
| Objections come with specific, actionable changes | Vague objections ("I just don't like it") |
| Objections spark constructive discussion | Objections met with silence |
| Section resolves in 1-2 rounds | Still running after 3 rounds (fatigue setting in) |
| Objectors propose specific alternative text | Nobody proposes concrete changes |

**Fallback vote tiebreaker** (when objections persist after max rounds):

1. Most endorsements + consents (including defaults) → fewest objections wins
2. If tied: most endorsements
3. If still tied: most active responses (excluding defaults)
4. If still tied: scored voting (0-10), highest minmax wins

---

**Remember:** All metrics in this guide are tools, not rules. The Discover and Deliberate metrics are experimental and still evolving. The strongest signals remain qualitative: are people engaging deeply, are minds changing, are participants exploring each other's positions rather than just stating their own? If you run this process, please share what you learn.

---

## Practical guidance and tooling

You don't need specialised software to run the 4Ds. The process is designed so that participants only ever need to reply to emails. All the tooling complexity sits with the facilitator.

Here's what we recommend.

### Git repository (recommended)

We typically structure the assembly in a Git repository (usually GitHub). The assembly document and the target document template are checked in at the start. As each section achieves consensus through the Decide phase, a pull request is created to replace the placeholder text with the accepted consensus text.

Pull requests are useful for a few reasons. They provide a durable, timestamped record of who endorsed, consented, and objected (which can matter for legal or governance purposes). They allow inline commentary on specific parts of the text. And they give the group a visible, accumulating record of progress as the document fills in section by section.

But a Git repository is optional. A shared folder with markdown files, or even a shared document, works fine if that's what your participants are comfortable with.

### Email

Discover and Deliberate are run over email. Questions go out, responses come back, synthesis reports are distributed, candidate preferences are shared, and participants engage with each other's commentary all through email threads.

We recommend email because it's the one technology that every organisation has access to and every employee has permission to use. Banking and financial institutions in particular often block external collaboration tools, but email always works.

The Decide phase can also run over email, though if you're using GitHub, pull requests provide a natural mechanism for Endorse / Consent / Object.

### AI assistant

Any large language model with a sufficient context window (32k+ tokens recommended) can serve as the AI synthesis agent. The prompts in this guide are designed to be copy-pasteable into Claude, ChatGPT, or similar tools. For larger assemblies with more participants and longer conversation histories, a longer context window helps.

### Spreadsheet

A simple spreadsheet is useful for tracking ratings during Deliberate, computing averages and minmax, monitoring engagement depth (tokens per person), and watching how things change across rounds.

### What you don't need

You don't need a platform login, specialised consensus software, or any tool that participants would need to install or learn. The process is manual and that's fine. You're building understanding of how groups converge (or don't), and doing it by hand teaches you things that automation hides. Once you've run a few assemblies manually and have a feel for the rhythms, there are tools that can automate the email handling, synthesis, metrics, and verification. But start by hand. You'll be a better facilitator for it.

---

*The 4Ds process was developed through a year of running AI-facilitated assemblies at the Green Software Foundation, where it was used to build consensus across a consortium of 70+ member organisations on technical sustainability standards. It draws on ideas from social choice theory, generative social choice theory, and practical facilitation experience.*

*We're still early in this work. Some of what's documented here will change as we run more assemblies and learn more. If you run an assembly using this process, we'd love to hear about it. What worked, what didn't, what metrics proved useful, what surprised you. This guide gets better with more people contributing their experience.*

---

## Appendix: Prompts

The 4Ds process uses three prompts (one per phase: Discover, Deliberate, Decide). Each prompt is designed to be copy-pasted into any AI assistant (Claude, ChatGPT, or similar) with your assembly documents attached or referenced by file path. The prompts are self-contained and reusable across rounds without editing.

These prompts are still evolving. Adapt them to your context.

### The three prompts

**[Discover Synthesis](prompts/01-discover.md)** (Used for every round of the Discover phase. Run it with no responses to generate initial questions. Run it with cumulative responses to generate a synthesis report including emerging candidate preferences, follow-up questions, and a readiness assessment. The same prompt handles both question generation and synthesis).

**[Deliberate Synthesis](prompts/02-deliberate.md)** (Used for every round of the Deliberate phase. Takes the Discover stage synthesis plus all cumulative Deliberate activity. Produces ratings analysis, three revised candidate preferences (consensus, popular, anti-consensus), a proposed preference (the would-be Decide candidate), and a readiness assessment).

**[Decide Synthesis](prompts/03-decide.md)** (Used for every round of the Decide phase. Takes both stage syntheses plus all cumulative Decide activity. If there are no objections, confirms consensus and reproduces the final text verbatim. If there are objections, analyses them and generates a revised candidate with a change log).

### How the prompts connect

Each prompt references the assembly document and the 4Ds guide by file path. Within a phase, all raw participant input is cumulative (each round includes everything from all previous rounds in that phase). Between phases, only the stage synthesis (the final output from the last round) is passed forward:

```text
DISCOVER rounds → cumulative raw responses
  └─ final round output = Discover stage synthesis
       └─ passed to DELIBERATE

DELIBERATE rounds → Discover stage synthesis + cumulative raw activity
  └─ final round output = Deliberate stage synthesis
       └─ passed to DECIDE

DECIDE rounds → Discover + Deliberate stage syntheses + cumulative activity
```

### Response and activity file formats

Each prompt includes a recommended file format for organising participant input. These formats keep the facilitator's work consistent and make it easy to append new rounds without restructuring.

- **[Discover responses](examples/discover-responses.md)** (Grouped by question, then by participant within each question. This keeps related perspectives physically close together).
- **[Deliberate activity](examples/deliberate-activity.md)** (Grouped under each candidate preference, with nested quoting to show conversation threads where participants respond to each other).
- **[Decide activity](examples/decide-activity.md)** (Votes listed per participant with nested quoting for discussion around objections).

### Example assembly document

See **[examples/assembly-document.md](examples/assembly-document.md)** for a complete example of an assembly document with frontmatter, constraints, section definitions (including word count targets), and the section sequencing that the prompts expect.
