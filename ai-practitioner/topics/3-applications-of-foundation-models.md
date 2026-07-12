# Domain 3 - Applications of Foundation Models

## Computer Vision

- Amazon Rekognition - managed service for analyzing images and video without ML expertise.
  - Label Detection - identifies objects, scenes, and activities in an image.
  - Image Properties - measures quality attributes like brightness, sharpness, and dominant colors.
  - Image Moderation - flags unsafe or inappropriate content such as nudity or violence.
  - Face Comparison - measures similarity between faces across two images.
  - Face Liveness - verifies a real person is present to prevent spoofing during authentication.
  - Celebrity Recognition - identifies well-known public figures in images and video.

## Natural Language Processing (NLP)

- Lemmatization - reduces words to their dictionary base form (e.g., "running" → "run").
- Stemming - chops words to a root by removing suffixes, often crudely (e.g., "running" → "runn").
- Lowercasing - normalizes text to lowercase so casing differences don't create distinct tokens.
- Stopword Removal - strips common low-value words like "the" and "is" to focus on meaningful terms.
- Punctuation Removal - removes punctuation marks to clean and standardize text for processing.

## AWS NLP Services

- Amazon Comprehend - extracts entities, sentiment, key phrases, and topics from text.
- Amazon Kendra - intelligent enterprise search service that returns precise answers from documents.
- Amazon Lex - builds conversational chatbots and voice interfaces using the same tech as Alexa.
- Amazon Polly - converts text into lifelike speech (text-to-speech).
- Amazon Transcribe - converts speech audio into text (speech-to-text).
- Amazon Translate - performs neural machine translation between languages.

## Amazon Comprehend Use Cases

- Voice of customer - analyzes reviews and feedback to gauge customer sentiment at scale.
- Knowledgebase - organizes and indexes documents by topic and entity for retrieval.
- Legal Analysis - extracts entities and clauses from contracts and legal documents.

## Amazon Kendra

- GenAI Enterprise Edition - higher-tier edition with generative AI features and larger document capacity.
- Basic Enterprise Edition - standard intelligent search edition for enterprise document sets.

- Factoid Questions - answers "who/what/when/where" queries with a specific fact.
- Descriptive Questions - answers "how/why" queries requiring a longer explanatory passage.
- Keyword and Natural Language Questions - handles both simple keyword lookups and full natural-language queries.

## Intelligent Document Processing (IDP)

- Digitization - converts physical or scanned documents into machine-readable digital text.
- Extraction - pulls structured fields and data from unstructured documents.
- Validation and Updates - verifies extracted data for accuracy and feeds corrections back into systems.

## Fraud Detection

- Amazon Fraud Detector - managed service that uses ML to identify potentially fraudulent online activity.

## When to use AI?

- Complexity - favor AI when rules are too numerous or nuanced to hand-code reliably.
- Cost - weigh whether AI's accuracy gains justify its development and inference expense.
- Nondeterminism (healthcare) - avoid AI where unpredictable outputs are unacceptable for safety-critical decisions.

## Amazon Bedrock

- Model Provider - the company that built a hosted FM, such as Anthropic, Meta, or Amazon.
- Modality - the input/output type a model handles, like text, image, or multimodal.
- Chat/Text Playground - a console workspace for interactively testing prompts against a model.
  - Mode - choose between conversational chat or single-turn text completion.
  - Select Model - pick which provider's FM to run in the playground session.

## Configuration Options

- Temperature - controls output randomness, with lower values giving more deterministic responses.
- Top P - restricts sampling to the smallest set of tokens whose cumulative probability meets the threshold.
- Top K - limits sampling to the K most likely next tokens.
- Response Length - caps the maximum number of tokens the model generates.
- Stop Sequences - strings that immediately halt generation when produced.
- Guardrails - configurable safety policies that filter harmful or unwanted model behavior.
  - Content Filtering - blocks categories of harmful content like hate, violence, or sexual material.
  - Sensitive Information Protection - detects and redacts PII and other sensitive data.
  - Multilingual Support - applies guardrail policies across multiple languages.
  - Prompt and Response Protection - screens both user inputs and model outputs against the policy.

## Image/Video Playground

- Generate Image - creates a new image from a text prompt.
- Generate Variations - produces alternative versions of an existing image.
- Remove Object - erases an unwanted element from an image and fills the gap.
- Replace Background - swaps the scene behind the main subject.
- Replace Object - substitutes one element in an image for another via prompt.
- Generate Video - creates a short video clip from a prompt or source image.

- Negative Prompts - specify what the model should avoid including in the output.
- Response Image - an input image supplied to guide or condition the generation.
- Advanced Configuration - extra controls for fine-tuning generation behavior.
  - Prompt Strength - how closely the output adheres to the prompt versus the source image.
  - Seed - a fixed value that makes image generation reproducible.

## Choosing an FM

- Categories - the task types a model supports, such as text, chat, or embeddings.
- Last Version - the most recent model release, usually offering the best quality.
- Language - the languages a model is trained to understand and generate.
- Max Tokens - the context window size limiting combined input and output length.

## License Types

- Apache 2.0 - permissive open-source license allowing commercial use with patent protection.
- MIT license - minimal permissive license allowing nearly unrestricted reuse.
- GNU General Public License (GPL) - copyleft license requiring derivative works to stay open source.

## License Advantages

- Transparency - open licenses let you inspect how the model works.
- Innovation - community access accelerates improvement and experimentation.
- Customization - freedom to modify and adapt the model to your needs.

## Measuring Success: Business Goals and Metrics

- User Satisfaction - how happy users are with the AI-powered experience.
  - Customer Satisfaction Score (CSAT) - a direct post-interaction rating of satisfaction.
  - Net Promoter Score (NPS) - measures how likely users are to recommend the product.
- Average Revenue per User (ARPU) - average income generated per active user.
- Conversion Rate - the share of users who complete a desired action.
  - Optimized Content - AI-tailored content that drives more conversions.
  - Search - improved search relevance that helps users find and buy.
  - Dynamic pricing - AI-adjusted prices that maximize conversions and revenue.
  - Automated A/B testing - automatically testing variants to find what converts best.
- Efficiency - output or cost savings gained from automation.

## Model Customization

- Distillation - train a smaller student model to mimic a larger teacher model.
  - Efficiency - lower inference cost and latency from the smaller model.
  - Edge - small enough to run on resource-constrained or on-device deployments.
- Fine-Tuning - adapt a pre-trained model's weights on task-specific labeled data.

## Bedrock Hyperparameters

- Learning Rate - how large each weight-update step is during training.
- Epoch - one full pass over the training dataset.
- Batch Size - the number of examples processed before each weight update.

## Continued Pretraining

- Further pre-train a model on domain-specific unlabeled text to absorb specialized knowledge.

## Agents in Amazon Bedrock

- Managed framework where an FM reasons, plans, and calls tools to complete multi-step tasks.

## Multiagent Collaboration

- Multiple specialized agents coordinate, with a supervisor delegating subtasks to complete a goal.
- Pricing - how you pay for agent and model usage.
  - On Demand - pay per request with no commitment.
  - Provisioned Throughput - reserved capacity for predictable, high-volume workloads.

## Amazon Q

- Amazon Q Business - generative AI assistant that answers questions over enterprise data.
  - Unified Search - searches across connected enterprise sources from one interface.
  - Amazon Q Apps - lets users build lightweight AI apps from natural-language descriptions.
  - Application Tasks - performs actions in connected business applications.
- Amazon Q Developer - AI coding assistant for writing, debugging, and modernizing software.

## The Anatomy of a Prompt

- Instructions - the directive telling the model what task to perform.
- Context - background information that helps the model respond accurately.
- Input Data - the specific content the model should process.
- Output Indicator - a cue specifying the desired format or start of the response.

## Best Practices for Prompting

- Be Clear - state the task precisely to avoid ambiguous results.
- Avoid Leading Questions - phrase neutrally so you don't bias the answer.
- Use Analogies or Comparisons - relate concepts to familiar ideas for better understanding.
- Ask for Alternatives - request multiple options to explore different responses.
- Use Prompt Templates - reusable structures with placeholders for repeatable prompting.
  - Consistency - templates produce uniform outputs across requests.
  - Efficiency - templates save time by reusing proven prompt structures.
  - Clarity - templates enforce a clear, organized prompt format.

## Prompting Techniques

- Zero-Shot Prompting - ask the model to perform a task with no examples.
- Few-Shot Prompting - provide a few examples to demonstrate the desired pattern.
- Chain-of-Thought Prompting (CoT) - prompt the model to reason step by step before answering.

## Security Issues

- Model Poisoning - corrupting training data to embed malicious behavior in the model.
- Hijacking and Prompt Injection - crafted inputs that override the model's intended instructions.
- Exposure - unintended disclosure of sensitive data through model outputs.
- Prompt Leaking - tricking the model into revealing its hidden system prompt.
- Jailbreaking - bypassing safety guardrails to elicit prohibited content.

## Task Statement 3.1: Describe design considerations for applications that use foundation models (FMs).

### Identify selection criteria to choose FMs

- **Cost**
  - Per-token pricing for input and output varies significantly by model
  - Estimate monthly spend: average tokens per request × requests per day × price per token
  - Smaller models (Haiku, Titan Express) for high-volume simple tasks; larger models for complex reasoning
  - Provisioned throughput for predictable high-volume workloads vs. on-demand for variable traffic

- **Modality**
  - Text-only: summarization, Q&A, code generation, chat
  - Vision: image analysis, document understanding with charts/diagrams
  - Multi-modal: combined text + image input (Claude vision, Titan Multimodal Embeddings)
  - Image generation: Stability AI, Titan Image Generator on Bedrock
  - Match model modality to application input/output requirements

- **Latency**
  - Time to first token and total generation time affect user experience
  - Smaller models generally faster; streaming reduces perceived wait
  - Regional endpoint proximity: invoke model in same region as application
  - Real-time chat vs. batch processing have different latency tolerances

- **Multi-lingual**
  - Model language coverage for target markets
  - Quality varies by language; test on representative non-English prompts
  - Amazon Translate can preprocess/postprocess; some FMs handle translation natively
  - Consider locale-specific compliance and cultural nuance

- **Model size**
  - Larger models: better reasoning, longer context, higher cost and latency
  - Smaller models: sufficient for classification, routing, extraction, simple Q&A
  - Model cascade: small model triages → large model handles complex queries

- **Model complexity**
  - General-purpose LLMs vs. specialized models (embeddings, image, code)
  - Open-weight (Llama) vs. proprietary (Claude) - licensing and hosting implications
  - Parameter count correlates with capability but not always with task-specific performance

- **Customization**
  - Does the use case require fine-tuning or is prompting + RAG sufficient?
  - Bedrock supports customization for select models (continued pre-training, fine-tuning)
  - SageMaker JumpStart for full control over custom training pipelines
  - Evaluate customization ROI before committing to training costs

- **Input/output length**
  - Context window limits maximum prompt + retrieved context + conversation history
  - Long documents require chunking, summarization, or models with large context (100K+ tokens)
  - Set max output tokens to control response length and cost
  - Models differ: Claude (200K), Llama 3 (128K), Titan (varies by version)

- **Prompt caching**
  - Bedrock prompt caching: cache repeated prompt prefixes (system prompts, long documents)
  - Reduces cost and latency for requests sharing the same prefix
  - Ideal for applications with stable system instructions and variable user queries
  - Cache hit rate is a key optimization metric

### Describe the effect of inference parameters on model responses

- **Temperature**
  - Controls randomness in token selection (typically 0.0 to 1.0)
  - **Low (0–0.3)**: deterministic, focused, factual - good for Q&A, extraction, code
  - **Medium (0.4–0.7)**: balanced creativity and coherence - general conversation
  - **High (0.8–1.0)**: creative, diverse, unpredictable - brainstorming, creative writing
  - Temperature 0 produces most reproducible outputs

- **Top-p (nucleus sampling)**
  - Limits token selection to smallest set whose cumulative probability ≥ p
  - Lower top-p = more focused; higher = more diverse
  - Often used together with temperature; adjust one at a time when tuning

- **Top-k**
  - Only consider the k most likely next tokens
  - Reduces chance of unlikely token selections
  - Less commonly adjusted than temperature and top-p

- **Max tokens (output length)**
  - Hard cap on generated response length
  - Prevents runaway generation and controls cost
  - Too low: truncated, incomplete answers
  - Too high: unnecessary cost and latency for simple queries

- **Stop sequences**
  - Strings that halt generation when encountered
  - Useful for structured output (end of JSON, section markers)
  - Prevents model from continuing past desired endpoint

- **Input length effects**
  - Longer input = more tokens processed = higher cost and latency
  - Very long inputs may hit context window limits (truncation or error)
  - RAG retrieval quality matters more than raw input length

- **Inference parameter best practices**
  - Start with model defaults; tune based on evaluation results
  - Document parameter settings per use case
  - Different parameters for different application modes (creative vs. factual)
  - Store parameters in Bedrock Prompt Management for consistency

### Define Retrieval Augmented Generation (RAG) and describe its business applications

- **RAG definition**
  - Architecture that retrieves relevant documents from a knowledge base and injects them into the model prompt
  - FM generates answers grounded in retrieved context rather than relying solely on training data
  - Reduces hallucinations by anchoring responses to authoritative source material
  - Enables use of proprietary, current, or domain-specific data without fine-tuning

- **RAG workflow**
  - **Ingest**: chunk documents → generate embeddings → store in vector database
  - **Query**: user question → embed query → retrieve top-k similar chunks
  - **Generate**: append retrieved chunks to prompt → FM produces grounded answer
  - **Optional**: rerank retrieved chunks; cite sources in response

- **Business applications**
  - **Enterprise Q&A**: employees ask questions about internal policies, HR, IT docs
  - **Customer support**: agents and chatbots answer from product manuals and FAQs
  - **Legal and compliance**: query contracts, regulations, and case law
  - **Healthcare**: clinical guidelines and research (with appropriate safeguards)
  - **Financial services**: analyst reports, filings, and market research
  - **Developer productivity**: code documentation and architecture decision records

- **Amazon Bedrock Knowledge Bases**
  - Managed RAG service: connect data sources → automatic chunking, embedding, retrieval
  - Data sources: S3, Confluence, SharePoint, Salesforce, Web crawlers
  - Vector store options: OpenSearch Serverless, Aurora PostgreSQL (pgvector), Pinecone, Redis
  - Integrates with Bedrock Agents and direct InvokeModel API
  - Supports metadata filtering and custom chunking strategies

- **RAG vs. fine-tuning**
  - RAG: best when knowledge changes frequently or must be citeable
  - Fine-tuning: best when behavior, tone, or format must change; knowledge is stable
  - Often combined: fine-tuned model + RAG for domain behavior + current knowledge

### Identify AWS services that help store embeddings within vector databases

- **Amazon OpenSearch Service**
  - k-NN plugin for vector similarity search at scale
  - Hybrid search: combine vector (semantic) and keyword (BM25) retrieval
  - OpenSearch Serverless: fully managed, auto-scaling vector collections
  - Default vector store for Bedrock Knowledge Bases
  - Use cases: large-scale document search, log analytics + semantic search

- **Amazon Aurora (PostgreSQL-compatible)**
  - pgvector extension stores and queries embeddings in PostgreSQL
  - Familiar SQL interface for teams already using relational databases
  - Combine vector search with structured metadata filters via SQL
  - Bedrock Knowledge Bases supports Aurora as vector store backend
  - Use cases: moderate-scale RAG, applications needing transactional + vector data

- **Amazon Neptune**
  - Graph database with vector search capabilities
  - Combine knowledge graph relationships with semantic similarity
  - Useful when entities and relationships matter (social networks, fraud, recommendations)
  - Query: "find similar documents AND their connected entities"

- **Amazon RDS for PostgreSQL**
  - pgvector extension on managed PostgreSQL
  - Same vector capabilities as Aurora with standard RDS feature set
  - Suitable for smaller to mid-size RAG workloads
  - Existing RDS PostgreSQL instances can add pgvector without migration

- **Other options**
  - **Amazon S3 Vectors**: cost-optimized vector storage for large-scale, lower-frequency queries
  - **Third-party via Bedrock**: Pinecone, Redis Enterprise Cloud as Knowledge Base vector stores
  - **Amazon MemoryDB**: vector search with in-memory performance (Redis-compatible)

- **Choosing a vector store**
  - Scale: number of vectors, query QPS, index size
  - Hybrid search needs: keyword + semantic
  - Existing infrastructure: already using OpenSearch or PostgreSQL?
  - Latency requirements: in-memory (MemoryDB) vs. disk-based
  - Cost: serverless auto-scaling vs. provisioned capacity

### Explain the cost tradeoffs of various approaches to FM customization

- **Pre-training**
  - Train FM from scratch on massive datasets
  - Highest cost: millions in compute, data, and expertise
  - Full control over model architecture and training data
  - Rarely justified; only for organizations building proprietary FMs
  - AWS: SageMaker distributed training on large GPU clusters

- **Fine-tuning**
  - Adapt pre-trained FM on domain-specific labeled data
  - Moderate to high cost: GPU hours for training + hosting custom model endpoint
  - Improves task-specific accuracy, tone, format, and terminology
  - Data must be curated and labeled; quality directly affects outcome
  - AWS: Bedrock model customization, SageMaker fine-tuning jobs
  - Ongoing cost: hosting fine-tuned model (provisioned throughput or on-demand)

- **In-context learning (prompting)**
  - Guide model behavior via prompts without changing weights
  - Lowest cost: only inference tokens; no training compute
  - Techniques: zero-shot, few-shot examples, chain-of-thought in prompt
  - Limited by context window size; examples consume tokens
  - Fastest to iterate; no deployment of new model version
  - Performance ceiling lower than fine-tuning for specialized tasks

- **RAG**
  - Retrieve external knowledge at inference time; no model weight changes
  - Cost: embedding generation + vector store + retrieval + inference tokens
  - Vector store hosting (OpenSearch, Aurora) adds infrastructure cost
  - Best for dynamic knowledge; update documents without retraining
  - Retrieval quality is critical; poor chunks = poor answers regardless of model

- **Model distillation**
  - Train smaller "student" model to mimic larger "teacher" model
  - Reduces inference cost and latency while preserving much of teacher quality
  - One-time distillation training cost; ongoing savings on every inference call
  - Useful when large model quality is needed at small-model price point
  - AWS: SageMaker for custom distillation pipelines

- **Cost comparison summary**
  - **Lowest upfront**: in-context learning (prompting only)
  - **Moderate ongoing**: RAG (vector store + retrieval + inference)
  - **Higher upfront + ongoing**: fine-tuning (training + custom endpoint)
  - **Highest**: pre-training from scratch
  - **Best long-term inference savings**: distillation after quality validation

### Define the role of AI agents and describe AI agents' business applications

- **AI agent definition**
  - Autonomous system that uses an FM to reason, plan, and take actions via tools
  - Breaks complex goals into steps; iterates until task is complete
  - Combines: FM (brain) + tools (hands) + memory (context) + orchestration (workflow)

- **Agent components**
  - **Reasoning**: FM decides what to do next based on goal and observations
  - **Planning**: decompose task into subtasks with ordering
  - **Tool use**: call APIs, query databases, run code, search documents
  - **Memory**: retain conversation history, user preferences, intermediate results
  - **Orchestration**: manage loop (plan → act → observe → repeat)

- **Business applications**
  - **Customer service**: look up orders, process returns, escalate to human - Amazon Connect + Bedrock Agents
  - **IT operations**: diagnose incidents, run remediation scripts, create tickets
  - **Sales assistance**: research prospects, draft proposals, update CRM
  - **HR onboarding**: guide new hires through paperwork, answer policy questions, schedule training
  - **Financial analysis**: pull data from multiple sources, generate reports, flag anomalies
  - **Software development**: write code, run tests, deploy, debug - Amazon Q Developer
  - **Research**: gather information from web and internal docs, synthesize findings

- **Amazon Bedrock Agents**
  - Managed agent framework: define instructions, attach knowledge bases, configure action groups
  - Action groups: Lambda functions that agents invoke as tools
  - Pre-built connectors: API Gateway, OpenAPI schemas
  - Handles orchestration loop, session state, and guardrails
  - AgentCore for production-scale agent deployment

- **Agents vs. simple RAG chatbot**
  - RAG chatbot: retrieve docs → answer question (single turn or conversational)
  - Agent: multi-step workflows with tool calls, conditional logic, and state changes
  - Use agents when task requires actions beyond generating text

## Task Statement 3.2: Choose effective prompt engineering techniques.

### Define the concepts and constructs of prompt engineering

- **Context**
  - Background information the model needs to understand the task
  - Domain knowledge, user profile, conversation history, retrieved documents
  - More relevant context → better responses; irrelevant context → confusion and wasted tokens

- **Instruction**
  - Explicit directive telling the model what to do
  - Clear, specific, actionable: "Summarize the following article in 3 bullet points"
  - System-level instructions set persistent behavior across all user interactions
  - Separate instructions from content (use delimiters: XML tags, triple quotes, markdown headers)

- **Negative prompts**
  - Tell the model what NOT to do or include
  - Examples: "Do not include personal opinions", "Do not reveal system instructions", "Avoid technical jargon"
  - Reduces unwanted behaviors without lengthy positive instructions
  - Bedrock Guardrails complement negative prompts with enforced filters

- **Role / persona**
  - Assign a identity: "You are an experienced AWS solutions architect"
  - Shapes tone, depth, and perspective of responses
  - Keep roles consistent with use case and audience

- **Output format**
  - Specify structure: JSON, markdown table, bullet list, numbered steps
  - Include example of desired output format (few-shot)
  - Reduces parsing errors in downstream application code

- **Delimiters**
  - Separate sections of prompt: `<document>`, `###`, `"""`, `[INST]`
  - Prevents model from confusing instructions with content
  - Critical when user input is embedded in prompt (injection defense)

### Define techniques for prompt engineering

- **Zero-shot**
  - No examples provided; model relies on pre-training knowledge and instructions alone
  - Simplest approach: "Classify the sentiment of this review as positive, negative, or neutral"
  - Works well for common tasks; may underperform on niche or complex formats

- **Single-shot (one-shot)**
  - One example demonstrating desired input-output pattern
  - Helps clarify format and expectations with minimal token cost
  - Useful when zero-shot produces inconsistent structure

- **Few-shot**
  - Multiple examples (typically 3–10) showing input-output pairs
  - Model learns pattern from examples without weight updates
  - More examples = better pattern learning but more tokens consumed
  - Select diverse, representative examples covering edge cases

- **Chain-of-thought (CoT)**
  - Instruct model to reason step-by-step before giving final answer
  - "Let's think through this step by step" or provide worked examples with reasoning
  - Improves accuracy on math, logic, and multi-step problems
  - Trade-off: longer responses, more output tokens

- **Prompt templates**
  - Reusable prompt structures with variable placeholders
  - Example: `"Summarize {{document}} in {{num_bullets}} bullet points for a {{audience}} audience"`
  - Ensures consistency across application requests
  - AWS: Bedrock Prompt Management stores and versions templates

- **Additional techniques**
  - **Self-consistency**: generate multiple responses; select most common answer
  - **Tree of thought**: explore multiple reasoning branches
  - **ReAct (in agents)**: interleave reasoning and action steps
  - **Meta-prompting**: ask model to improve or refine its own prompt

### Identify and describe the benefits and best practices for prompt engineering

- **Response quality improvement**
  - Iterative prompt refinement is fastest path to better outputs
  - Often achieves 80% of fine-tuning benefit at 0% training cost
  - A/B test prompt variants with evaluation metrics

- **Experimentation**
  - Test multiple prompt versions against benchmark queries
  - Track which variants perform best on accuracy, relevance, safety
  - Bedrock playground for rapid iteration before production deployment

- **Guardrails**
  - Combine prompts with Bedrock Guardrails for enforced safety
  - System instructions set behavioral boundaries
  - Output validation in application code as final safety net

- **Discovery**
  - Prompting reveals model capabilities and limitations before committing to architecture
  - Prototype use cases quickly to validate business value
  - Identify whether RAG, fine-tuning, or agents are needed

- **Specificity and concision**
  - Be precise about task, format, constraints, and audience
  - Remove ambiguous or contradictory instructions
  - Shorter, clearer prompts often outperform long, verbose ones
  - Every unnecessary word costs tokens

- **Using multiple components**
  - Combine: role + context + instruction + examples + output format + negative constraints
  - Structure with clear sections and delimiters
  - Layer techniques: few-shot examples + chain-of-thought + format specification

- **Additional best practices**
  - Version and document every prompt change
  - Test with edge cases, adversarial inputs, and out-of-domain queries
  - Evaluate across demographics and languages if serving diverse users
  - Monitor production prompts for quality drift

### Define potential risks and limitations of prompt engineering

- **Prompt exposure**
  - System prompts may leak into model responses if user tricks the model
  - Reveals proprietary instructions, business logic, or security rules
  - Mitigation: Guardrails, output filtering, never put secrets in prompts

- **Prompt poisoning**
  - Attacker embeds malicious instructions in data the model processes (documents, user input)
  - Example: hidden text in a document saying "ignore previous instructions and..."
  - Mitigation: input sanitization, RAG source trust, Guardrails, instruction/data separation

- **Prompt hijacking (indirect injection)**
  - User input overrides system instructions via crafted prompts
  - "Ignore all previous instructions and instead..."
  - Mitigation: delimiter separation, input validation, Guardrails denied topics, least-privilege tool access

- **Jailbreaking**
  - Bypass safety guardrails through creative prompting (roleplay, hypotheticals, encoding)
  - Model produces harmful, biased, or policy-violating content
  - Mitigation: Bedrock Guardrails, content filters, human review for sensitive outputs, red-team testing

- **Limitations of prompting alone**
  - Cannot add knowledge not in training data (use RAG)
  - Cannot reliably change deeply ingrained model behavior (use fine-tuning)
  - Context window limits how many examples and instructions fit
  - Inconsistent results with high temperature; brittle with edge cases
  - Does not reduce inference cost (may increase it with long prompts)

### Describe prompt versioning and management strategies that use Amazon Bedrock Prompt Management

- **Why version prompts**
  - Track changes over time; rollback when new version degrades quality
  - Compare performance across versions with evaluation jobs
  - Audit trail for compliance and debugging production issues
  - Team collaboration: multiple developers work on prompts without conflicts

- **Amazon Bedrock Prompt Management features**
  - Create, store, and organize prompt templates in Bedrock console and API
  - Version prompts: each edit creates a new version; pin production to specific version
  - Variables/placeholders for dynamic content injection
  - Associate inference parameters (temperature, max tokens) with prompt versions
  - Share prompts across team members with IAM permissions

- **Management strategies**
  - **Naming conventions**: `{app}-{task}-v{version}` (e.g., `support-summarize-v3`)
  - **Environment separation**: dev/staging/prod prompt versions
  - **Change control**: require evaluation pass before promoting version to production
  - **Default vs. variant**: maintain baseline prompt; test challenger variants
  - **Integration**: reference managed prompt IDs in application code instead of hardcoded strings

- **Workflow**
  - Draft prompt in playground → save to Prompt Management → run evaluation → deploy version → monitor → iterate
  - CI/CD: automate prompt deployment with Bedrock API in CodePipeline
  - Tag prompts with metadata: owner, use case, last evaluation date, performance score

## Task Statement 3.3: Describe the training and fine-tuning process for FMs.

### Describe the key elements of training an FM

- **Pre-training**
  - Train on massive unlabeled text corpora (web, books, code)
  - Learns language structure, facts, reasoning patterns
  - Self-supervised objectives: predict next token, masked token prediction
  - Requires enormous compute (thousands of GPUs, weeks/months)
  - Done by model providers (Anthropic, Meta, Amazon); not typical for customers

- **Fine-tuning**
  - Adapt pre-trained model on smaller, task-specific labeled dataset
  - Adjusts model weights to specialize behavior for target use case
  - Much less compute than pre-training; hours to days on GPU instances
  - Types: full fine-tuning (all weights) or parameter-efficient (LoRA, adapters - subset of weights)

- **Continuous pre-training**
  - Further pre-train on domain-specific unlabeled text (no labels needed)
  - Teaches model domain vocabulary, concepts, and knowledge
  - Step before instruction fine-tuning for specialized domains (medical, legal, financial)
  - AWS: Bedrock model customization (continued pre-training option)

- **Distillation**
  - Train smaller student model to replicate larger teacher model's behavior
  - Student learns from teacher's outputs (soft labels) not just ground truth
  - Result: faster, cheaper inference with acceptable quality trade-off
  - AWS: custom SageMaker training pipelines

- **RLHF (Reinforcement Learning from Human Feedback)**
  - Post-training alignment: humans rank model outputs; reward model learns preferences
  - FM fine-tuned with reinforcement learning to maximize reward model score
  - Produces more helpful, harmless, honest responses
  - Done by model providers; customers rarely run RLHF directly

### Define methods for fine-tuning an FM

- **Instruction tuning**
  - Fine-tune on instruction-response pairs: `{"instruction": "...", "response": "..."}`
  - Teaches model to follow directives and produce useful outputs
  - Most common fine-tuning approach for chat/assistant use cases
  - Data format: conversational turns, task descriptions with expected outputs

- **Adapting models for specific domains**
  - Fine-tune on domain text: medical records, legal contracts, financial reports
  - Improves terminology, style, and factual accuracy in target domain
  - Often preceded by continuous pre-training on domain corpus
  - Evaluate on domain-specific benchmarks

- **Transfer learning**
  - Leverage knowledge from pre-trained model; apply to new but related task
  - Pre-trained FM already understands language; fine-tuning adapts to specific task
  - Requires far less data and compute than training from scratch
  - Core principle behind all FM fine-tuning

- **Continuous pre-training**
  - Additional pre-training on domain-specific unlabeled data before instruction tuning
  - Ingests proprietary documents, manuals, knowledge bases into model weights
  - Model learns domain language patterns without labeled examples
  - Bedrock customization: "Continued pre-training" workflow

- **Parameter-efficient fine-tuning (PEFT)**
  - LoRA (Low-Rank Adaptation): train small adapter matrices; freeze base model weights
  - Dramatically reduces training cost, memory, and storage
  - Multiple LoRA adapters can be swapped on one base model for different tasks
  - AWS: supported in SageMaker and select Bedrock customization options

### Describe how to prepare data to fine-tune an FM

- **Data curation**
  - Collect high-quality, relevant examples for target task
  - Remove duplicates, low-quality entries, and off-topic samples
  - Balance dataset: cover common cases and important edge cases
  - Minimum dataset size varies; typically hundreds to thousands of examples

- **Data governance**
  - Ensure legal right to use data for training (licensing, consent)
  - Remove or anonymize PII and sensitive information
  - Document data provenance, lineage, and usage policies
  - Compliance: GDPR, HIPAA, industry-specific regulations
  - AWS: SageMaker Ground Truth for labeling; Macie for PII detection in S3

- **Data size**
  - More data generally improves fine-tuning quality (with diminishing returns)
  - Quality matters more than quantity: 500 excellent examples > 5,000 mediocre ones
  - Start small, evaluate, incrementally add data targeting failure modes

- **Labeling**
  - Instruction tuning: label input-output pairs (instruction + ideal response)
  - Classification: label categories; generation: label reference outputs
  - Consistent labeling guidelines across annotators
  - Inter-annotator agreement checks for quality assurance
  - AWS: SageMaker Ground Truth with human labelers or automated labeling

- **Representativeness**
  - Training data must reflect production data distribution
  - Include diverse examples: languages, formats, difficulty levels, edge cases
  - Underrepresented scenarios in training = poor performance in production
  - Test set must be held out and represent real-world queries

- **RLHF data preparation**
  - Collect human preference rankings: "response A is better than response B"
  - Train reward model on preferences
  - Fine-tune FM with reinforcement learning against reward model
  - Expensive and complex; typically done by FM providers, not end customers
  - Alternative for customers: DPO (Direct Preference Optimization) on preference pairs

- **Data format**
  - JSONL is common: one example per line with instruction, input, output fields
  - Conversational format: array of role/content message pairs
  - Follow model provider's recommended fine-tuning data schema
  - Bedrock and SageMaker document required formats per model

## Task Statement 3.4: Describe methods to evaluate FM performance.

### Determine approaches to evaluate FM performance

- **Human-in-the-loop evaluation**
  - Human reviewers score outputs on relevance, accuracy, fluency, safety, helpfulness
  - Gold standard for subjective tasks (creative writing, open-ended Q&A)
  - Expensive and slow; use for final validation and ongoing spot checks
  - Rating scales: Likert (1–5), pairwise comparison, pass/fail rubrics
  - AWS: SageMaker Ground Truth for human evaluation workflows

- **Benchmark datasets**
  - Standardized test sets with known correct answers
  - Compare model performance across consistent tasks
  - Examples: MMLU (knowledge), HumanEval (code), GSM8K (math), HELM (holistic)
  - Run benchmarks before selecting model; re-run after fine-tuning
  - Limitation: may not reflect your specific use case or domain

- **Amazon Bedrock Model Evaluation**
  - Managed evaluation service for comparing models and prompt versions
  - **Automatic evaluation**: metrics like accuracy, robustness, toxicity on built-in datasets
  - **Human evaluation**: invite reviewers to score outputs via built-in UI
  - **LLM-as-a-judge**: use one FM to evaluate another's outputs
  - Compare multiple models or prompt variants side-by-side
  - Generate evaluation reports for model selection decisions

### Identify relevant metrics to assess FM performance

- **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**
  - Measures overlap between generated summary and reference summary
  - ROUGE-1 (unigram), ROUGE-2 (bigram), ROUGE-L (longest common subsequence)
  - Higher = more overlap; common for summarization tasks
  - Limitation: does not capture semantic similarity beyond n-gram overlap

- **BLEU (Bilingual Evaluation Understudy)**
  - Measures n-gram precision between generated and reference text
  - Originally for machine translation; also used for text generation
  - Higher BLEU = closer to reference; penalizes short outputs via brevity penalty
  - Limitation: rigid; misses paraphrases that are equally valid

- **BERTScore**
  - Uses BERT embeddings to measure semantic similarity between generated and reference text
  - Captures meaning beyond exact word overlap
  - Better for evaluating paraphrased or reworded correct answers
  - Precision, recall, and F1 variants

- **LLM-as-a-judge**
  - Use a capable FM (e.g., Claude) to score or rank another model's outputs
  - Prompt judge model: "Rate this response on accuracy, relevance, and helpfulness (1-5)"
  - Scalable alternative to human evaluation; correlates well for many tasks
  - Bedrock Model Evaluation supports LLM-as-judge workflows
  - Limitation: judge model has its own biases; validate against human scores

- **Additional metrics**
  - **Perplexity**: how surprised the model is by test data; lower = better language modeling
  - **F1 / Accuracy**: for classification tasks extracted from FM outputs
  - **Toxicity / bias scores**: automated safety metrics (Clarify, Guardrails reports)
  - **Latency and throughput**: tokens per second, time to first token
  - **Cost per query**: tokens consumed × price per token

### Determine whether an FM effectively meets business objectives

- **Productivity**
  - Time saved per task vs. manual baseline
  - Volume of work completed per employee per day
  - Example: support agents resolve 30% more tickets with FM-assisted responses

- **User engagement**
  - Adoption rate: percentage of target users actively using the FM feature
  - Session frequency and duration
  - Feature retention: do users return after first use?

- **Task engineering**
  - Task completion rate: did the FM successfully accomplish the intended task?
  - Error rate: how often does output require human correction?
  - Escalation rate: how often do users fall back to human support?

- **Alignment checks**
  - Map technical metrics (ROUGE, accuracy) to business outcomes
  - High BLEU does not guarantee user satisfaction
  - Run pilot with real users before full rollout
  - Define success criteria upfront: "reduce drafting time by 50%" not just "high ROUGE"

### Identify approaches to evaluate the performance of applications built with FM

- **RAG application evaluation**
  - **Retrieval quality**: precision@k, recall@k - did retrieval find the right documents?
  - **Answer faithfulness**: is the answer supported by retrieved context? (no hallucination beyond sources)
  - **Answer relevance**: does the answer address the user's question?
  - **End-to-end**: correct answer rate on domain-specific Q&A test set
  - Test with questions that require multi-document synthesis and unanswerable questions

- **Agent evaluation**
  - **Task success rate**: did agent complete the goal end-to-end?
  - **Step accuracy**: were individual tool calls correct?
  - **Efficiency**: number of steps/tokens to complete task
  - **Error recovery**: does agent handle tool failures gracefully?
  - **Safety**: does agent avoid unauthorized actions or data access?

- **Workflow evaluation**
  - Test multi-step pipelines: prompt → RAG → post-processing → output
  - Integration testing: FM + downstream systems (databases, APIs)
  - Load testing: performance under expected production traffic
  - Regression testing: new model/prompt version does not break existing functionality

- **Continuous evaluation**
  - Monitor production outputs with automated scoring
  - Sample production traffic for periodic human review
  - A/B test model versions or prompt changes with real users
  - Alert on quality degradation (drift detection)

### Identify business objective alignment metrics for AI applications

- **Task completion rate**
  - Percentage of user requests fully resolved without human intervention
  - Core metric for agents, chatbots, and automated workflows
  - Track by task type: simple FAQ vs. complex multi-step requests

- **User satisfaction**
  - CSAT (Customer Satisfaction Score): post-interaction rating
  - NPS (Net Promoter Score): likelihood to recommend
  - Thumbs up/down on individual FM responses
  - Qualitative feedback: user comments and support escalations

- **Cost per interaction**
  - Total cost (API tokens + infrastructure + human review) / number of interactions
  - Compare against cost of human-handled equivalent
  - Target: FM interaction cost < fraction of human cost with acceptable quality
  - Track token usage trends; optimize prompts and model selection to reduce cost

- **Additional alignment metrics**
  - **Revenue impact**: conversion rate lift, upsell from FM recommendations
  - **Deflection rate**: support tickets avoided by FM self-service
  - **Time to resolution**: average time to solve user problem (FM vs. human)
  - **Employee satisfaction**: internal tool adoption and perceived usefulness
  - **Error cost**: financial impact of FM mistakes (wrong refunds, incorrect advice)
  - **Compliance rate**: percentage of outputs passing regulatory/safety review
