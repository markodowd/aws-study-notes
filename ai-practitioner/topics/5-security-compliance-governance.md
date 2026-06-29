# Domain 5 - Security, Compliance, and Governance for AI Solutions

## Task Statement 5.1: Explain methods to secure AI systems.

### Identify AWS services and features to secure AI systems

- **IAM roles, policies, and permissions**
  - Principle of least privilege: grant only permissions required for each role
  - Service roles for Bedrock, SageMaker, Lambda to access AWS resources on behalf of applications
  - Resource-based policies on S3 buckets, KMS keys, and Bedrock models
  - Condition keys: restrict access by VPC, source IP, MFA, or time
  - Separate roles for developers, data scientists, and production services
  - Use IAM Access Analyzer to identify overly permissive policies

- **Encryption**
  - **At rest**: S3 SSE-S3, SSE-KMS, or SSE-C; EBS volume encryption; SageMaker storage encryption
  - **In transit**: TLS 1.2+ for all API calls (Bedrock, SageMaker endpoints)
  - **Customer-managed KMS keys**: control key rotation, access policies, and audit trail
  - Encrypt training data, model artifacts, vector stores, and inference logs
  - Bedrock encrypts data at rest and in transit by default

- **Amazon Macie**
  - ML-powered service to discover, classify, and protect sensitive data in S3
  - Detects PII, financial data, credentials, and custom sensitive data patterns
  - Scan training datasets and RAG document corpora before ingestion
  - Automated alerts when sensitive data is exposed or unencrypted
  - Integrate with Security Hub for centralized findings

- **AWS PrivateLink**
  - Private connectivity between VPC and AWS services without traversing public internet
  - VPC endpoints for Bedrock, SageMaker, S3, and other services
  - Traffic stays on AWS network; reduces exposure to internet-based attacks
  - Required for workloads with strict network isolation requirements

- **AWS Shared Responsibility Model**
  - **AWS responsible for**: security OF the cloud (hardware, hypervisor, managed service infrastructure)
  - **Customer responsible for**: security IN the cloud (data, access control, application logic, prompts, model configuration)
  - For AI: customer secures training data, prompts, fine-tuning data, application integrations, and output handling
  - AWS secures Bedrock/SageMaker infrastructure; does not train on customer data by default

- **Amazon Bedrock AgentCore Identity**
  - Manages authentication and authorization for AI agents accessing external systems
  - Agents authenticate to third-party APIs, databases, and SaaS apps securely
  - OAuth, API keys, and credential management for agent tool integrations
  - Prevents agents from accessing unauthorized resources

- **Policy in AgentCore**
  - Define policies governing what agents can and cannot do
  - Restrict agent actions: which tools, APIs, and data sources are permitted
  - Enforce organizational security boundaries on autonomous agent behavior
  - Complement IAM policies with agent-specific action controls

- **Amazon Bedrock Guardrails**
  - Content filters: block harmful categories (hate, violence, sexual content)
  - Denied topics: prevent discussion of specified subjects
  - PII redaction: mask sensitive data in inputs and outputs
  - Word filters: block profanity, competitor names, or custom blocked terms
  - Contextual grounding check: verify responses are supported by source documents
  - Apply to both prompts and completions; configure per application

### Describe the concept of source citation and documenting data origins

- **Source citation**
  - Attribute answers to specific source documents used in generation
  - RAG applications return citations with retrieved chunks so users can verify claims
  - Reduces hallucination risk by grounding outputs in authoritative material
  - Bedrock Knowledge Bases can return source references with generated answers
  - Critical for regulated industries requiring auditability of AI-generated content

- **Data lineage**
  - Track data from origin through every transformation to final use in model
  - Records: where data came from, who processed it, what changes were applied, when
  - Essential for debugging model errors, compliance audits, and bias investigations
  - AWS: SageMaker ML Lineage Tracking, AWS Glue Data Catalog lineage

- **Data cataloging**
  - Centralized inventory of datasets with metadata: schema, owner, classification, quality
  - Enables discovery of approved data sources for training and RAG
  - Tags: sensitivity level, retention policy, geographic origin, license terms
  - AWS: AWS Glue Data Catalog, Amazon DataZone, SageMaker Feature Store metadata

- **Amazon SageMaker Model Cards**
  - Standardized documentation for ML models
  - Records: training data sources, preprocessing steps, evaluation results, known limitations
  - Ethical considerations section: bias metrics, intended use, out-of-scope uses
  - Provides transparency for auditors, compliance teams, and downstream consumers
  - Part of model governance lifecycle from development through deployment

- **Best practices for data provenance**
  - Document every data source license and usage rights
  - Version datasets alongside model versions they trained
  - Immutable audit log of data access and modifications
  - Reject data from unknown or untrusted origins for training/RAG

### Describe best practices for secure data engineering

- **Assessing data quality**
  - Validate completeness, accuracy, consistency, and timeliness before use
  - Automated profiling: missing values, outliers, duplicate records, schema violations
  - Quality gates: block pipeline progression if data fails quality thresholds
  - AWS: SageMaker Data Wrangler, Glue DataBrew, Deequ (open source on Spark)

- **Implementing privacy-enhancing technologies**
  - **Data anonymization**: remove or mask direct identifiers (names, SSNs, emails)
  - **Pseudonymization**: replace identifiers with tokens reversible only with separate key
  - **Differential privacy**: add statistical noise to protect individual records in aggregate
  - **Federated learning**: train on distributed data without centralizing raw data
  - **Synthetic data**: generate artificial datasets preserving statistical properties
  - AWS: Macie for PII detection; SageMaker supports differential privacy training

- **Data access control**
  - Role-based access control (RBAC) on S3 buckets, databases, and data catalogs
  - Column- and row-level security for sensitive fields
  - Lake Formation: fine-grained permissions on data lake resources
  - Separate dev/staging/prod data environments with isolated access
  - Audit all data access via CloudTrail

- **Data integrity**
  - Checksums and hashing to detect tampering or corruption in transit and at rest
  - Versioning on S3 buckets for training data and model artifacts
  - Immutable logs for data pipeline events
  - Validate data schema on ingestion; reject malformed records
  - Reproducibility: pin dataset versions to model versions

### Describe security and privacy considerations for AI systems

- **Application security**
  - Input validation and sanitization before sending to FM
  - Output validation before displaying or acting on model responses
  - Secure API design: authentication, rate limiting, request size limits
  - WAF rules to block malicious requests to AI endpoints
  - OWASP LLM Top 10 awareness: prompt injection, insecure output handling, training data poisoning

- **Threat detection**
  - Monitor for anomalous API usage patterns (unusual volume, new callers, off-hours access)
  - Detect prompt injection attempts in user inputs
  - Guardrails block known attack patterns
  - AWS: GuardDuty for threat detection, Security Hub for aggregated findings
  - CloudWatch alarms on error rates and latency spikes

- **Vulnerability management**
  - Regular scanning of containers, AMIs, and dependencies used in AI pipelines
  - Patch SageMaker notebook instances, training containers, and Lambda runtimes
  - AWS: Inspector for automated vulnerability scanning
  - Dependency scanning in CI/CD pipelines

- **Infrastructure protection**
  - VPC isolation for SageMaker endpoints and training jobs
  - Security groups and NACLs restrict network traffic
  - No public internet access for training data or model endpoints when required
  - PrivateLink and VPC endpoints for service connectivity

- **Prompt injection**
  - Attacker embeds malicious instructions in user input or retrieved documents
  - Can override system prompts, exfiltrate data, or trigger unauthorized actions
  - Mitigations: delimiter separation, input validation, Guardrails, least-privilege agent tools
  - Never put secrets (API keys, passwords) in system prompts

- **Encryption at rest and in transit**
  - All data encrypted by default on AWS; enforce with bucket policies and SCPs
  - TLS for all client-to-service and service-to-service communication
  - Customer-managed KMS keys for regulatory control and audit
  - Encrypt vector stores, embedding caches, and conversation logs

- **Data leakage prevention**
  - Guardrails PII redaction on inputs and outputs
  - Prevent model from revealing training data or system prompts
  - Output filtering: block responses containing sensitive patterns
  - Network egress controls: restrict what AI services can reach externally
  - Log and alert on responses containing credentials or PII

- **Output filtering and validation**
  - Schema validation for structured outputs (JSON, XML)
  - Content policy enforcement via Guardrails before returning to user
  - Business logic checks: validate agent actions before execution
  - Human review for high-risk outputs (A2I)

- **Audit trail and logging requirements**
  - CloudTrail logs all AWS API calls (Bedrock InvokeModel, SageMaker predictions)
  - Application-level logging: prompts, responses, model ID, user ID, timestamp
  - Retain logs per compliance requirements (often 1–7 years)
  - Immutable log storage (S3 Object Lock, CloudTrail log file validation)
  - Enable for forensic investigation and regulatory audits

- **Toxicity**
  - Monitor and block harmful, hateful, or abusive model outputs
  - Guardrails content filters with configurable thresholds per category
  - Toxicity scoring in Bedrock Model Evaluation
  - User reporting mechanism for toxic outputs missed by filters

### Describe hallucination detection methods and grounding techniques

- **Retrieval Augmented Generation (RAG) grounding**
  - Retrieve relevant documents and inject into prompt as context
  - Model generates answers based on retrieved content, not just training knowledge
  - Bedrock Knowledge Bases automate retrieval and grounding
  - Reduces hallucinations by anchoring responses to verified source material

- **Output validation**
  - Cross-check generated facts against knowledge base or structured database
  - Regex and schema validation for structured outputs
  - Reject or flag responses that fail validation rules
  - Post-processing pipeline: generate → validate → approve/reject → deliver

- **Confidence scoring**
  - Model or separate classifier assigns confidence level to each output
  - Low-confidence responses routed to human review (A2I) or flagged to user
  - Logprobs from FM API indicate token-level certainty
  - Display uncertainty to users: "I'm not confident in this answer"

- **Contextual grounding check (Bedrock Guardrails)**
  - Automated check: is the response supported by the provided source context?
  - Returns grounding score; block or warn on ungrounded responses
  - Specifically designed for RAG applications

- **Citation requirements**
  - Require model to cite source documents for factual claims
  - Verify cited sources actually contain the claimed information
  - Users can click through to original documents for verification

- **Additional grounding techniques**
  - **Constrained generation**: restrict output to predefined options or templates
  - **Multi-model verification**: second model checks first model's output
  - **Human-in-the-loop**: reviewer validates outputs before publication
  - **Fact-checking APIs**: cross-reference claims against external knowledge bases
  - **Temperature 0**: reduce randomness for factual tasks

## Task Statement 5.2: Recognize governance and compliance regulations for AI systems.

### Identify AWS services and features to assist with governance and regulation compliance

- **AWS Config**
  - Continuously records and evaluates AWS resource configurations
  - Config rules check compliance: encryption enabled, public access blocked, logging active
  - Automated remediation for non-compliant resources
  - AI-relevant rules: S3 bucket encryption, SageMaker endpoint in VPC, IAM policy checks
  - Compliance dashboards and historical configuration timeline

- **Amazon Inspector**
  - Automated vulnerability scanning for EC2, ECR containers, and Lambda functions
  - Scans AI training containers, inference images, and notebook instances
  - Prioritized findings with CVE details and remediation guidance
  - Integrates with Security Hub and EventBridge for automated response

- **AWS Audit Manager**
  - Prebuilt frameworks mapping to compliance standards (SOC, PCI, HIPAA, GDPR, NIST)
  - Continuously collects evidence from AWS services for audit readiness
  - Custom frameworks for internal AI governance policies
  - Automated evidence collection reduces manual audit preparation

- **AWS Artifact**
  - On-demand access to AWS compliance reports and agreements
  - SOC 1/2/3, PCI DSS, ISO 27001, HIPAA, FedRAMP reports
  - Business Associate Addendum (BAA) for HIPAA-eligible services
  - Demonstrate AWS compliance to auditors and customers

- **AWS CloudTrail**
  - Logs all API activity across AWS account
  - AI-relevant events: Bedrock InvokeModel, SageMaker CreateEndpoint, S3 data access
  - Immutable audit trail for who did what, when, and from where
  - Integrate with CloudWatch Logs and SIEM tools for analysis
  - Organization trail for multi-account governance

- **AWS Trusted Advisor**
  - Automated checks for security, cost optimization, performance, and fault tolerance
  - Flags: overly permissive security groups, unencrypted resources, MFA not enabled
  - Supplement AI-specific governance with general AWS best practices

- **Additional governance services**
  - **AWS Organizations + SCPs**: enforce policies across all accounts (e.g., require encryption)
  - **AWS Security Hub**: centralized security findings and compliance scores
  - **Amazon CloudWatch**: monitoring, logging, and alerting for AI workloads
  - **AWS Lake Formation**: data lake governance with fine-grained access control
  - **Amazon DataZone**: data governance and cataloging for enterprise data sharing

### Describe data governance strategies

- **Data lifecycles**
  - Define stages: create → store → use → share → archive → destroy
  - Policies per stage: who can access, how long to retain, when to delete
  - AI-specific: training data lifecycle separate from inference data lifecycle
  - Automate transitions: S3 lifecycle rules, Glacier archival, scheduled deletion
  - Model artifacts follow same lifecycle as the data that trained them

- **Logging**
  - Comprehensive logging of data access, model invocations, and pipeline events
  - Centralized log aggregation (CloudWatch Logs, OpenSearch, third-party SIEM)
  - Structured logs with consistent fields: user, action, resource, timestamp, outcome
  - Log retention aligned with regulatory requirements

- **Residency**
  - Data must remain in specific geographic regions for legal compliance
  - Deploy Bedrock, SageMaker, S3, and vector stores in required regions
  - Cross-region inference may move data; verify policies before enabling
  - Document where data is stored, processed, and transmitted

- **Monitoring**
  - Continuous monitoring of data quality, access patterns, and model behavior
  - SageMaker Model Monitor for drift and bias detection
  - Macie for ongoing sensitive data discovery
  - CloudWatch dashboards for AI service metrics and anomalies

- **Observation**
  - Real-time visibility into AI system behavior in production
  - Trace requests end-to-end: input → retrieval → model → output → action
  - X-Ray for distributed tracing across AI application components
  - Observability beyond logging: metrics, traces, and structured events

- **Retention**
  - Define how long to keep training data, logs, model versions, and conversation history
  - Balance: compliance requirements (keep) vs. privacy principles (delete when no longer needed)
  - Automated deletion policies (S3 lifecycle, DynamoDB TTL)
  - Right to erasure: ability to delete user data on request (GDPR)

### Describe processes to follow governance protocols

- **Policies**
  - Written AI governance policies: acceptable use, data handling, model approval, incident response
  - Define which data can be used for training, RAG, and inference
  - Prohibit use of customer data for model training without consent
  - Require security review before deploying AI features to production
  - Align with organizational risk appetite and regulatory obligations

- **Review cadence**
  - Regular scheduled reviews of AI systems, data access, and model performance
  - Quarterly governance board reviews for high-risk AI applications
  - Annual policy updates reflecting new regulations and lessons learned
  - Triggered reviews after incidents, model changes, or regulatory updates

- **Review strategies**
  - **Model review**: accuracy, bias, safety before production deployment
  - **Data review**: quality, provenance, PII scan before training or RAG ingestion
  - **Access review**: periodic IAM access audits (who has access to what)
  - **Output review**: sample production outputs for quality and safety (human audit)
  - **Vendor review**: assess FM provider policies, certifications, and data handling

- **Governance frameworks**
  - **Generative AI Security Scoping Matrix**
    - Framework for assessing GenAI risk based on use case scope
    - Dimensions: data sensitivity, user interaction, autonomy level, external exposure
    - Higher scope = more security controls required
    - Guides control selection: Guardrails, VPC, human review, encryption level
  - **NIST AI Risk Management Framework (AI RMF)**
    - Govern, Map, Measure, Manage functions for AI risk
  - **ISO/IEC 42001**: AI management system standard

- **Transparency standards**
  - Disclose AI use to end users ("You are chatting with an AI assistant")
  - Document model capabilities, limitations, and known failure modes in Model Cards
  - Publish bias evaluation results for high-impact applications
  - Maintain changelog of model and prompt version updates

- **Team training requirements**
  - Security awareness training for all team members working with AI
  - Topics: prompt injection, data privacy, responsible AI, incident reporting
  - Role-specific training: data scientists (bias testing), developers (secure coding), operators (monitoring)
  - Regular refreshers as threats and regulations evolve
  - Document training completion for audit evidence

- **Incident response for AI**
  - Defined process for AI-specific incidents: harmful output, data leak, model compromise
  - Roles: who investigates, who communicates, who remediates
  - Kill switch: ability to disable AI feature immediately
  - Post-incident review and governance policy updates
