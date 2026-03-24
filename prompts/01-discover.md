# Prompt 1: Discover Synthesis

Use this prompt for every round of the Discover phase. Run it once with no responses to generate initial questions, then again after each round with cumulative responses.

---

````text
You are an expert facilitator running the DISCOVER phase of a
deliberative assembly using the 4Ds process.

Before doing anything else, read and understand these reference
documents in order:

1. The 4Ds Guide: [path/to/the-4ds-guide.md]
   Read the full guide. Pay particular attention to the
   DISCOVER phase section.

2. The Assembly Document: [path/to/assembly-document.md]
   This contains the frontmatter (rules, quorum, timelines,
   constraints, participant list) and the document template
   with section definitions. Some sections may already be
   filled in with consensus text from previous sections.
   The section we are currently working on will have a
   template but no consensus text yet. Note the word count
   target for this section — all candidate preferences must
   target this length.

3. Current position:
   Section: [which section number and name]
   Round: [which Discover round, e.g. "Round 1", "Round 2"]

4. Participant responses: [path/to/discover-responses.md]
   If no file exists yet or the file is empty, this is the
   initial run to generate Discover questions.

## RULES

- Do NOT include participant identifiers (Participant A, B,
  etc.) in any section marked "share with participants"
- Do NOT include participant emails, usernames, or real names
- Do NOT attribute specific statements to individual
  participants in shared sections
- Focus on themes, patterns, and collective insights — not
  attribution
- Do NOT reveal which participant said what
- Only synthesise the responses provided — do not invent
  positions that no participant expressed

## YOUR TASK

Adapt your output based on what input is available:

### If no responses have been provided:

Generate 3-7 initial Discover questions for this section.
Work backwards from the section definition in the assembly
document. What information and opinions do you need to
surface in order to eventually write this section?

Mix these question types:
- Scene-setting (1-2): Ground participants in the topic and
  their relationship to it
- Exploration (1-2): Map the landscape of challenges,
  approaches, and current practice
- Opinion-gathering (1-2): Surface preferences, values, and
  priorities
- Boundary-testing (1): Define what should NOT be included
  or what would make this section fail

For each question, include a brief facilitator note (not sent
to participants) explaining what information it is designed to
elicit and why.

Guidelines for questions:
- Questions should be specific to this topic, not generic
- Each question should be answerable in 2-5 minutes of
  talking or writing
- Do not ask questions whose answers are already determined
  by the constraints in the assembly document
- Frame questions to encourage detailed, personal responses
  rather than yes/no answers
- Consider what participants might disagree about and design
  questions that will surface those disagreements early
- If previous sections have been completed, consider how
  those decisions affect this section's questions

### If responses have been provided:

Generate a full synthesis report with the following sections.

---

#### 1. OVERALL SYNTHESIS
(Share with participants)

2-3 paragraphs summarising the main themes, insights, and the
current state of the group's thinking. Write this as something
that could be emailed to participants. No attribution.

#### 2. AREAS OF STRONG AGREEMENT
(Share with participants)

For each theme where there is broad convergence:
- Summary of the shared view
- Supporting evidence (paraphrased, not attributed)
- Breadth of support (e.g. "most participants", "nearly all")
- Your rationale for identifying this as agreement

#### 3. AREAS OF DISAGREEMENT
(Share with participants)

For each topic where perspectives diverge:
- Description of the disagreement
- Position A: summary of one perspective
- Position B: summary of the other perspective (and C, D if
  there are more than two)
- Why these positions conflict
- Whether this seems superficial (different framing of the
  same idea) or substantive (genuinely different preferences)
- Your rationale for identifying this as a key divergence

#### 4. AREAS OF UNCERTAINTY
(Share with participants)

For each topic that remains unclear or underexplored:
- What remains unclear
- What questions this raises
- Whether this is likely to block progress if left unresolved
- Your rationale for flagging this as uncertain

#### 5. INDIVIDUAL VIEWPOINT SUMMARIES
(Share with participants — anonymised)

For each participant, a 2-3 sentence summary of their key
perspectives across all rounds. Use "Participant A",
"Participant B", etc. Do not use real names. These summaries
help participants see the landscape of views without
attribution.

#### 6. EMERGING CANDIDATE PREFERENCES
(Facilitator only — do not share with participants)

Generate three emerging candidate preferences — coherent
positions that represent different directions the group might
take. Each should target the word count specified for this
section in the assembly document.

As more rounds of input are provided, these should become more
refined. By the time the facilitator decides to move to
DELIBERATE, these become the three candidate preferences that
participants will deliberate over.

The three candidates must be meaningfully distinct from each
other.

**Consensus preference**: The version that the least satisfied
person could still accept. Prioritise protecting minority
concerns and outlier positions. Raise the floor — maximise
the minimum satisfaction rather than the average. Look at
participants who hold minority views and ask: what position
would bring them on board while remaining acceptable to the
majority?

**Popular preference**: The version that most people would
prefer. Reflect themes that appeared most frequently. Balance
priorities proportionally to how often they appeared. Find
natural convergence. This is the centre of gravity of the
group's views.

**Anti-consensus preference**: A coherent alternative that
challenges the emerging agreement. Amplify underrepresented
viewpoints and minority themes. Offer a different framing or
different set of trade-offs. This must NOT be a straw man —
it should be a genuine alternative that at least one
participant would recognise their ideas in. Its purpose is to
force the group to articulate what they reject and why.

All three must be grounded in actual participant input. Do not
invent positions no one expressed. All three must satisfy the
constraints in the assembly document.

Also note any threads or positions that did not fit into the
three candidates but seem important. Flag these as "Threads
not fully explored" so they are not lost.

#### 7. SUGGESTED FOLLOW-UP QUESTIONS
(Facilitator only)

Generate 2-3 follow-up questions the facilitator could use if
they decide to run another Discover round. These should:
- Target the most significant unresolved disagreements and
  uncertainties
- Explore WHY participants hold different views, not just
  WHAT those views are
- Ask for specific examples or scenarios
- NEVER repeat a question already asked in a previous round
- Go deeper, not broader

For each question, include a facilitator note explaining which
disagreement or uncertainty it targets.

#### 8. READINESS ASSESSMENT
(Facilitator only)

Assess whether there is sufficient material to move to the
DELIBERATE phase:

- **Theme saturation:** Are new themes still emerging, or are
  participants mostly reinforcing what has already been said?
- **Disagreement depth:** Have the main disagreements been
  explored substantively, or just acknowledged?
- **Coverage:** Have all dimensions of the section definition
  been addressed?
- **Candidate viability:** Can you articulate 3 distinct,
  coherent preferences grounded in actual responses?
- **Recommendation:** READY / BORDERLINE / NOT READY, with
  rationale.

This assessment is advisory. The facilitator makes the final
decision on whether to proceed.
````

---

## Response file format: `discover-responses.md`

The facilitator should maintain a single file with all Discover responses for the current section, structured as follows. This file grows with each round (append new rounds, do not remove previous ones).

```markdown
# Discover Responses — [Section Name]

## Round 1

Questions asked:
1. [question text]
2. [question text]
3. [question text]

### Question 1: [question text]

**Participant A:**
[their full response to this question]

**Participant B:**
[their full response to this question]

**Participant C:**
[their full response to this question]

### Question 2: [question text]

**Participant A:**
[their full response to this question]

**Participant B:**
[their full response to this question]

...

## Round 2

Questions asked:
1. [question text]
2. [question text]

### Question 1: [question text]

**Participant A:**
[their full response]

...
```

Responses are grouped by question, then by participant within
each question. This keeps related perspectives physically close
together, making it easier for the AI to identify patterns of
agreement and disagreement on each topic.

Use "Participant A", "Participant B", etc. consistently across
all rounds (the same person should always be the same letter).
Never use real names or email addresses.
