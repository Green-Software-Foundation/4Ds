# Discover Responses — Section 1: Scope and Applicability

## Round 1

Questions asked:

1. In your organisation, what types of purchasing decisions involve AI — either as the primary product or as a feature embedded in something else? Give specific examples from the last 12 months.
2. When you hear "AI procurement," what comes to mind? Where would you draw the line between a purchasing decision that needs AI-specific assessment and one that doesn't?
3. Are there types of AI purchasing decisions that you think should be OUT of scope for these guidelines? What and why?
4. What's the biggest gap in your current procurement process when it comes to evaluating AI?

### Question 1

**Participant A:**
We've had three major AI-related purchases this year. First, we bought a fraud detection platform — that was obviously an AI procurement. Second, we renewed our CRM license, but the vendor added "AI-powered insights" as a new feature. Nobody in procurement flagged that as an AI decision, it just went through the normal renewal. Third, we're evaluating a document processing service that uses OCR and classification models. The second one worries me most because AI is sneaking into existing products and our procurement process doesn't catch it.

**Participant B:**
In healthcare, almost everything we buy now has some AI component. Our radiology imaging system uses AI for preliminary reads. Our scheduling system uses ML for capacity prediction. Our EHR vendor just added a clinical decision support module. The challenge is that these are all different risk levels — an AI that helps schedule appointments is very different from one that influences clinical decisions. We need scope that accounts for that gradient.

**Participant C:**
From a legal perspective, we're seeing AI appear in contracts three ways: as the primary deliverable, as a feature of a larger platform, and as something the vendor uses internally to deliver their service (e.g., a translation service that uses AI but doesn't expose the model to us). I'd argue all three need to be in scope, but the assessment depth should vary.

**Participant D:**
We're a cloud provider, so we're on both sides — we procure AI tools internally and we sell AI services. When we procure, the environmental impact is a significant concern. Training and running large models has measurable carbon cost. Most procurement frameworks I've seen completely ignore this dimension.

### Question 2

**Participant A:**
For me, AI procurement means any purchase where the product makes decisions or predictions that affect business outcomes, and where the logic isn't fully transparent. A traditional rules engine doesn't count — you can read the rules. But anything with a trained model, even a simple classifier, should be in scope. The line is: can you fully explain how it reaches its conclusions?

**Participant B:**
I'd draw the line differently. I think it's about autonomy and impact. If the AI is making or strongly influencing decisions that affect people (patients, employees, customers), it needs assessment regardless of how simple the model is. A basic logistic regression that decides whether someone gets a loan is more important to assess than a complex model that optimises warehouse layout.

**Participant C:**
Legally, I'd say any product that processes personal data through automated decision-making is in scope. That aligns with GDPR Article 22 and similar provisions. But I recognise that's a narrow definition — it misses AI used for internal operations where personal data isn't involved.

**Participant D:**
I think the line should be drawn by the vendor's disclosure. If a vendor discloses AI/ML in their product documentation or marketing, it's in scope. If they don't disclose it, it's not in scope but they're on the hook for any issues. This puts the burden of transparency on vendors rather than requiring procurement teams to detect hidden AI.

**Participant E:**
As a small company, I'd want the scope to be narrow enough that we can actually apply it. If every SaaS tool with a recommendation engine counts as "AI procurement," we'd never finish evaluating anything. There needs to be a materiality threshold.

### Question 3

**Participant A:**
Consumer AI tools that individual employees choose to use — things like personal AI assistants or browser extensions. Those should be covered by acceptable use policies, not procurement guidelines.

**Participant B:**
I'd keep internal R&D experimentation out of scope. When our data science team is experimenting with models during development, that's not procurement. The guidelines should kick in when something moves to production or when we're buying from a third party.

**Participant C:**
AI used purely for internal analytics where no decisions about individuals are made. If someone runs a model to forecast quarterly revenue, that doesn't need the same scrutiny as a model that evaluates employee performance.

**Participant F:**
I'd be cautious about excluding too much. In government, we've seen "internal analytics" tools quietly become decision-making tools. I'd prefer scope that's broad with proportionate assessment rather than narrow with strict assessment.

### Question 4

**Participant A:**
We don't have standardised questions to ask AI vendors. Every procurement manager makes it up as they go. Some ask great questions, some don't ask any AI-specific questions at all.

**Participant B:**
The biggest gap is ongoing monitoring. We do a reasonable job evaluating at purchase time, but we have no process for re-evaluating when the vendor updates their models. We found out six months after the fact that our radiology AI vendor had retrained their model on a different dataset.

**Participant E:**
Honestly, the biggest gap is knowledge. Our procurement team doesn't know what questions to ask because they don't understand AI well enough. We need guidelines that don't assume AI expertise.

**Participant G:**
The gap I see across organisations is the absence of contextual risk assessment. People either apply maximum scrutiny to everything (which is unsustainable) or no scrutiny to anything (which is dangerous). There's no middle ground that says "for this type of AI in this context, here's the appropriate level of assessment."

## Round 2

Questions asked:

1. Several participants raised the issue of AI features appearing in existing products without being flagged by procurement. How should guidelines handle this "embedded AI" scenario — where AI is a feature, not the product?
2. There's a tension between keeping scope broad enough to be safe and narrow enough to be practical. If you had to define a single test for "does this need AI-specific procurement assessment," what would it be?

### Question 1

**Participant A:**
I think the guidelines need to require that vendors disclose AI features. If procurement doesn't know AI is present, they can't assess it. So the first step is getting visibility, and that's a contractual requirement, not a procurement process.

**Participant C:**
Agreed, but disclosure alone isn't enough. You also need a trigger mechanism — when a vendor adds AI features to an existing product mid-contract, that should automatically trigger a reassessment. Otherwise it falls through the cracks.

**Participant E:**
For small companies, this is really hard. We don't have the leverage to demand disclosure from large vendors. If Microsoft adds an AI feature to Office 365, we're not going to negotiate a disclosure clause. The guidelines need to be realistic about power dynamics.

**Participant H:**
In retail, we handle this through our vendor management programme. Any material change to a product requires notification. We just need to add "introduction of AI/ML capabilities" to the definition of material change. It's not a new process, it's extending an existing one.

### Question 2

**Participant B:**
My single test: "Does this product use automated processing to generate outputs that influence decisions about people or critical operations?" If yes, AI-specific assessment is needed. If it's purely informational with a human always in the loop making the actual decision, lighter-touch assessment.

**Participant F:**
I'd frame it as: "Would a failure or bias in this system cause harm that's difficult to detect or reverse?" That captures both the severity and the opacity dimensions. A transparent system with easily reversible outputs is lower risk than an opaque system with sticky consequences.

**Participant G:**
I'd add a practical modifier: "...and the organisation doesn't have the internal expertise to evaluate it without guidance." This keeps highly technical organisations from being burdened by guidelines designed for less technical ones. But I'm not sure if that's too subjective.

**Participant I:**
From a data protection perspective, the test is clearer: "Does this product process personal data through automated means where the processing could have legal or similarly significant effects on individuals?" That's essentially the GDPR test, and it works well as a bright line. But I acknowledge it doesn't cover non-personal-data AI uses.
