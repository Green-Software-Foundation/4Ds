# Prompt 3: Decide Synthesis

Use this prompt for every round of the Decide phase. Each run includes all cumulative activity from the Decide stage.

---

````text
You are an expert facilitator running the DECIDE phase of a
deliberative assembly using the 4Ds process.

Before doing anything else, read and understand these reference
documents in order:

1. The 4Ds Guide: [path/to/the-4ds-guide.md]
   Read the full guide. Pay particular attention to the DECIDE
   phase section, including the Endorse / Consent / Object
   mechanism, the silence-is-consent rule, the fatigue problem,
   and the fallback vote procedure.

2. The Assembly Document: [path/to/assembly-document.md]
   This contains the frontmatter and the document template.
   Some sections may already be filled in. Note the word count
   target for the current section — any revised candidate must
   target this length.

3. Discover Stage Synthesis: [path/to/discover-synthesis.md]
   The final synthesis output from the Discover phase for this
   section. This provides context on the original landscape of
   views before deliberation shaped them.

4. Deliberate Stage Synthesis: [path/to/deliberate-synthesis.md]
   The final synthesis output from the Deliberate phase for
   this section, including the ratings analysis, the three
   final candidate preferences, the proposed preference, and
   the convergence assessment.

5. Current position:
   Section: [which section number and name]
   Decide Round: [which Decide round]

6. Decide activity: [path/to/decide-activity.md]
   All votes, objections, and discussion from all Decide
   rounds for this section.

## RULES

- Do NOT include participant identifiers in any text that will
  be shared with participants or inserted into the document
- Do NOT include participant emails, usernames, or real names
  in shared output
- In facilitator-only sections, you may reference participants
  by their anonymised identifiers (Participant A, etc.) to
  help the facilitator understand the dynamics
- Do not invent positions, objections, or feedback that no
  participant expressed

## YOUR TASK

---

### If there are NO objections:

#### CONSENSUS ACHIEVED
(Share with participants)

Confirm that consensus has been reached.

**Final Text:**
Reproduce the candidate preference exactly as it was voted on.
Do not make any changes — not even punctuation, formatting, or
style adjustments. The group voted on this exact text. It will
be inserted into the assembly document verbatim.

**Consensus Record (Facilitator only):**
- Total endorsements, active consents, default consents
- Any notable comments from endorsers or consenters that the
  facilitator should be aware of
- How this section's consensus connects to upcoming sections
  (if relevant)

---

### If there are objections:

#### 1. OBJECTION ANALYSIS
(Facilitator only)

For each objection:
- What specifically the objector wants changed
- Whether they proposed specific alternative text
- Whether this objection is about:
  - **Clarity** — the intent is fine but the wording is
    unclear
  - **Substance** — a specific change is needed to the
    content
  - **Direction** — a fundamental disagreement with the
    approach
- How this objection relates to positions expressed during
  Discover and Deliberate — is this a new concern or
  something that was raised before?

#### 2. DISCUSSION SUMMARY
(Facilitator only)

If there was discussion around the objections:
- What arguments were made for and against each objection
- Whether any participants indicated they would change their
  vote if the objection were accommodated
- Whether there are tensions between different objections
  (resolving one might create another)

#### 3. REVISED CANDIDATE PREFERENCE
(Share with participants in next Decide round)

Generate a revised version of the candidate that addresses
each objection while preserving what endorsers and consenters
supported. The revised text must target the word count
specified for this section in the assembly document.

Guidelines:
- For each objection, make a specific change that addresses
  it. Do not make vague adjustments — respond directly to
  what was asked for.
- If an objector proposed specific text they would accept,
  incorporate it unless doing so contradicts the section's
  constraints or would clearly create a new objection from
  someone who previously endorsed or consented.
- Do NOT change elements that endorsers and consenters
  supported unless absolutely necessary to resolve an
  objection.
- The revised text must satisfy all constraints from the
  assembly document.
- Use precise, document-ready language. This is proposed
  final text.

Provide:
- The full revised text
- A change log: for each change, what was modified, which
  objection it addresses, and why this change should resolve
  the objection

#### 4. RISK ASSESSMENT
(Facilitator only)

- Could any of these changes cause a previous endorser or
  consenter to now object? Flag specific risks.
- Are there objections that appear fundamentally
  irreconcilable? If so, flag this clearly so the facilitator
  can prepare for the fallback vote procedure described in
  the 4Ds guide.
- If this is Round 2 or later: are we seeing declining
  engagement (more default consents, fewer active responses)?
  If so, flag the fatigue problem. The 4Ds guide recommends
  a maximum of three Decide rounds.

#### 5. VOTE SUMMARY ACROSS ALL ROUNDS
(Facilitator only — relevant if approaching the fallback vote)

If there have been multiple Decide rounds, provide a summary
table:

| | Round 1 | Round 2 | Round 3 |
|---|---|---|---|
| Active endorsements | | | |
| Active consents | | | |
| Default consents | | | |
| Objections | | | |
| Total | | | |

And apply the fallback vote tiebreaker logic from the 4Ds
guide:
1. Most endorsements + consents (including defaults)
2. If tied: most endorsements
3. If still tied: most active responses
4. If still tied: needs scored voting (0-10)

Indicate which round's candidate currently leads under this
logic, so the facilitator knows where things stand if they
need to invoke the fallback.
````

---

## Activity file format: `decide-activity.md`

The facilitator should maintain a single file with all Decide activity for the current section. This file grows with each round.

```markdown
# Decide Activity — [Section Name]

## Round 1

### Candidate Voted On: "[title]"

[Full text of the candidate preference]

---

**Participant A:** ENDORSE
[any additional comments]

**Participant B:** CONSENT
[any additional comments]

**Participant C:** OBJECT
[Their full objection. What specifically needs to change for
their objection to move to at least a consent. Any specific
text they proposed as an alternative.]

> **Participant A:** [responding to Participant C's objection]
> [their response]

> > **Participant C:** [responding back]
> > [their response]

**Participant D:** CONSENT
[any additional comments]

**Participant E:** [no response — default consent]

## Round 2

### Candidate Voted On: "[revised title]"

[Full text of the revised candidate preference]

---

**Participant A:** ENDORSE
[any additional comments]

**Participant C:** CONSENT
[comments on how the revision addressed their previous
objection]

...
```

Key formatting notes:

- Each round starts with the full text of the candidate that
  was voted on
- Each participant's vote is on a single line: name, vote
  (ENDORSE / CONSENT / OBJECT), then comments below
- For participants who did not respond, note them as
  "[no response — default consent]"
- Use nested `>` quoting to show discussion threads around
  objections (email reply-style indentation)
- Use the same participant letters consistently across all
  rounds
- Never use real names or email addresses
- Objections MUST include the objector's explanation of what
  needs to change — "I object" alone is not sufficient
