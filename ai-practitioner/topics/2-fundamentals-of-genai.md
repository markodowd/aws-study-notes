# Domain 2 - Fundamentals of GenAI

## Neural Networks and Deep Learning

- Input Layer
- Hidden Layer
- Output Layer

- Deep Learning
  - Neural Network with many hidden layers
  - Backpropagation

## Generative AI Models

- Generative Adversarial Network (GAN)
- Variational Autoencoder (VAE)
- Transformer Model
- Diffusion Model

## Generative Adversarial Network (GAN)

Random Noise > Generator > Synthetic Data > Discriminator > Classification
                  ^ Adversarial Feedback                        ^ Real Data

## Variational Autoencoder (VAE)

- Complex neural network and advanced probability theory

Input data > Encoder > Latent Space > Decoder
                          ^               ^ Reconstructed Data
                        Generated Data

## VAE Use Cases

- Anomaly Detection
- Drug Discovery
- Sound

## Transformer Model

- Input Embedding
  - Converts token into a vector
- Positional Encoding
  - Unique numberical vector to each position
- Encoder Stack
  - Attemptes to understand meaning
- Decoder Stack
  - Generating an output sequence
  - Masked self-attention
  - Encoder-decoder attention
  - Output generation

Input Text > Input Embedding + Positional Encoding > Encoder Stack > Decoder Stack > Output Text

- Transformer is a prediction engine

## Diffusion Model

- Forward Diffusion
- Reverse Diffusion

## Foundation Models

- Large Language Model (LLM)
- Multimodal

## Training Foundation Models

- Data Selection
- Pretraining
- Optimization
  - Fine-tuning
  - Retrieval-augmented generation
- Evaluation
- Deployment

## Fine Tuning

- Data Collection
- Privacy and Security
- Data Labeling
- Training
  - Instruction fine-tuning
  - RLHF
  - Iterate and Evaluate

## Advanced Fine Tuning

- Low-rank Adaptation (LoRA)
- Representation fine-tuning (ReFT)

## RAG

- Data Collection and indexing
- Chunking
- Embedding Creation
- Vector Database Storage
- User input
- Processing User Input
- Retrieval
- Augmentation
- Response

## AWS Vector Database Capabilities

- Amazon OpenSearch Service
- Amazon OpenSearch Serverless
- Amazon Kendra

## RAG Disadvantages

- Not enough relevant data
- Search limitations
- Chunking problems

## Evaluation

- Human Evaluation
  - User Experience
  - Contextual Appropriateness
  - Creativity and Flexibility
  - Ethical Considerations
  - Emotional Intelligence
- Benchmark Datasets
  - Accuracy
  - Speed and Efficiency
  - Scalability
  - Responsible AI
  - Robustness
  - Generalization
- Standard Evaluation Metrics
  - Recall-Oriented Understudy for Gisting Evaluation (ROUGE)
  - Bilingual Evaluation Understudy (BLEU)
  - Bidirection encoder representations from transformers score (BERTScore)

## Task Statement 2.1: Explain the basic concepts of generative AI (GenAI).

### Define foundational GenAI concepts

- **Tokens**
  - Smallest units a model processes; can be words, subwords, or characters depending on tokenizer
  - Input and output length limits are measured in tokens (context window)
  - Token count directly affects inference cost on token-priced services (e.g., Bedrock)
  - Longer prompts and outputs = more tokens = higher cost and latency

- **Chunking**
  - Splitting large documents into smaller segments for processing
  - Needed when source material exceeds model context window
  - Chunk size and overlap affect retrieval quality and answer accuracy
  - Common in RAG pipelines: chunk → embed → store → retrieve relevant chunks at query time
  - Strategies: fixed-size, sentence-based, semantic, or document-structure-aware (headings, paragraphs)

- **Embeddings**
  - Dense numerical vectors that represent meaning of text (or other data) in high-dimensional space
  - Similar concepts map to nearby points in vector space
  - Used for semantic search, clustering, classification, and RAG retrieval
  - AWS: Amazon Titan Embeddings, Cohere Embed via Bedrock, SageMaker embedding models

- **Vectors**
  - Arrays of numbers representing data in a mathematical space
  - Embeddings are a type of vector
  - Stored in vector databases for similarity search (nearest-neighbor lookup)
  - Distance metrics: cosine similarity, dot product, Euclidean distance
  - AWS: Amazon OpenSearch Serverless (vector search), Aurora PostgreSQL with pgvector, Bedrock Knowledge Bases

- **Prompt engineering**
  - Crafting inputs (prompts) to guide model behavior without changing model weights
  - Techniques: clear instructions, role assignment, few-shot examples, chain-of-thought, output format constraints
  - Iterative refinement based on model responses
  - Lower cost and faster than fine-tuning for many tasks
  - Bedrock supports system prompts, inference parameters (temperature, top-p, max tokens)

- **Transformer-based Large Language Models (LLMs)**
  - Built on the transformer architecture (attention mechanism)
  - Process entire sequences in parallel during training (unlike RNNs)
  - Self-attention lets the model weigh relationships between all tokens in context
  - Scale to billions of parameters; pre-trained on massive text corpora
  - Autoregressive: predict next token given prior tokens (GPT-style)
  - Examples on Bedrock: Anthropic Claude, Meta Llama, Amazon Titan Text

- **Foundation Models (FMs)**
  - Large pre-trained models adaptable to many downstream tasks
  - Trained on broad data; not specialized for one narrow task out of the box
  - Adaptation methods: prompting, fine-tuning, RAG, agents
  - Available as managed APIs (Bedrock) or for self-hosting (SageMaker JumpStart)
  - Distinction from traditional ML: one model serves many use cases vs. train-per-task

- **Multi-modal models**
  - Accept and/or produce more than one data type (text, image, audio, video)
  - Understand relationships across modalities (image + question → text answer)
  - Use cases: image captioning, visual Q&A, document analysis with charts, video summarization
  - Examples: Claude (vision), Amazon Titan Multimodal Embeddings, Stability AI image models on Bedrock

- **Diffusion models**
  - Generative models that learn to create data by reversing a noise-addition process
  - Start from random noise and iteratively denoise to produce output
  - Dominant approach for high-quality image and video generation
  - Text-to-image: prompt conditions the denoising process
  - AWS: Stability AI models (SDXL, etc.) available through Amazon Bedrock

### Identify potential use cases for GenAI models

- **Image generation**
  - Marketing creatives, product mockups, concept art, design prototypes
  - Personalized visuals for ads or user profiles
  - AWS: Stability AI on Bedrock, Amazon Titan Image Generator

- **Video generation**
  - Short promotional clips, storyboards, training content
  - Still emerging; often combines image models + animation pipelines

- **Audio generation**
  - Text-to-speech, voice cloning, music and sound effects
  - Podcast narration, accessibility, IVR voices
  - AWS: Amazon Polly (TTS), third-party models via Bedrock where available

- **Summarization**
  - Condense long documents, meeting transcripts, research papers, support tickets
  - Abstractive (rewrite in own words) vs. extractive (select key sentences)
  - AWS: Bedrock with Claude/Titan, Amazon Q Business

- **AI assistants**
  - Conversational helpers for employees or customers
  - Answer questions, draft content, explain policies, guide workflows
  - AWS: Amazon Q, Bedrock chat applications, custom apps with InvokeModel API

- **Translation**
  - Real-time and batch translation across languages
  - Can combine with GenAI for context-aware, nuanced translation
  - AWS: Amazon Translate (neural MT), Bedrock for idiomatic or domain-specific translation

- **Code generation**
  - Write, complete, explain, debug, and refactor code from natural language
  - Generate tests, documentation, and infrastructure-as-code
  - AWS: Amazon Q Developer, Bedrock with code-capable models, SageMaker for custom code models

- **Customer service agents**
  - Handle FAQs, order status, troubleshooting, escalation routing
  - Multi-turn conversation with access to knowledge bases and backend APIs
  - AWS: Amazon Lex + Bedrock, Bedrock Agents, Amazon Connect with Q

- **Search**
  - Semantic search over documents (meaning-based, not just keyword match)
  - Natural language queries over enterprise data
  - AWS: Amazon Kendra, Bedrock Knowledge Bases, OpenSearch vector search

- **Recommendation engines**
  - GenAI enhances descriptions, explanations, and conversational discovery
  - Generate personalized product summaries or "why we recommend this" text
  - Combine with Amazon Personalize for ranking + GenAI for narrative

### Describe the FM lifecycle

- **Data selection**
  - Identify datasets for pre-training, fine-tuning, or RAG grounding
  - Criteria: relevance, quality, diversity, licensing, privacy, bias risk
  - Remove PII, toxic content, and duplicates where possible
  - For RAG: curate authoritative, up-to-date source documents

- **Model selection**
  - Choose FM based on task, modality, latency, cost, context length, and compliance
  - Evaluate multiple models on representative prompts before committing
  - Consider: open vs. proprietary, region availability, customization support
  - AWS: compare models in Bedrock playground; JumpStart for self-hosted options

- **Pre-training**
  - Train FM from scratch on massive unlabeled data (typically done by model provider)
  - Learns language, reasoning, and world knowledge
  - Extremely expensive (compute, data, time); rarely done by individual organizations
  - Results in base model ready for prompting or further adaptation

- **Fine-tuning**
  - Further train FM on domain-specific labeled data to specialize behavior
  - Types: full fine-tuning, parameter-efficient (LoRA, adapters), continued pre-training
  - Improves performance on proprietary tasks, tone, format, or terminology
  - AWS: Bedrock model customization, SageMaker fine-tuning jobs

- **Evaluation**
  - Measure model quality before and after deployment
  - Automated metrics: BLEU, ROUGE, perplexity, benchmark scores
  - Human evaluation: relevance, fluency, safety, task success rate
  - Red-team testing for harmful, biased, or incorrect outputs
  - AWS: Bedrock model evaluation, SageMaker Clarify, custom eval pipelines

- **Deployment**
  - Serve model for production inference
  - Options: managed API (Bedrock), dedicated endpoints (provisioned throughput), self-hosted (SageMaker)
  - Integrate with applications via SDK, API Gateway, Lambda, agents
  - Apply guardrails, logging, and access controls at deployment boundary

- **Feedback**
  - Collect user ratings, corrections, and implicit signals (thumbs up/down, edits)
  - Use feedback for prompt refinement, RAG corpus updates, or retraining triggers
  - Close the loop: monitor → identify failures → improve data, prompts, or model → redeploy
  - Human-in-the-loop review for high-stakes outputs

### Describe the token-based pricing model and its effect on cost and performance

- **How token pricing works**
  - Charged per input tokens (prompt + context) and output tokens (generated response)
  - Different rates for input vs. output (output often costs more)
  - Pricing varies by model (larger/more capable models cost more per token)
  - Billed per API call based on actual token usage

- **Effect on cost**
  - Long system prompts, few-shot examples, and retrieved RAG context all increase input tokens
  - Verbose outputs (long summaries, detailed code) increase output tokens
  - High-traffic applications multiply token costs quickly
  - Mitigations: shorter prompts, concise output instructions, smaller models for simple tasks, caching

- **Effect on performance**
  - More tokens in context = longer processing time (higher latency)
  - Models have maximum context windows; exceeding limits truncates or fails
  - Larger context models may be slower per request
  - Batch vs. real-time: streaming reduces perceived latency for long outputs

- **Provisioned throughput (alternative pricing)**
  - Reserve model capacity for predictable, high-volume workloads
  - Fixed hourly cost regardless of token count (within capacity limits)
  - Better cost predictability at scale; avoids per-token spikes
  - Trade-off: pay for reserved capacity even during low usage
  - AWS: Amazon Bedrock provisioned throughput

- **Cost optimization strategies**
  - Right-size model: use smaller/cheaper models for simple classification or routing
  - Prompt caching (Bedrock): reuse repeated prompt prefixes at lower cost
  - Summarize or compress context before sending to model
  - Set max output tokens to cap response length
  - Monitor token usage with CloudWatch and cost allocation tags

### Describe the role of context engineering in FM applications

- **Definition**
  - Designing and managing all information the model sees at inference time
  - Broader than prompt engineering: includes system instructions, retrieved documents, conversation history, tool results, and metadata
  - Goal: give the model the right information to produce accurate, relevant, safe outputs

- **Components of context**
  - **System prompt**: role, rules, tone, output format, safety boundaries
  - **User prompt**: specific task or question
  - **Retrieved context**: relevant chunks from knowledge bases (RAG)
  - **Conversation history**: prior turns in a chat session
  - **Tool outputs**: results from API calls, database queries, code execution
  - **Structured metadata**: user profile, locale, permissions, session state

- **Context window management**
  - Total context must fit within model's token limit
  - Prioritize most relevant information when space is limited
  - Summarize older conversation turns to preserve history within budget
  - Truncate or rerank retrieved chunks by relevance score

- **Why it matters**
  - Poor context → hallucinations, irrelevant answers, ignored instructions
  - Good context → grounded, accurate, personalized responses without fine-tuning
  - Often higher ROI than fine-tuning for knowledge-heavy applications

- **AWS support**
  - Bedrock Knowledge Bases inject retrieved context automatically
  - Bedrock Agents manage tool results and orchestration context
  - Prompt management and versioning in Bedrock

### Define foundational agentic AI concepts

- **Agentic AI overview**
  - Systems that autonomously plan, use tools, and execute multi-step workflows to achieve goals
  - Goes beyond single prompt-response to iterative reasoning and action
  - Built on FMs with orchestration, memory, and tool integration layers

- **Multi-agent system patterns**
  - **Single agent**: one FM with tools handles entire workflow
  - **Supervisor pattern**: orchestrator agent delegates subtasks to specialist agents
  - **Collaborative pattern**: multiple agents discuss or vote on solutions
  - **Pipeline pattern**: agents pass outputs sequentially (research → draft → review)
  - Use when tasks are too complex for one agent or require specialized capabilities

- **Model Context Protocol (MCP)**
  - Open standard for connecting AI agents to external data sources and tools
  - Standardized interface so agents can discover and invoke capabilities consistently
  - Reduces custom integration code per data source
  - Enables agents to access databases, APIs, file systems, and SaaS apps through MCP servers
  - Supports interoperable agent ecosystems across tools and platforms

- **Multi-agent communication patterns**
  - **Message passing**: agents send structured messages to each other
  - **Shared memory**: agents read/write to a common state store (blackboard pattern)
  - **Handoff**: one agent transfers control and context to another
  - Requires clear protocols to avoid loops, conflicts, and context loss

- **Memory management**
  - **Short-term memory**: current conversation context within session
  - **Long-term memory**: persisted user preferences, facts, and past interactions
  - **Working memory**: intermediate reasoning steps and tool results during a task
  - Techniques: summarization, vector stores for episodic memory, session attributes
  - AWS: Bedrock Agents session state, DynamoDB, OpenSearch for long-term memory

- **Tool usage**
  - Agents invoke external functions: API calls, SQL queries, code execution, search
  - FM decides which tool to call and with what parameters (function calling / tool use)
  - Tool results are fed back into context for next reasoning step
  - AWS: Bedrock Agents action groups, Lambda functions, API Gateway integrations

- **Workflow orchestration**
  - Coordinate multi-step processes: plan → act → observe → repeat
  - ReAct pattern: Reason + Act in a loop until task is complete
  - Error handling: retry, fallback agents, human escalation
  - AWS: Bedrock Agents, Step Functions, Strands Agents, Bedrock AgentCore

## Task Statement 2.2: Understand the capabilities and limitations of GenAI for solving business problems.

### Describe the advantages of GenAI

- **Adaptability**
  - One FM handles many tasks via prompting without retraining
  - Quickly pivot to new use cases (summarize today, translate tomorrow)
  - Fine-tuning and RAG further adapt to domain-specific needs

- **Responsiveness**
  - Natural language interface lowers friction for users
  - Real-time conversational interaction
  - Streaming outputs improve perceived speed for long generations

- **Conversational capabilities**
  - Multi-turn dialogue with context retention
  - Clarifying questions, follow-ups, and iterative refinement
  - Supports chatbots, copilots, and virtual assistants

- **Ability to generate content**
  - Create text, code, images, and more from scratch
  - Draft emails, reports, marketing copy, documentation
  - Accelerates content production and creative workflows

- **Additional advantages**
  - Reduces need for large labeled datasets (compared to training custom ML from scratch)
  - Democratizes AI: business users can interact via natural language
  - Combines with existing systems via APIs, agents, and RAG
  - Rapid prototyping and time-to-market for AI features

### Identify disadvantages of GenAI solutions

- **Hallucinations**
  - Model generates plausible-sounding but factually incorrect information
  - Especially risky for medical, legal, financial, or factual Q&A use cases
  - Mitigations: RAG grounding, citations, confidence thresholds, human review

- **Interpretability**
  - Difficult to explain why a specific output was generated
  - Black-box reasoning; limited audit trail for individual token decisions
  - Problematic in regulated industries requiring explainable decisions

- **Inaccuracy**
  - Performance varies by domain, language, and prompt phrasing
  - May miss nuance, outdated knowledge (training cutoff), or domain-specific terminology
  - Requires ongoing evaluation and monitoring

- **Nondeterminism**
  - Same prompt can produce different outputs (controlled partly by temperature)
  - Makes testing and reproducibility harder
  - Set temperature to 0 for more deterministic outputs when needed

- **Additional limitations**
  - Context window limits how much information can be processed at once
  - Cost at scale: token pricing can become expensive for high-volume apps
  - Latency: large models may be too slow for real-time critical paths
  - Security risks: prompt injection, data leakage, harmful content generation
  - Bias and fairness concerns inherited from training data

### Identify factors to consider when selecting GenAI models

- **Model types**
  - Text-only vs. multi-modal (vision, audio)
  - General-purpose LLM vs. specialized (code, embedding, image generation)
  - Open-weight (Llama) vs. proprietary (Claude, Titan)

- **Performance requirements**
  - Accuracy and quality on your specific task (run benchmarks with your data)
  - Throughput: requests per second needed
  - Context length: how much input must the model handle?

- **Capabilities**
  - Function calling / tool use support
  - Fine-tuning and customization availability
  - Streaming, batch inference, embedding generation
  - Language and domain coverage

- **Constraints**
  - Deployment: managed API only vs. VPC-hosted vs. on-premises
  - Data residency: which regions is the model available in?
  - Must customer data leave your account/VPC?

- **Compliance**
  - Industry regulations (HIPAA, GDPR, PCI)
  - Model provider data handling policies (is prompt data used for training?)
  - Content safety and moderation requirements
  - AWS: Bedrock does not train on customer data by default; BAA available for eligible services

- **Cost**
  - Per-token pricing vs. provisioned throughput
  - Total cost at expected volume (input-heavy vs. output-heavy workloads)
  - Fine-tuning and hosting costs for custom models

- **Latency**
  - Time to first token (streaming) and total generation time
  - Model size vs. speed trade-off
  - Regional proximity: invoke model in same region as application

- **Model complexity**
  - Larger models: better quality but higher cost, latency, and ops burden
  - Smaller models: sufficient for routing, classification, or simple tasks
  - Consider model cascade: small model filters → large model for complex queries

### Determine business value and metrics for GenAI applications

- **Cross-domain performance**
  - Measure how well one GenAI solution performs across multiple business areas
  - Example: Amazon Q assisting HR, engineering, and sales with consistent quality
  - Track per-domain success rates and user satisfaction

- **Return on Investment (ROI)**
  - (Value gained − total cost) / total cost
  - Value: labor savings, revenue lift, error reduction, faster time-to-market
  - Cost: API fees, development, infrastructure, monitoring, human review

- **Efficiency**
  - Time saved per task (e.g., report drafting: 2 hours → 15 minutes)
  - Tickets deflected or resolved without human agent
  - Developer velocity: code completion acceptance rate, PR cycle time

- **Conversion rate**
  - Percentage of users who complete desired action after GenAI interaction
  - E-commerce: chatbot-assisted purchases vs. unassisted
  - A/B test GenAI features against control groups

- **Average Revenue Per User (ARPU)**
  - Revenue impact of GenAI-driven personalization or upsell
  - Higher engagement from AI recommendations or assistants

- **Accuracy**
  - Task-specific: correct answers, valid code, faithful summaries
  - Human evaluation scores, automated benchmark metrics
  - Error rate and hallucination rate in production

- **Customer Lifetime Value (CLV)**
  - Long-term revenue impact of improved customer experience via GenAI
  - Reduced churn from better support, faster resolution, personalization

- **Additional business metrics**
  - Net Promoter Score (NPS) and customer satisfaction (CSAT)
  - Employee productivity and adoption rates
  - Cost per interaction vs. human-handled baseline
  - Time to deploy new AI features (speed to market)

## Task Statement 2.3: Describe AWS infrastructure and technologies for building GenAI applications.

### Identify AWS services and features to develop GenAI applications

- **Amazon Bedrock**
  - Fully managed service to access FMs from multiple providers via unified API
  - Model choice: Claude, Llama, Titan, Mistral, Stability AI, Cohere, and more
  - Features: inference, fine-tuning (customization), Knowledge Bases (RAG), Agents, Guardrails
  - Provisioned throughput for dedicated capacity
  - Prompt management and model evaluation

- **Amazon SageMaker AI**
  - Full ML platform for training, fine-tuning, deploying, and monitoring models
  - Build custom GenAI pipelines with your own data and containers
  - Distributed training for large models; model hosting on GPU instances
  - MLOps: pipelines, model registry, monitoring, Clarify for bias

- **SageMaker JumpStart**
  - Pre-trained FMs and solutions ready to deploy with few clicks
  - Model hubs: Llama, Falcon, Stable Diffusion, and hundreds of models
  - Fine-tuning notebooks and deployment templates
  - Alternative to Bedrock when you need VPC-only hosting or custom infrastructure

- **Amazon Quick**
  - Generative BI: ask questions about data in natural language
  - Auto-generates visualizations, insights, and narratives from datasets
  - Lowers barrier for business users to explore data without SQL

- **Kiro**
  - AI-powered integrated development environment (IDE)
  - Assists developers with code generation, explanation, and application building
  - Accelerates development of GenAI-powered applications on AWS

- **Strands Agents**
  - Open-source SDK/framework for building AI agents
  - Simplifies tool integration, multi-step reasoning, and agent workflows
  - Works with Bedrock and other model providers
  - Use for custom agent logic beyond managed Bedrock Agents

- **Amazon Bedrock AgentCore**
  - Managed runtime for deploying and scaling AI agents in production
  - Handles infrastructure, security, and observability for agent workloads
  - Integrates with Bedrock models, tools, and enterprise systems
  - Supports long-running, stateful agent sessions at scale

- **Supporting services**
  - **Amazon Q**: generative AI assistant for business (Q Business) and developers (Q Developer)
  - **Amazon OpenSearch Serverless**: vector search for RAG
  - **AWS Lambda + API Gateway**: serverless GenAI application backends
  - **Amazon S3**: document storage for knowledge bases and training data

### Describe the advantages of using AWS GenAI services to build applications

- **Accessibility**
  - No ML PhD required: call APIs, use playgrounds, deploy pre-built solutions
  - Console, SDK, and no-code/low-code options (Bedrock Agents, Quick, Q)
  - JumpStart and Bedrock provide ready-to-use models

- **Lower barrier to entry**
  - Skip building and training FMs from scratch
  - Managed infrastructure handles GPUs, scaling, and patching
  - Start with prompting; add RAG, fine-tuning, or agents as needed

- **Efficiency**
  - Pre-integrated model catalog, vector stores, and agent frameworks
  - Reuse AWS security, networking, and IAM across AI and non-AI workloads
  - SageMaker Pipelines and Bedrock for repeatable workflows

- **Cost-effectiveness**
  - Pay-per-use token pricing for experimentation
  - No upfront GPU cluster investment
  - Provisioned throughput when per-token costs exceed reserved capacity economics
  - Spot instances and serverless options for training and inference

- **Speed to market**
  - Deploy GenAI features in days/weeks, not months
  - Bedrock Knowledge Bases and Agents accelerate RAG and tool-use patterns
  - Amazon Q and Quick provide turnkey business-user experiences

- **Ability to meet business objectives**
  - Broad model choice: pick best model per use case
  - Enterprise features: VPC, encryption, audit logging, guardrails
  - Global regions for low-latency and data residency compliance

### Describe the benefits of AWS infrastructure for GenAI applications

- **Security**
  - Data encrypted at rest (KMS) and in transit (TLS)
  - IAM policies control who can invoke models and access data
  - VPC endpoints keep traffic within AWS network (Bedrock, SageMaker)
  - Guardrails filter harmful content and enforce topic boundaries
  - No customer data used to train Bedrock base models by default

- **Compliance**
  - AWS complies with SOC, ISO, PCI, HIPAA (with BAA), FedRAMP, and more
  - Shared responsibility model: AWS secures infrastructure; customer secures data and access
  - CloudTrail logs API calls for audit
  - Model cards and documentation for governance

- **Responsibility (Shared Responsibility Model)**
  - **AWS responsible for**: hardware, hypervisor, managed service security, FM infrastructure
  - **Customer responsible for**: data classification, access controls, prompt safety, output validation, compliance of application logic
  - Understand where responsibility shifts for custom models vs. managed APIs

- **Safety**
  - Bedrock Guardrails: content filters, denied topics, PII redaction, word filters
  - Responsible AI tooling: bias detection (Clarify), human review workflows
  - Model evaluation and red-teaming before production
  - Throttling and quotas to prevent abuse

### Describe cost tradeoffs of AWS GenAI services

- **Responsiveness vs. cost**
  - Faster models or provisioned throughput cost more
  - Smaller models reduce latency and cost but may sacrifice quality
  - Streaming improves UX without reducing total tokens generated

- **Availability**
  - Multi-AZ deployments increase reliability but add infrastructure cost
  - On-demand Bedrock: AWS manages availability; no capacity planning
  - Self-hosted SageMaker endpoints: you pay for instance uptime regardless of usage

- **Redundancy**
  - Multi-region deployment for disaster recovery doubles or triples cost
  - Evaluate RTO/RPO requirements vs. budget
  - Bedrock regional endpoints vs. cross-region inference for resilience

- **Performance**
  - GPU instance types (p4d, p5) for self-hosted inference are expensive
  - Provisioned throughput guarantees performance but commits spend
  - Right-size: don't use Claude Opus for simple classification

- **Regional coverage**
  - Not all models available in all regions
  - Cross-region inference may add latency and data transfer costs
  - Deploy in region closest to users and data source

- **Token-based pricing**
  - Lowest barrier to start; costs scale linearly with usage
  - Unpredictable bills during traffic spikes
  - Optimize prompts and output length; use caching where available
  - Monitor with Cost Explorer and billing alarms

- **Provisioned throughput**
  - Predictable monthly cost for steady high-volume workloads
  - Cheaper than on-demand tokens above breakeven volume
  - Risk of over-provisioning unused capacity
  - Required for some SLA-sensitive production deployments

- **Custom models**
  - Fine-tuning incurs training compute costs (GPU hours)
  - Hosting custom fine-tuned models: dedicated endpoint costs
  - Worth it when prompting + RAG cannot meet quality bar
  - Intellectual property and data privacy benefits may justify premium
  - SageMaker JumpStart fine-tuning vs. Bedrock customization: compare pricing and ops burden

- **General cost optimization**
  - Model routing: cheap model for triage, expensive model for complex tasks
  - Batch inference for non-real-time workloads
  - SageMaker Serverless Inference or Lambda for spiky, low-volume traffic
  - S3 Intelligent-Tiering for large document corpora used in RAG
