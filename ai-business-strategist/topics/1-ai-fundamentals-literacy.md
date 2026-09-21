# Domain 1 - AI Fundamentals and Literacy

## Task 1.1: Describe core AI concepts and define terminology

**Amazon Bedrock**

A managed AWS (Amazon Web Services) service for building GenAI (Generative AI) applications using foundation models from multiple providers through a single API

**Amazon SageMaker AI**

AWS's platform for building, training, and deploying custom ML (Machine Learning) models

**Amazon Quick**

A standalone, agentic AI (Artificial Intelligence) workspace for business users and knowledge workers

**CEO (Chief Executive Officer)**

The executive stakeholder focused on the strategic, board-level view of the AI initiative

- Comfortable with strategic framing
- Less comfortable with mechanics
- Asks questions on behalf of the board

**CDO (Chief Digital Officer)**

The stakeholder who owns the organization's digital transformation roadmap

- Owns the digital roadmap
- New to AI specifically
- Skeptical of vendor over-claims
- Reviews every draft

**CFO (Chief Financial Officer)**

The stakeholder responsible for validating the financial case for the AI investment

- Demands ROI clarity
- Will challenge any unjustified investment claims in the briefing

**Engineering**

The technical team supplying the underlying data and system details for the briefing

- Provides a technical glossary, a data inventory, and notes on training data
- None of it written for an executive audience

### Skill 1.1.1: Recognize and explain fundamental AI concepts in business contexts (for example, algorithms, models, training, inference, predictions)

**Algorithm**

A set of step-by-step rules or calculations a computer follows to process data and produce a result

**Model**

The output of training: a system that has learned patterns from data and can be used to make predictions or decisions on new inputs

**Training**

The process of feeding historical data into an algorithm so it can learn patterns and produce a model

**Inference**

Using a trained model to generate an output, such as a prediction or classification, from new input it has not seen before

**Prediction**

The output a model produces, such as a forecast, score, or classification, based on the patterns it learned during training

### Skill 1.1.2: Distinguish between AI, Machine Learning (ML), and Generative AI (GenAI)

**AI (Artificial Intelligence)**

Any system that performs tasks normally requiring human-like judgment

- Classifying
- Predicting
- Recognising Patterns
- Generating Content

**ML (Machine Learning)**

A way of building AI in which systems learn patterns from data instead of following hand-written rules

- System learns patterns from data

**GenAI (Generative AI)**

A subset of ML focused on producing new content

- Text
- Images
- Code
- Audio

**The Hierarchy**

AI, ML, GenAI are not interchangeable. They are nested

AI > ML > GenAI

Artificial Intelligence (AI) is the umbrella term. It covers any system that performs tasks normally requiring human-like judgment, such as classifying, predicting, recognizing patterns, generating content, or making decisions

Machine learning (ML) is a way of building AI. Instead of writing rules by hand, ML systems learn patterns from data. Almost all modern AI is built using ML

Generative AI is a way of building ML systems that produce new content (text, images, code, audio). Generative AI is a subset of ML, which is a subset of AI

### Skill 1.1.3: Distinguish between structured and unstructured data and explain the relevance of data types for AI

**Structured Data**

Data organized into a fixed, predictable format, such as rows and columns in a database or spreadsheet

**Semi-Structured Data**

Data with some organizational structure but no fixed schema, such as JSON (JavaScript Object Notation) or XML (Extensible Markup Language) files

**Unstructured Data**

Data with no predefined format, such as free text, images, audio, or video

#### Data Type Match

Demand Forecast: Structured
Service Chatbot: Semi-Structured
Product Generator: Unstructured
Recommendation Engine: Structured, Unstructured

### Skill 1.1.4: Data Quality Matters for AI Outcomes

Garbage in, garbage out

Each of the following five defects produces its own kind of AI failure

**Incomplete records (missing values)**

The AI cannot learn the pattern for those records. If 15% of products are missing category labels, the model has 15% less information to learn from. Worse, it may make confident predictions about products in the missing category that are systematically wrong

**Outdated Information**

The AI learns yesterday's customer behavior and applies it to today. The patterns the model sees in training do not match the patterns customers are showing now

**Inconsistent Formatting (currency, dates, units, codes)**

The AI treats the same value as multiple different values. The system's view of reality fragments

**Biased Samples**

Some segments of customers, products, or situations are over-represented in the data. Others are under-represented. The model becomes confident about the over-represented ones and inaccurate about the under-represented ones

**Duplicate Records**

Some examples are weighted more heavily than they should be. The model's predictions skew toward the over-counted patterns

### Skill 1.1.5: Explain concepts related to training an AI model by using historical data

**Training**

The system processes historical examples where the answer is already known. For a churn model, that means looking at customers from the past who either stayed or left. The system finds patterns: which behaviors, purchases, support interactions, or engagement metrics tend to precede a customer leaving. It builds a model that predicts whether a new customer is likely to leave

The training data is the examples. The trained model is the result. Inference is when the model uses that learning to predict for a new customer

#### Choosing which historical data to use

**Keep**

- Relevance. The data describes the same kind of customer behavior the model will see in production. Past data about behaviors no longer measured is not relevant

- Recency. The data reflects current customer patterns. If customer behavior shifted significantly in the last year, training on three-year-old data may produce a model that predicts last year's customers, not this year's

- Completeness. There is enough of the right kind of data to learn from. A model trained on a thousand customers is less reliable than one trained on a million

- Representativeness. The data covers the full range of customers the model will face. If your training data only includes loyalty members, the model will be unreliable on non-members

**Exclude**

- Data from a period when the business operated very differently. Pandemic-era purchasing patterns are not predictive of current behavior. Data from before a major reorganization or system migration may reflect a business that no longer exists

- Data correlated with the outcome but not available at prediction time. A common churn-modeling mistake is including the cancellation event itself in the training data. The model "predicts" by noticing that the customer already canceled. That is useless in production

- Data with significant gaps for important segments. If you cannot represent a customer segment in training, your model cannot reliably serve that segment in production

- Data from a vendor or system you no longer use. If the data will not be available going forward, the model ends up depending on a feature you cannot supply later

**Public Consequences of Getting It Wrong**

When historical data is chosen poorly, the resulting model failures become visible to customers and the public, not just to the team that built it

### Skill 1.1.6: Ensure awareness of global frameworks and unified AI vocabulary (for example, ISO/IEC 23053, ISO/IEC 42001)

**ISO/IEC 23053 (AI System Framework)**

ISO/IEC 23053 is a framework for describing AI systems. It provides a shared vocabulary, letting one organization describe an "AI system" or a "model" so other organizations and regulators interpret it consistently. Think of it as the dictionary the industry agreed on

When a vendor uses 23053 vocabulary, they signal that their system descriptions can be checked against an international reference, not just against vendor marketing language

**ISO/IEC 42001 (AI Management System)**

ISO/IEC 42001 is the first international standard for AI Management Systems. It describes how an organization should govern its use of AI. Who is responsible for what. How AI lifecycle decisions get made. What oversight exists. How risks are managed

It is structurally comparable to ISO 9001 (quality management) or ISO 27001 (information security). If you have worked with those standards, you have a feel for what 42001 looks like in practice

When a vendor cites 42001 alignment, they are signaling that their internal AI governance is structured against an international standard

**The Two-Standard Comparison**

| Dimension | ISO/IEC 23053 | ISO/IEC 42001 |
|---|---|---|
| Purpose | Shared vocabulary for describing AI systems | Governance of AI inside the organization |
| Scope | How vendors talk about their systems | Who owns what; how risks are managed |
| Aligned | Uses the agreed-on vocabulary | Internal practices map to the standard |

**Standardized Vocabulary Matters**

What "alignment" does and does not mean
This is the part of the lesson that matters most for the briefing

"Alignment" is not the same as "certification." This is the single distinction the lesson says matters most. Flip each card to see who is actually attesting to the claim

**Alignment**

Self-declared: the vendor structured its practices in line with the standard

**Certification**

Independently verified: an outside body confirmed the practices meet the standard

**Recognizing the limits**

These are awareness-level frameworks for this module's purposes. The job here is to recognize these references in vendor materials and ask one more level of question because of it

## Task 1.2: Identify and select appropriate AI solution types

### Skill 1.2.1: Determine when to use rule-based automation and when to use AI solutions

**Predictability**

- Same inputs: Rule
- different inputs: AI

**Data Complexity**

- Small number of structured fields: Rule
- Free-text, images, audio, or many subtle factors: AI

**Decision Variability**

- Same answer every time: Rule
- Answer change based on context, history, or learned patterns: AI

**Cost of Error**

- Rule: Predictable, visible
- AI: Less predictable, sometimes silent

#### What to ask the vendor

What part of this is actually AI versus rules?
The honest answer often reveals a system that is 80% rules with a small AI component for one specific decision. That can still be the right system. It is not the system the marketing language describes

What data does the AI part learn from?
If the answer is "we use proprietary algorithms" or "our AI is trained on industry data," the vendor is dodging. Sound vendors can describe what their system learns from in concrete terms

How does this perform compared to a well-designed rules-based system on the same task?
Vendors rarely volunteer this comparison because the comparison is often unflattering. If the rules-based system performs equally well and costs less, the case for AI weakens

### Skill 1.2.2: Distinguish AI agents from other AI solutions and identify the core capabilities of AI agents (for example, autonomy, tool use, agent-to-agent communication, and orchestration strategies)

**Agent**

An AI agent is built on top of an AI model, usually a large language model. The agent has access to tools: the ability to look things up, call APIs, and take actions in real systems. It can plan multi-step actions and decide which tool to use at each step. It runs in a feedback loop. It perceives the environment, reasons about what to do, takes an action, perceives the result, then decides what to do next

**Core Capabilities of an Agent**

Four capabilities define an AI agent. Two of them are what separate a single agent from the other AI solutions you have seen. The other two appear once more than one agent is involved

- Autonomy. The agent decides its own next step inside the perceive-reason-act loop. It does not wait for a person to run each step. This is the capability that separates an agent from a generative AI tool, which produces output only when prompted. Autonomy is also why agents need governance: an agent without human checkpoints can take actions the company never anticipated or authorized, which is why human review points and audit trails matter for agents in a way they do not for a tool that only generates text

- Tool use. The agent reaches into real systems. It looks things up, calls APIs, and takes actions, rather than only producing text. This is the capability that separates an agent from a predictive model, which outputs a score or a category but does not act

- Agent-to-agent communication and orchestration strategies are the remaining two core capabilities. They describe how multiple agents pass work between each other and how that work is coordinated

**The Four-Shape Comparison**

| System Type | What It Does | Acts on Systems? | Right Fit When |
|---|---|---|---|
| Predictive model | Outputs a score or classification | No | The decision is "is this fraud" or "is this likely to churn" |
| Generative AI | Produces new content on prompt | No | The task is to write, summarize, draft, or translate |
| AI agent | Reasons, plans, and takes multi-step actions | Yes | Multi-step reasoning is required and real systems are involved |
| Rule-based automation | Executes predefined rules | Yes (predictably) | Inputs and decisions are predictable |

**What is not an Agent**

Three systems get called agents and are not. Each one falls short on a different capability

- A generative AI tool that produces output on each prompt
- A rule-based workflow that automates steps
- A predictive model that scores or classifies

The distinction is not academic. Each of these systems is appropriate for different problems. Calling all of them "agents" obscures the choice

#### When an Agent is the Right Shape

**Fits**

- Multi-step reasoning. The next step depends on the result of the previous step. The system has to think and act in sequence, not in a single response
- Interaction with external systems. The task requires looking things up in real systems (CRM (Customer Relationship Management), inventory, payment, scheduling). A pure generative AI tool cannot reach those systems
- A range of acceptable resolutions. There is more than one right answer for a given input, and the agent has to choose among them based on context

**Does not fit**

- Simple lookup or generation tasks. If the task is "answer this question" or "write this email," an agent adds cost and complexity for no benefit. A generative AI tool with RAG (Retrieval Augmented Generation) handles the lookup case. A generative AI tool with good prompts handles the generation case
- Tasks with strict compliance or audit requirements. If every step needs to be human-reviewed, an agent that decides on its own removes the review point. A workflow with humans in the loop is the better shape
- Tasks where the cost of an unexpected action is high. Agents reason and act. The cost of an unexpected action determines whether you want a system that acts on its own

#### Recognizing Multi-Agent Patterns and Orchestration

Three multi-agent patterns at recognition depth

**Sequential**

One agent's output becomes the next agent's input, in a fixed order

**Parallel Processing**

Multiple agents work on different parts of a task at the same time, and their outputs are combined

**Supervisor-Worker**

A supervisor agent assigns tasks to specialized worker agents and combines their results

**Agent-to-Agent Communication**

Agents pass structured information to each other. Often as text or as structured data formats like JSON. The handoff is the moment errors compound

**Orchestration**

Some platforms have a built-in supervisor agent that coordinates. Other platforms use external orchestration logic, like a workflow engine, that calls agents like services. Both approaches work

### Skill 1.2.3: Describe why AI solutions require ongoing monitoring and updates to detect and remediate model drift and performance changes

**Why AI systems degrade on their own**

A model is trained on data from a specific point in time. The model captures the patterns in that data. Then the world keeps moving. Customer behavior shifts. Product mixes change. Seasons turn. Markets respond to events the training data never saw. The model's view of reality goes stale even though the model itself has not changed

This is called model drift. The model's outputs become less accurate over time without anyone touching the system

**Three categories of drift in business terms**

**Data Drift**

The inputs the model sees are different from the inputs it was trained on

**Concept Drift**

The relationship between inputs and the right output has changed

**Performance Drift**

Measured outcomes decline even when the inputs and the model both look stable

**What monitoring looks like**

Monitoring is not a technical exercise that lives only in engineering. It is a leadership decision about what to watch and what to do when the watch lights up

- Track outcome metrics over time. Whatever metric proves the system is delivering value, track it daily or weekly. Open rate, click-through, conversion, escalation rate, return rate

- Compare input distributions to training-time distributions. Are the inputs the model is seeing today similar to what it was trained on? Engineering can produce this comparison automatically

- Set thresholds that trigger investigation. When a metric falls more than X percent in Y weeks, somebody has to look. The thresholds should be defined in advance, not invented when the metric slips

- Define a response plan in advance. When monitoring catches a problem, what happens? Retrain the model? Roll back to the previous version? Pause the system? Page somebody? The plan exists or it does not

**The leadership cost of skipping monitoring**

Many AI initiatives skip monitoring at launch because the system is "working." Within a quarter, the system has degraded and nobody noticed. The customer noticed. The competitor noticed. The team finds out from the wrong source

Monitoring costs money. Not monitoring costs more. The price of building monitoring at launch is small. The price of explaining to the CEO why an AI system silently failed for two months is much larger

### Skill 1.2.4: Establish transparent classification of AI tools (for example, approved, blocked, under evaluation) to mitigate shadow AI risks

**What Shadow AI is**

Shadow AI is the use of AI tools the organization has not formally approved. Most often free or personal-account versions of public tools. Driven by the same dynamics that produce Shadow IT: employees move faster than approval processes

**Approved**

The tool has passed review. Security review. Privacy review. Vendor diligence. Data handling review. Use cases the review covered are explicitly permitted. Use cases the review did not cover are not yet permitted under the same approval

Approved is not permanent. A tool that was approved can move to "under evaluation" or "blocked" if conditions change: a security incident, a vendor policy change, a regulatory shift

**Under Evaluation**

The tool is in the review process. Employees may not use it for production work yet. A pilot program may be allowed under controlled conditions: limited scope, defined timeline, explicit data restrictions. Pilots produce evidence the review uses to make a final classification

Under evaluation has a timeline. Tools that sit "under evaluation" for nine months are not under evaluation. They are in limbo. The framework should specify how long evaluation can run before a decision is required

**Blocked**

The tool fails review or carries risks the organization is not willing to accept. Active enforcement: network blocks, policy enforcement, manager communication. The reason for the block should be specific and documented, not "we said no"

Blocking without communicating alternatives drives Shadow AI underground. Employees with real productivity needs find harder-to-monitor tools. The communication has to include "here is what we did approve and why"

#### What the framework needs

- Clear criteria for each category
- A defined review process with named owners
- A communication plan. Employees need to know what is available, what is blocked, what is coming
- A response plan for when employees use blocked tools
- A re-review cadence

Governance actions per category

**Category Actions**

- Approved: Training, documented usage guidelines, monitoring of use, periodic re-review, single-sign-on integration where possible
- Under evaluation: Sandboxed pilots, collected feedback, defined timeline, explicit data restrictions, named pilot owner
- Blocked: Policy communication, technical enforcement (network blocks where feasible), education on why and what alternatives exist, response plan when employees use the tool anyway

**Leadership Framing**

Banning AI tools without alternatives does not work - Employees find workarounds because they have real productivity needs. The framework's job is to channel those needs toward approved tools, not to suppress them

"Approved" is not permanent - Review cadence is the discipline that keeps the framework honest. Without it, classifications calcify. The organization ends up governing an outdated picture of what its tools actually do

Communication matters more than enforcement - Most employees comply when they understand what is available and why. Heavy enforcement without clear communication produces resentment and harder-to-detect Shadow AI

## Task 1.3: Apply GenAI concepts and techniques

### Skill 1.3.1: Apply basic prompt engineering principles to achieve desired AI outputs

**Prompt**

A prompt is the input you give a generative AI tool: the task you want done, any context it needs, and any constraints the output must honor

**Task**

The thing you want done

**Context**

The background the tool needs to fit your situation: product, audience, brand voice

**Constraints**

The limits the output must honor: length, tone, words to avoid

**Format**

The shape of the output, so the people and systems downstream get what they expect

#### Four Prompt Engineering Principles

**Clarity**

State the task once, in plain language, with no ambiguity. One task per prompt

**Specificity**

Add concrete constraints the tool cannot ignore: length, audience, tone, format, things to avoid

**Context Provision**

Give the tool the background information it needs to produce output that fits your situation: brand attributes, audience traits, product details, past examples that worked

**Structured Output**

Tell the tool the shape of the output, such as bullet points, JSON (JavaScript Object Notation), or a table, especially when another system or person expects a specific format

#### Common Prompt Patterns

**Zero-Shot**

Asking the model to complete a task with no examples, relying only on its instructions

**Few-Shot**

Giving the model a small number of examples of the task done well before asking it to do the task

**Chain-of-Thought (CoT)**

Asking the model to reason step by step before giving its final answer, which improves accuracy on multi-step tasks

#### Good Prompting in Practice

Your team will not write a perfect prompt every time. The goal is not to write every prompt yourself. Your job is to recognize what good looks like and help your team build a shared library of prompts that worked. The library compounds: the more good prompts the team can adapt, the faster the team gets to good output on new tasks

### Skill 1.3.2: Identify when token limits or context window constraints affect GenAI system performance

**Token**

A token is a chunk of text the model processes as a unit. A common short word is usually one token; long words, brand names, and uncommon terms are often two or three tokens. Both the input (the prompt) and the output (the model's response) count toward billing and limits

This is also why two prompts of the same character length can have different costs. A prompt full of common English words uses fewer tokens. A prompt full of brand names, product SKUs (Stock Keeping Units), and customer IDs (Identifiers) uses more

#### What a context window is, in business terms

When the conversation or input exceeds the window, some information falls out of view. The model literally cannot reference it anymore. It may not even warn you. It just produces output as if that information was never there

#### Practical implications

**Long inputs may exceed the window silently**

The tool does not flag the cutoff. It produces output and behaves as if it had everything you sent. Spot checks are the only way to catch the problem

**Larger context windows are not always better**

They cost more. They can slow down responses. They do not fix prompt quality issues, model accuracy issues, or the team's prompt-engineering practices. A larger window is a hammer; not every problem is a nail

**The right fix is often upstream of the model**

Most context-window problems can be solved by sending less per prompt. Summarize the customer history before sending it. Send only the most recent N items. Restructure the prompt to focus on the segment that matters for the task

### Skill 1.3.3: Recognize how model adaptation techniques (for example, Retrieval Augmented Generation (RAG), fine-tuning) improve AI responses for specific business needs

#### What out-of-the-box Generative AI (GenAI) Can't Do

Off-the-shelf generative AI tools have three known limits when applied to a specific business. Both of the vendor's proposals exist because of them

**They do not know your company-specific information**
Product catalogs, internal policies, current inventory, named programs. The tool was trained on public data. Your private data is not in there

**They do not sound like your brand by default**
They sound like the average of everything they were trained on. For most companies, that average reads as bland, generic, or vaguely corporate

**They sometimes invent information to fill gaps**
When the tool does not know an answer but the prompt expects one, it can produce confident-sounding output that is wrong. This is called hallucination. It is one of the central risks responsible-AI practices are designed to address. Hallucination is not limited to topics the tool has no information on. A model can also produce confident, wrong output on topics it was trained on. "The model knows this subject" is never a guarantee the answer is correct

#### RAG (Retrieval-Augmented Generation)

**The model is given a reference library**: your product catalog, your policies, your knowledge base. At query time, the system retrieves the most relevant items from the library. It gives them to the model along with the user's question. The model answers based on the retrieved information rather than its general training

**Right fit when**: The answer needs to be grounded in your company-specific information that changes frequently. Examples: product specs, pricing, return policies, store hours, current inventory, policy FAQs

**Why frequency matters**: Updating a RAG system means updating the library. New policy goes in the library; the next query references it. No retraining required. This is a major operational advantage when your information changes regularly

#### Fine-tuning in business terms

The model is retrained on a curated set of your company's content: past customer emails, brand-voice copy, internal style guides, examples of writing that worked. The retrained model learns the patterns: voice, structure, vocabulary, sentence rhythm. It applies them to new tasks even when the input does not include explicit voice guidance

**Right fit when**: The output needs to consistently match your specific style or domain language. Examples: brand voice for marketing copy, internal report formatting, specialized industry vocabulary, regulated-industry phrasing

**Why consistency matters**: A fine-tuned model produces on-brand output by default. The team does not have to add voice guidance to every prompt. Over many prompts, this saves time and produces more consistent output than prompt engineering alone can achieve

#### Caution

Before proposing fine-tuning, flag one caution: it retrains the model on your proprietary company content, which carries data-governance and security implications the CISO (Chief Information Security Officer) will need to approve. Raise it as a data-handling decision, not just a quality upgrade. The security conversation needs to happen before the vendor commitment, not after

The tradeoffs:

**RAG**

- Faster
- Lower up front
- Update the library; the model stays the same
- Grounding answers in current company information

**Fine-Tuning**

- Slower
- Higher up front
- Retrain when the style or domain shifts significantly
- Consistent style or specialized language

**What this means for the two requests**

Customer service chatbot. The bottleneck is information, not voice. The team needs answers that match the current policy and product catalog. The information changes often. The output style is less critical because customers expect a customer-service tone, not a brand-voice tone. RAG is the right fit

Marketing brand voice. The bottleneck is voice, not information. The team needs the tool to consistently produce on-brand output without rewriting. The brand voice changes rarely. Fine-tuning is the right fit
