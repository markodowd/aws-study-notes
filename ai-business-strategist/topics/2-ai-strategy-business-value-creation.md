# Domain 2 - AI Strategy and Business Value Creation

## Task 2.1: Develop AI strategies that align with business objectives

### Skill 2.1.1: Identify high-impact AI use cases across business functions (for example, customer operations, sales and marketing, research and development, software development) and map AI capabilities to specific business outcomes

**AI Capability Types**

- **Prediction**: Estimating future outcomes from historical patterns (Demand Forecasting)
- **Classification**: Sorting inputs into defined categories (Defect Detection)
- **Pattern Recognition**: Finding structure in unstructured data (Fraud Signals)
- **Recommendation**: Surfacing the next best action or option (Pricing Optimisation)

#### Use Case Selection Criteria

**Business Impact**

Does solving this problem move a metric that matters? Revenue, cost, customer retention, operational efficiency. If the answer is, "It would be nice," that's not enough

**Data Availability**

- Does the data exist?
- Is it accessible?
- Is it clean enough to train on?

The most common reason AI projects fail isn't the model, it's the data. Research shows 34% of organizations that missed expected AI value blamed poor use case selection. Most of those had data problems they didn't discover until after they'd committed

**Organizational Readiness**

- Does the team have the capability to build, deploy, and maintain this?
- Is there a process owner who will actually use the output?

An AI model that no one trusts or acts on delivers zero value

**Strategic Alignment**

- Does this initiative support where the business is going?

A use case that solves a real problem but contradicts the three-year roadmap will get defunded at the next budget cycle

### Skill 2.1.2: Evaluate build-buy-partner decisions for AI implementations (by considering factors including budget, timelines, capabilities, vendor proposals, and regulatory compliance requirements)

**Three Implementation Paths (Decision Point)**

- Build - Full control, longest timeline
- Buy - Fastest to value, least control
- Partner - Shared risk, shared ownership

**Build**

Your team designs, develops, and owns the AI solution from the ground up

- Full control over the model, the data, and the roadmap
- Highest upfront cost and longest time to value (typically 9–18 months for a production-ready system)
- Requires in-house data science capability, or the budget to hire it
- IP (Intellectual Property) stays with you; no vendor dependency
- Right when: the use case is core to your competitive advantage, your data is proprietary, or no vendor solution fits your requirements

**Buy**

You license a pre-built AI product or platform from a vendor

- Fastest path to value (weeks, not months)
- Lower upfront cost, but ongoing licensing fees that compound over time
- Limited customization, you get what the vendor built, configured to your parameters
- Vendor dependency: if they change pricing, deprecate features, or get acquired, you're exposed
- Right when: the use case is not a differentiator, a proven solution exists, and speed matters more than control

**Partner**

You co-develop with a third party (system integrator, startup, consulting firm, or cloud provider)

- Shared development cost and shared risk
- Faster than build, more customizable than buy
- IP ownership is negotiable, and if you don't negotiate it upfront, you may not own what you paid to build
- Partner quality varies significantly; due diligence matters
- Right when: you need custom capability but lack the internal team to build it, or when the partner brings proprietary data or domain expertise you can't replicate

**Budget and Total Cost of Ownership (TCO)**

Don't compare upfront costs. Compare 3-year TCO. A vendor solution at $400K/year looks cheaper than a $1.2M build. That flips by year three, once the build is paid off and the vendor fee keeps compounding. Include implementation, integration, maintenance, retraining, and talent costs in every comparison

**Timeline**

How quickly does the business need value? If the CFO (Chief Financial Officer) needs ROI evidence in 12 months, an 18-month build path isn't viable, regardless of its long-term economics

**Internal Capabilities**

Does your team have the data science, ML (Machine Learning) engineering, and MLOps (Machine Learning Operations) capability to build and maintain this? A build decision made without that capability becomes a de facto partner decision. You just discover it after committing the budget

**Differentiation**

Is this AI capability a competitive advantage for you, or is it something every organization in your industry will eventually have? If it's truly differentiating, build it so no one else has it. If it's table stakes, buy the best available solution and move on

**Regulatory Compliance**

Some industries and use cases have compliance requirements that constrain the path. Data residency rules may prohibit certain cloud vendors. Explainability requirements may rule out black-box models. Audit trail requirements may favor build over buy. Know your constraints before you evaluate options

### Skill 2.1.3: Prioritize AI initiatives based on business value, feasibility, sustainability, and strategic alignment (by deciding to scale, pause, or terminate initiatives)

**Portfolio Prioritization Criteria**

- Business Value - Quantified ROI Projection
  Business value: What is the measurable impact if this initiative succeeds? Revenue growth, cost reduction, customer retention, operational efficiency. Quantify it. "Strategic" is not a number
- Feasability - Data + Team + Timeline Confirmed
  Feasibility: Can this initiative actually be executed given current data, team capability, and timeline? An initiative with high value and low feasibility is a wish, not a plan
- Sustainability - Cost Curve Improves, Data Flywheel Exists
  Sustainability: Will this initiative continue to deliver value after the initial deployment? Three dimensions:
  Economic sustainability, Does the cost curve improve at scale, or does it get worse? An initiative that costs $500K to run at pilot scale and $2M to run at enterprise scale may not be worth scaling
  Data flywheel, Does the model improve as it processes more data? Initiatives with self-reinforcing data loops compound in value over time. Initiatives without them plateau
  Organizational sustainability, Does this initiative survive its creators? If the only person who understands how it works leaves, does it collapse? Initiatives that require heroic maintenance are fragile
- Strategic Alignment - Aligned To Strategic Roadmap
  Strategic alignment: Does this initiative support where the business is going over the next three years? An initiative can solve a real problem and still contradict the strategic roadmap. That gets it defunded at the next budget cycle, regardless of results

#### Three Buckets for Every Initiative

**Scale**

The initiative has demonstrated value, the data supports it, the team can execute, and the cost curve improves at scale. Move it forward. Increase investment. Expand scope

- Early KPIs are tracking
- Adoption is above 60%
- The model is improving
- The sponsor is engaged
- The business case holds at scale

**Pause**

- A specific, resolvable condition is blocking progress
- The initiative has merit, but it can't move forward until that condition is met
- Pause with a clear condition and a deadline. If the condition isn't met by the deadline, the pause becomes a termination

Signals: Data access issue that's being resolved. Key hire in progress. Regulatory approval pending. Sponsor transition underway. The fundamental case is still valid

**Terminate**

- The fundamental case no longer holds
- The problem has changed, the data doesn't support the model
- The business has moved on
- The initiative has consumed budget without producing results. Stop it. Redeploy the resources

Signals: Adoption below 20% after 6 months with no recovery plan. Model accuracy not improving. Business case assumptions have changed. No sponsor willing to own it. Sunk cost is the only argument for continuing

### Skill 2.1.4: Determine when AI is not the appropriate solution for a business problem

**When AI is not the answer**

#### Deterministic vs Probabilistic Problems

Three signals for rule-based automation

The most expensive AI mistake isn't a failed model. It's building an AI solution for a problem that didn't need one. Three signals that a problem is better solved with rule-based automation than AI:

Deterministic rules exist. If you can write down every condition and every outcome, "if X, then Y", you don't need AI. You need a workflow engine. Expense approval routing, invoice matching, compliance checklists: these are rule-based problems
High volume, low variability. If the inputs are consistent and the output is always the same, a rules engine outperforms a model. It's also cheaper, faster to build, and easier to audit
No ambiguity in the correct answer. AI is designed for situations where the right answer isn't obvious from the inputs. If the right answer is always obvious, AI adds complexity without adding value

**When AI is the answer**

- High variability in inputs (customer behavior, equipment wear patterns, market signals)
- Complex patterns that humans can't reliably detect at scale (visual defects, fraud signals, demand anomalies)
- Prediction or classification needed (what will happen, what category does this belong to)
- The cost of a wrong answer is low enough to tolerate model error rates

### Skill 2.1.5: Evaluate key considerations when preparing to transition business processes to AIbased solutions or between AI platforms (for example, business continuity, cost implications, data readiness, performance impact)

**Transition Planning**

**Four factors determine how you plan the transition**

- Business continuity: What happens if the AI system fails during the transition? For a vision QC (Quality Control) system on a production line, a failure means uninspected product reaching customers. For a demand forecasting system, a failure means reverting to manual planning. The higher the continuity risk, the more conservative the transition approach
- Cost implications: Running two systems in parallel (the old process and the new AI system) costs money. Parallel running is the safest approach, but it's also the most expensive. The transition plan needs to account for the overlap period
- Data readiness: Is the data the AI system needs available and clean at the point of transition? A system that performs well in testing on historical data may behave differently on live production data. Plan for a calibration period
- Performance impact: How will the transition affect the people doing the work? A scheduling system that changes how plant managers plan their week requires change management, not just a software deployment. Adoption is a transition risk, not just a technical one

**Three Transition Approaches**

**Parallel Running**

Both the old process and the new AI system operate simultaneously. Results are compared. The AI system takes over only when it has demonstrated consistent performance. Safest approach; highest cost

**Phased Rollout**

The AI system is deployed in stages (one plant, one product line, one team) before full deployment. Limits blast radius if something goes wrong. Requires clear criteria for advancing each phase

**Rollback Planning**

Define the trigger conditions under which you revert to the prior process. What accuracy threshold, what error rate, what business impact triggers a rollback? Having a rollback plan isn't pessimism, it's the condition that lets you move forward confidently

## Task 2.2: Measure and demonstrate AI business value

### Skill 2.2.1: Define key performance indicators (KPIs) for AI initiatives, including tangible benefits (for example, cost reduction, revenue growth) and intangible benefits (for example, customer satisfaction, employee productivity)

**Measurement Problem**

- How to define the right KPIs for an AI initiative, the metrics that actually prove value to the stakeholders who matter
- How to establish the baselines those KPIs will be measured against, before the initiative starts, not after

#### Tangible & Intangible Benefits

All AI value needs to be measurable, or it cannot be defended

**Tangible Benefits**

- Cost reduction
- Revenue growth
- Time savings
- Productivity gains

**Intangible Benefits**

- Customer satisfaction
- Employee productivity
- Brand perception
- Organizational agility

**Stakeholder KPI Framing**

| Role | Primary KPI Concern | Question They're Asking | KPI Types That Answer It |
|---|---|---|---|
| CFO (Chief Financial Officer) | Financial return | "What is the financial return?" | Cost reduction, payback period, revenue impact. Translate intangibles into financial proxies (e.g., 8-point CSAT (Customer Satisfaction) improvement = 3% churn reduction = $X retained revenue) |
| CHRO (Chief Human Resources Officer) | Workforce impact | "What is the workforce impact?" | Employee productivity, time recovered from manual tasks, satisfaction scores. Frame cost numbers as "hours recovered" not "headcount reduced" |
| CIO (Chief Information Officer) | Strategic alignment / roadmap fit | "Does this align with the roadmap?" | Adoption rate, integration health, technical debt reduction. KPIs that show the initiative is running through official governed channels, since shadow AI tools spreading outside the governed stack are a separate risk |

### Skill 2.2.2: Establish baseline metrics before implementing AI solutions to accurately measure AI adoption effects

A KPI without a baseline is an opinion. A KPI with a baseline is evidence

**Process Performance**: How long does the current process take? What is the error rate? What is the throughput? These are the numbers the AI initiative is supposed to improve
**Customer Metrics**: What is the current CSAT score? NPS (Net Promoter Score)? Complaint volume? If the AI initiative is supposed to improve customer experience, you need to know where you started
**Operational Metrics**: What is the current scrap rate, downtime frequency, OEE (Overall Equipment Effectiveness), or defect rate? These are the operational KPIs most AI initiatives in manufacturing are designed to move
**Financial Metrics**: What is the current cost per unit, revenue per customer, or margin? These are the numbers the CFO will use to calculate ROI

**Three Common Baseline Mistakes**

- Starting before measuring
- Using averages
- Ignoring seasonality

**The Launch Test**

Before any AI initiative launches, ask, "If this initiative delivers exactly what we expect, what number will be different, and what is that number today?" If you cannot answer both parts, you are not ready to launch

### Skill 2.2.3: Calculate AI return on investment (ROI) by using comprehensive frameworks (for example, time savings, cost reduction, revenue growth, productivity gains)

Four-Component ROI Framework

**Calculating ROI**

ROI = (Total Benefits - Total Costs) ÷ Total Costs x 100

**Why ROI Calculations Fail**

- What most people calculate
- Direct savings only
- Upfront costs only
- No hidden costs

**What the CFO Needs**

- Direct savings + indirect gains
- All cost categories (hidden & ongoing)
- Productivity gains quantified

1: Direct Savings

Direct savings are the costs that go away or go down because of the AI initiative. Scrap reduction, fewer unplanned downtime events, reduced manual inspection labor, lower rework costs. These are the easiest to calculate and the first thing the CFO will ask for

2: Indirect Gains

Indirect gains are the value created that doesn't show up directly on the cost line. Improved customer retention because product quality is higher. Faster response to customer complaints because defect data is real-time. Competitive positioning because the company can offer quality guarantees competitors can't. These are real but require a translation step to quantify

3: Hidden Costs

Hidden costs are the costs that weren't in the original business case but show up during implementation and operation. Compute costs that scale with production volume. Model retraining cycles when product mix changes. Integration maintenance when the ERP (Enterprise Resource Planning) system is upgraded. Talent costs for the data science team that has to monitor and maintain the model. These are the numbers that make a short payback period look considerably longer in retrospect

4: Productivity Gains

Productivity gains are the time and capacity recovered from manual processes. Plant managers who spent 4 hours per shift reviewing QC reports now spend 45 minutes. Quality engineers who manually sampled 5% of production now have 100% coverage with automated flagging. These gains are real but often undercounted because they don't show up as headcount reductions

Build the complete ROI picture
The CFO will ask about all four. If you only bring direct savings, the CFO will ask about the costs you did not include. You need to build the complete picture before you walk in

**Payback Period Calculation**

1: Investment period

Cumulative cost still runs ahead of cumulative benefit. The initiative is being paid for and has returned nothing yet

2: The crossover point

Cumulative benefit overtakes cumulative cost. This is the payback period, and it is the figure a CFO compares against other uses of the same capital

3: Value period

Benefit continues to accrue against a cost base that has already been recovered

4: What sits behind the line

Total investment cost includes first-year operating costs, not just the upfront spend. Leaving those out moves the crossover earlier than reality

**Data Point Calculations**

- **Total Investment Cost** = upfront implementation + first-year operating costs
- **Annual Net Benefit** = annual direct savings + annual productivity gains − annual operating costs

**Payback Period Formula**

- **Payback Period** = Total Investment Cost ÷ Annual Net Benefit

**What the CFO will also ask**

- Opportunity cost: What else could we have done with this capital? If the $680K partner investment could have returned 12% in another initiative, the AI initiative needs to beat that hurdle rate
- Risk adjustment: What's the probability that the projected benefits actually materialize? An 8-month payback on a 90% confidence projection is different from an 8-month payback on a 60% confidence projection
- Sensitivity: What happens to the payback period if the scrap rate improvement is 0.8% instead of 1.1%? If compute costs run 20% over estimate? The CFO wants to know the range, not just the point estimate

The discipline
Build the ROI model in a spreadsheet before the meeting, not during it. Know your sensitivity ranges. Know which assumptions are most likely to be challenged. The CFO will test the model — your job is to have already stress-tested it yourself

### Skill 2.2.4: Identify leading indicators that predict AI project success

- Adoption
- Data Pipeline
- Sponsor
- Accuracy Trajectory

#### Leading vs. Lagging Indicators

**Leading Indicators**

- User adoption rate: available at 30/60/90 days; predicts whether ROI will materialize
- Data pipeline health: available continuously; predicts model accuracy degradation
- Sponsor engagement: available in real time; predicts organizational support risk
- Model accuracy trajectory: available weekly; predicts whether model is learning or plateauing

**Lagging Indicators**

- ROI achieved: available 12–24 months after launch; confirms the initiative worked
- Cost savings realized: confirms financial return but arrives after the fact
- Revenue generated: confirms value but can't be acted on retroactively
- Customer retention improved: confirms customer impact after the relationship is already at risk

**Four Leading Indicators**

- Adoption rate
- Data pipeline health
- Sponsor engagement
- Accuracy trajectory

One yellow signal is a monitor. Two yellow signals are an investigation. Two red signals are an escalation

### Skill 2.2.5: Implement basic cost factor controls for AI implementations, including cost planning and optimization strategies

**AI Cost Drivers**

1: Compute

Compute costs are the most common source of budget overruns. Inference costs scale with production volume. Experiment costs scale with the number of model iterations the data science team runs. Running experiments on full production data instead of sampled data can generate 3–5x the expected compute bill within the first six months

2: Data Storage

Data storage costs compound quietly. Every model version needs to be stored. Every training dataset needs to be retained for audit and retraining purposes. Without a data retention policy, storage costs grow linearly with time and never come down

3: Model Retraining

Model retraining costs are triggered by events: product mix changes, seasonal shifts, data drift, accuracy degradation. Each retraining cycle consumes compute, data science time, and validation effort. Organizations that don't plan for retraining cycles underestimate the ongoing cost of keeping a model accurate

4: Talent

Talent costs are the most underestimated. The data science team that built the model needs to monitor it, retrain it, and respond to production incidents. A two-person team supporting three production models is a capacity constraint that shows up first as delayed retraining cycles and degraded model performance, only later as a budget line

**Cost Control strategies**

- Right-Sizing
- Data Sampling
- Retention Policies
- Shared Infrastructure

## Task 2.3: Position AI for competitive advantage

### Skill 2.3.1: Assess competitive landscapes and identify advantages to adopting AI

Announcement is not the analysis

**What we know**

- Evidence-based signals
- Verified capabilities

**What we assume**

- Stated intentions
- Unverified claims

**Competitive AI Capability Assessment**

1: Data Assets

AI is only as good as the data feeding it. What proprietary data does the competitor have, and how is it being collected? Real-time defect telemetry requires sensors on every line, a unified data pipeline, and years of labeled training data. If the competitor hasn't had that infrastructure, the "real-time" claim in the announcement is aspirational, not operational

2: Technical Infrastructure

What systems does this deployment actually require? An AI-powered transparency platform for CPG (Consumer Packaged Goods) customers needs three things in real time: edge computing at the plant level, a customer-facing data API (Application Programming Interface), and a model that can process and serve results at production speed. Each of these is a significant infrastructure investment. Check for evidence: job postings, technology partnerships, patent filings, supplier relationships

3: Organizational Capability

Does the competitor have the talent and governance to build and sustain this? A two-person data science function can deliver a pilot. It cannot sustain a production platform across five plants while managing model drift, retraining cycles, and customer-specific integrations. Look for evidence of team scale, not just announcements

4: Customer Integration

How deeply is the AI embedded in the customer's workflow? A dashboard that customers can log into is easy to replicate. A system where the customer's procurement platform pulls defect data directly from the competitor's API is a switching cost. The difference between feature and moat is how tightly the capability is woven into how the customer operates

**Burden of Proof by Dimension**

For each dimension ask, "What evidence would confirm this is real?"

A press release confirms intent. A customer reference confirms adoption. A production deployment with measurable customer outcomes confirms capability. The burden of proof increases with each dimension

### Skill 2.3.2: Identify opportunities to transform business models by using AI solutions

Business Model Change or Feature Upgrade

**Value Creation**

- Feature Update: Improves the competitor's offering within their existing model
- Business Model Change: Alters how the competitor creates and captures value — shifts from product to data and intelligence

**Switching Cost**

- Feature Update: Low - customers can switch away with normal friction
- Business Model Change: High — generated through integration depth; the customer's workflow is rebuilt around the competitor's system

**Response timeline Months**

- Feature Update: can be matched through focused product development
- Business Model Change: 18–36 months — you are not just building technology, you are rebuilding the customer's workflow

#### Three signals of business model change

**Value Creation Locus Shifts**

The competitor is no longer competing primarily on product quality, price, or service. They are competing on data and intelligence. The transparency platform does not just tell customers whether their packaging is defect-free. It gives CPG brands a data asset they can use in their own operations: real-time quality data for supplier scorecards, sustainability reporting, and customer-facing traceability

**Switching Cost is Generated**

The more customer data the competitor's platform ingests, the more valuable it becomes and the harder it is to switch away from. A packaging supplier embedded in a CPG brand's supplier scorecard system is hard to replace, even when the packaging itself is a commodity

**Response Timeline Lengthens**

A feature can be responded to in months. A platform with deep customer integration takes 18–36 months to displace, because you are not just building comparable technology. You are rebuilding the customer's workflow around a new system

### Skill 2.3.3: Describe how AI creates sustainable competitive advantages and operational improvements

#### Strategic response options

**When To Choose It**

- **Accelerate**: The competitor's move genuinely changes the basis of competition. The market is validating the direction (customers asking, not just the competitor announcing). Your organization has the capability or partnership access to execute
- **Hold**: The capability assessment shows significant gaps between announcement and production reality. The industry maturity stage does not yet reward the capability being announced. Your current competitive advantages are intact
- **Pivot**: The competitor has a genuine head start in the AI capability dimension, and your organization has a different advantage that customers value: relationship depth, speed-to-customization, regulatory expertise, geographic proximity, or proprietary formulation capability

**What It Requires**

- **Accelerate**: Capital above the current run rate; organizational bandwidth; a credible plan to reach feature parity before the competitor locks in customer integration
- **Hold**: A clear monitoring cadence (what signals would change your assessment?) and a communication plan for accounts that are asking
- **Pivot**: Honest assessment of which advantages are genuinely durable; a customer conversation to validate that the differentiated position is one customers will pay for

**What It Risks**

- **Accelerate**: Overinvesting ahead of market validation; stretching the data science team and IT infrastructure beyond sustainable capacity
- **Hold**: Missing the window if the competitor's platform matures faster than expected; allowing customer uncertainty to grow
- **Pivot**: Ceding the AI capability dimension if the market moves that direction faster than expected; investing in a differentiator that customers value less than you believe

**The Signal You Are Right**

- **Accelerate**: Customers begin making purchasing decisions based on the capability you are building, not just asking about it
- **Hold**: No accounts shift purchasing behavior based on the competitor's platform over the observation period
- **Pivot**: Customers renew and expand based on the differentiated position, not despite the AI gap

#### Competitive advantage durability grid

1: Durable differentiator

Hard to replicate and clearly valued by customers. Proprietary operational data, earned regulatory approvals, deep account relationships. Protect these and deepen them

2: Commoditizing

Customers value it, but a competitor can buy it. Most commercially available AI tooling sits here. Expect the advantage to erode as rivals acquire the same capability

3: Undervalued asset

Hard to replicate, but customers do not currently pay for it. Test whether the market can be taught to value it before investing further

4: Divest

Neither valued by customers nor defensible against competitors. Redirect the investment

### Skill 2.3.4: Determine appropriate AI investment levels based on industry maturity and competitive dynamics

**Industry AI Adoption**

- Experimental
- Early Adoption
- Growth
- Mature

#### Four-Stage Maturity Model

**Stage 1: Experimental**

- What AI looks like: Small number of players running pilots. Results mixed and hard to compare. No standard use cases
- Underinvestment risk: Minimal, being behind leaders is normal and defensible
- Overinvestment risk: High, committing capital before market proof creates stranded investment
- Appropriate posture: Watch and run targeted experiments

**Stage 2: Early Adoption**

- What AI looks like: Standard use cases emerging and proving out. 15–30% of competitors have production deployments with measurable results. Leading companies building data assets that will compound
- Underinvestment risk: Rising, waiting too long means entering a compounding disadvantage
- Overinvestment risk: Remains present, not every announced capability is real, and market pricing of AI value has not fully formed
- Appropriate posture: Selective expansion on proven use cases

**Stage 3: Growth**

- What AI looks like: Majority adoption underway. AI standard in leading companies. Competitors without production deployments are visibly behind
- Underinvestment risk: High, differentiation is becoming harder as the baseline rises
- Overinvestment risk: Shifts to specific capabilities rather than AI in general
- Appropriate posture: Close gaps on standard use cases; differentiate on proprietary data

**Stage 4: Mature**

- What AI looks like: AI is infrastructure. Built into products, processes, and customer expectations. Not having AI is a disqualifier
- Underinvestment risk: Existential, absence of AI is visible failure
- Overinvestment risk: Shifts to "where specifically?" not "how much?"
- Appropriate posture: Optimize; AI is cost of doing business

**Investment posture by position**

- Ahead of the industry
- In line with the industry
- Behind the industry

**Investment posture mistakes**

- Investing at Stage 4 pace in a Stage 2 industry: Building full AI infrastructure before the market values it creates stranded costs and organizational fatigue. The industry isn't rewarding AI-maturity yet. It's rewarding AI-proof in specific use cases

- Investing at Stage 1 pace in a Stage 2 industry: Treating the current moment as still experimental when peers are building production deployments means entering a compounding disadvantage. The cost of catching up is higher than the cost of keeping pace

- Letting one aggressive competitor set your investment level: The right reference point is the industry median, not the most aggressive player. If the leading competitor is investing at Stage 3 pace in a Stage 2 industry, following them may be right. Or they may be ahead of what the market will value. Evaluate the competitor's capability (Lesson 1) before using them as the investment benchmark
