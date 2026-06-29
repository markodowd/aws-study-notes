# Domain 1 - Fundamentals of AI and ML

## Understanding AI

AI, also known as artificial intelligence, is a technology with humanlike problem-solving capabilities. AI in action appears to simulate human intelligence. It can recognise images, write poems, and make data-based predictions

## Components of AI

- Artificial Intelligence > Machine Learning > Deep Learning > Generative AI

## Key Components of SageMaker

- **SageMaker Studio**
  - Web-based ML development environment
  - Manage completew workflow in one place
  - Team Collaboration and automation

- **Notebook Instances**
  - Managed Jupyter notebooks
  - Code, experiment, and visualize
  - No setup required

- **JumpStart**
  - Pretrained models and algorithms
  - Quick-start solutions
  - Fine-tuning for specific use cases

- **Data Wrangler**
  - Clean and transform data
  - Connect to 50+ data sources
  - Faster preprocessing workflows

- **Model Monitor**
  - Monitor deployed models
  - Detect data drift automatically
  - Alert on performance issues

- **MLOps Tools
  - Workflow automation
  - Governance and version control
  - End-to-end pipeline management

## ML Lifecycle

- Business Goal Identification
  - KPIs
- ML Problem Framing
  - SMEs
  - ML might be wrong approach compared to traditional data analytics or process automation
- Data Processing
  - Data stores/warehouses
  - Amazon Redshift
  - Lakehouse (Amazon SageMaker Lakehouse)
  - Kinesis (real-time data processing)
- Model Development
- Model Deployment
- Monitoring

## Types of Data

- Labeled Data
- Unlabeled Data

## Formats of Data

- Structured Data
- Unstructured Data

## SageMaker Data Wrangler

- Data preprocessing
- Feature Engineering
- Data Visualization

## Model Development

- Training
- Evaluation
- Tuning

## Training

- Supervised
- Unsupervised
- Reinforcement

## Dataset

- Training Data (70-80%)
- Validating Data (10-15%)
- Testing Data (10-15%)

## Classification

- Fraud Detection
- Customer Churn Predicition
- Image Recognition
- Medical Diagnostics
- Sentiment Analysis
- Spam Filtering

## Regression

- Forecasting sales numbers
- Estimating stock market trends
- Predicting population growth
- Calculating life expectancy

## Regression Algorithms

- Linear Regression 
- Random Forest Regression 
- Support Vector Regression (SVR)

## Unsupervised

- Clustering
- Dimensionality Reduction

## Clustering

- Euclidean Distance
- Cosine Similarity
- Manhattan Distance

## Clustering Algorithms

- k-means Clustering
- Density-based spatial clustering of applications with noise (DBSCAN)
- Amazon's Random Cut Forest (RCF)

## Dimensionality Reduction

- Overfitting

## Dimensionality Reduction Algorithms

- Principal component analysis (PCA)
- t-SNE
- Autoencoders

## Reinforcement Learning

- Games
- Robotics

## ML Methods

- Supervised Learning
  - Classification
  - Regression
- Unsupervised Learning
  - Clustering
  - Dimensionality Reduction
- Reinforcement Learning

## SageMaker Options

- Pretrained Models
  - Foundation Models (FMs)
  - Computer Vision Models
  - NLP
- Built-in Algorithms
- Docker Images

## Evaluation

- Model Fit
  - Overfitting
  - Underfitting
- Classification
  - Confusion Matrix
  - Accuracy
  - Recall
  - Area Under the Curve-Receiver Operating Curve (AUC-ROC)
- Regression

## Confusion Matrix

- True Positives
- False Negatives
- False Positives
- True Negatives (TN)

- Accuracy (score)
  - (TP + TN) / (TP + FN + FP + TN)
- Precision
  - TP / (TP + FP)
- Recall
  - TP / (TP + FN)
- AUC-ROC
  - Recall against FP
- Regression
  - Mean Squared Error (MSE)
  - R Squared

## Tuning

- Batch Size
- Learning Rate
- Neural Network

## Hyperparameter Optimization

- Grid Search
- Random Search
- Bayesian Optimization
- Optuna

## Model Deployent

- Self-hosted API
- Managed API

## Inferencing

- Real-time Inference
- Batch Transform
- Asynchronous Inference
- On-demand Serverless Inference

## Monitoring

- Data Drift
- Concept Drift
- Label Shift
- Feature Drift

## MLOps

- Practices
- Processes
- Automations (ML Lifecycle)

## SafeMaker MLOps

- SageMaker Feature Store
- SageMaker Experiments
- SageMaker Processing
- SageMaker Model Registry

## AWS Development Tools

- SageMaker Notebook Instances
- SageMaker Studio Classic

## AWS ML Services

- Amazon Comprehend
- Amazon Translate
- Amazon Textract
- Amazon Lex
- Amazon Polly
- Amazon Transcribe
- Amazon Rekognition
- Amazon Kendra
- Amazon Personalize
- AWS DeepRacer

## Task Statement 1.1: Explain basic AI concepts and terminologies.

### Define basic AI terms

- **Artificial Intelligence (AI)**
  - Broad field of building systems that perform tasks requiring human-like intelligence
  - Includes reasoning, perception, language understanding, decision making, and learning
  - Encompasses rule-based systems, classical ML, deep learning, and generative AI

- **Machine Learning (ML)**
  - Subset of AI where systems learn patterns from data instead of being explicitly programmed
  - Models improve performance through experience (training data)
  - Requires data, features, a learning algorithm, and evaluation

- **Deep Learning**
  - Subset of ML using multi-layer neural networks (deep neural networks)
  - Excels at complex patterns in images, text, audio, and unstructured data
  - Requires large datasets and significant compute (often GPUs)

- **Neural Networks**
  - Computing models inspired by biological neurons
  - Composed of layers: input layer, hidden layers, output layer
  - Neurons apply weights and activation functions to transform inputs into outputs
  - Training adjusts weights to minimize prediction error

- **Computer Vision**
  - AI field focused on interpreting and understanding visual data (images, video)
  - Tasks include image classification, object detection, segmentation, and facial recognition
  - Common AWS services: Amazon Rekognition, Amazon Textract

- **Natural Language Processing (NLP)**
  - AI field focused on understanding, generating, and processing human language
  - Tasks include sentiment analysis, entity recognition, translation, summarization, and chatbots
  - Common AWS services: Amazon Comprehend, Amazon Translate, Amazon Lex

- **Model**
  - Mathematical representation learned from data that maps inputs to outputs
  - Contains parameters (weights) tuned during training
  - Can be serialized and deployed for inference on new data

- **Algorithm**
  - Step-by-step procedure or mathematical method used to train a model
  - Examples: linear regression, decision trees, k-means, gradient descent, transformers
  - Different algorithms suit different problem types and data characteristics

- **Training**
  - Process of feeding data to a model so it learns patterns
  - Model adjusts internal parameters to minimize a loss function
  - Requires labeled data (supervised), unlabeled data (unsupervised), or reward signals (reinforcement)
  - Computationally intensive; often done offline in batches

- **Inferencing (Inference)**
  - Using a trained model to make predictions or generate outputs on new, unseen data
  - Occurs at runtime in production applications
  - Must balance latency, throughput, cost, and accuracy

- **Bias**
  - Systematic error where a model consistently deviates in a particular direction
  - Can arise from unrepresentative training data, flawed features, or algorithmic choices
  - Leads to unfair or inaccurate outcomes for certain groups or scenarios

- **Fairness**
  - Ensuring AI systems treat individuals and groups equitably
  - Requires evaluating model performance across demographic segments
  - Involves detecting and mitigating bias in data, models, and outputs

- **Fit (Overfitting / Underfitting)**
  - **Good fit**: model generalizes well to unseen data
  - **Overfitting**: model memorizes training data, performs poorly on new data
  - **Underfitting**: model is too simple to capture underlying patterns
  - Controlled through regularization, cross-validation, and appropriate model complexity

- **Large Language Model (LLM)**
  - Deep learning model trained on vast amounts of text data
  - Predicts and generates human-like text based on context
  - Powers tasks like summarization, Q&A, code generation, and conversation
  - Examples: models available through Amazon Bedrock (Claude, Llama, Titan, etc.)

- **Generative AI (GenAI)**
  - AI that creates new content (text, images, audio, video, code) rather than only classifying or predicting
  - Built on foundation models trained on large datasets
  - Uses techniques like transformers, diffusion models, and autoregressive generation

- **Agentic AI**
  - AI systems that can plan, reason, and take autonomous actions to achieve goals
  - Combines LLMs with tools, APIs, memory, and decision loops
  - Can break complex tasks into steps, call external services, and iterate on results
  - Examples: Amazon Bedrock Agents, agent frameworks built on foundation models

### Describe the similarities and differences between AI, ML, GenAI, deep learning, and agentic AI

- **Relationship hierarchy**
  - AI is the broadest category
  - ML is a subset of AI
  - Deep learning is a subset of ML
  - GenAI often uses deep learning (especially transformers)
  - Agentic AI often builds on GenAI/LLMs with orchestration layers

- **AI**
  - Any system exhibiting intelligent behavior
  - Includes non-learning approaches (expert systems, rule engines) and learning approaches
  - Goal: automate tasks requiring human-like cognition

- **ML**
  - Learns from data rather than hand-coded rules
  - Requires training data and an evaluation process
  - Produces models that improve with more relevant data
  - Focus: prediction, classification, clustering, ranking

- **Deep Learning**
  - Uses neural networks with many layers
  - Automatically learns feature representations from raw data
  - Requires more data and compute than traditional ML
  - Best for unstructured data (images, text, audio)

- **GenAI**
  - Creates novel content rather than only labeling or scoring inputs
  - Relies on foundation models pre-trained on massive datasets
  - Can be adapted via fine-tuning, RAG, or prompting
  - Focus: generation, creativity, content production

- **Agentic AI**
  - Goes beyond single-turn generation to multi-step autonomous workflows
  - Uses tools (APIs, databases, code execution) to act in the world
  - Maintains context and memory across interactions
  - Focus: task completion, orchestration, decision making

- **Key differences summary**
  - **AI**: intelligent behavior; varied inputs; outputs decisions and actions
  - **ML**: learn from data; structured or unstructured inputs; outputs predictions and labels
  - **Deep Learning**: learn representations; raw unstructured inputs; outputs predictions and embeddings
  - **GenAI**: create new content; prompts and context; outputs text, images, code, etc.
  - **Agentic AI**: autonomous task execution; goals and instructions; outputs completed multi-step tasks

### Describe various types of inferencing

- **Batch inferencing**
  - Processes large volumes of data offline at scheduled intervals
  - Optimized for throughput over latency
  - No immediate response required
  - Use cases: nightly fraud scoring, bulk document classification, periodic forecasting
  - AWS: SageMaker batch transform, scheduled Lambda jobs, EMR

- **Real-time (online) inferencing**
  - Synchronous requests with low-latency responses (milliseconds to seconds)
  - User or application waits for the result
  - Use cases: fraud detection at checkout, live recommendations, chatbot responses
  - AWS: SageMaker real-time endpoints, API Gateway + Lambda, Bedrock InvokeModel

- **Asynchronous inferencing**
  - Request is submitted and processed in the background; results retrieved later
  - Handles longer-running inference without blocking the caller
  - Use cases: large document analysis, video processing, lengthy text generation
  - AWS: SageMaker async inference endpoints, SQS-based patterns

- **Serverless inferencing**
  - No infrastructure to manage; scales automatically with demand
  - Pay per invocation; cold starts may affect latency
  - Use cases: variable or unpredictable traffic, event-driven workloads
  - AWS: Lambda with embedded models, SageMaker Serverless Inference, Bedrock

- **Choosing inference type**
  - Latency requirements: real-time vs. batch
  - Request size and processing duration: sync vs. async
  - Traffic patterns: steady vs. spiky (serverless helps with spikes)
  - Cost model: always-on endpoints vs. pay-per-use

### Describe the different types of data in AI models

- **Labeled data**
  - Each data point has a known correct output (target/label)
  - Required for supervised learning
  - Examples: emails tagged spam/not spam, images with object bounding boxes
  - Labeling is often expensive and time-consuming (Amazon SageMaker Ground Truth)

- **Unlabeled data**
  - Data without predefined outputs
  - Used in unsupervised learning to discover patterns or structure
  - Examples: customer transaction logs, raw text corpora, unannotated images

- **Tabular data**
  - Structured in rows and columns (spreadsheet-like)
  - Features are numeric or categorical
  - Common in traditional ML: fraud detection, churn prediction, pricing
  - AWS: stored in S3, queried with Athena, processed with SageMaker

- **Time-series data**
  - Data points indexed by time
  - Captures trends, seasonality, and temporal dependencies
  - Use cases: demand forecasting, anomaly detection, IoT sensor analysis
  - AWS: Amazon Forecast, SageMaker with time-series algorithms

- **Image data**
  - Visual data: photos, scans, video frames
  - Requires computer vision models (CNNs, vision transformers)
  - Use cases: defect detection, medical imaging, content moderation
  - AWS: Amazon Rekognition, SageMaker image classification/detection

- **Text data**
  - Unstructured natural language: documents, reviews, chat logs
  - Requires NLP or LLM techniques
  - Use cases: sentiment analysis, summarization, search, chatbots
  - AWS: Amazon Comprehend, Bedrock, OpenSearch with vector search

- **Structured data**
  - Organized in a defined schema (databases, tables, JSON with fixed fields)
  - Easy to query and process with SQL or pandas
  - Well-suited for traditional ML algorithms

- **Unstructured data**
  - No predefined schema: free text, images, audio, video
  - Represents ~80% of enterprise data
  - Requires feature extraction or deep learning to process
  - GenAI and deep learning have greatly improved unstructured data handling

### Describe different types of AI/ML learning

- **Supervised learning**
  - Model learns from labeled input-output pairs
  - Goal: predict labels for new, unseen data
  - **Classification**: predict a category (spam detection, image class)
  - **Regression**: predict a continuous value (house price, demand forecast)
  - Algorithms: linear/logistic regression, decision trees, random forests, SVMs, neural networks
  - Requires quality labeled datasets; label noise degrades performance

- **Unsupervised learning**
  - Model finds patterns in data without labels
  - **Clustering**: group similar data points (customer segmentation, anomaly grouping)
  - **Dimensionality reduction**: compress features while preserving structure (PCA, t-SNE)
  - **Association**: discover relationships between items (market basket analysis)
  - Algorithms: k-means, hierarchical clustering, DBSCAN, autoencoders
  - Useful for exploration, preprocessing, and when labels are unavailable

- **Reinforcement learning (RL)**
  - Agent learns by interacting with an environment and receiving rewards or penalties
  - Goal: maximize cumulative reward over time through trial and error
  - Key concepts: state, action, reward, policy, exploration vs. exploitation
  - Use cases: robotics, game playing, dynamic pricing, recommendation optimization
  - AWS: Amazon SageMaker RL, AWS DeepRacer
  - Requires careful reward design; can be sample-inefficient

- **Semi-supervised learning**
  - Combines a small amount of labeled data with a large amount of unlabeled data
  - Reduces labeling cost while improving accuracy over purely unsupervised methods

- **Self-supervised learning**
  - Model generates its own labels from the data structure
  - Common in pre-training foundation models (predict masked words, next sentence)
  - Bridge between unsupervised and supervised paradigms

## Task Statement 1.2: Identify practical use cases for AI.

### Recognize applications where AI/ML can provide value

- **Assist human decision making**
  - Surface insights from data too large or complex for manual analysis
  - Provide recommendations with confidence scores for human review
  - Examples: medical image triage, credit risk scoring, sales lead prioritization

- **Solution scalability**
  - Handle millions of requests without linear increase in human labor
  - Consistent quality regardless of volume
  - Examples: automated translation, content moderation at scale, chatbot support

- **Automation**
  - Replace repetitive, rule-based, or pattern-recognition tasks
  - Reduce errors and free humans for higher-value work
  - Examples: document processing (OCR + extraction), invoice classification, predictive maintenance alerts

- **Personalization**
  - Tailor experiences to individual users based on behavior and preferences
  - Examples: product recommendations, content feeds, dynamic pricing

- **Pattern discovery**
  - Uncover hidden trends, correlations, and anomalies in data
  - Examples: fraud ring detection, customer churn drivers, supply chain bottlenecks

### Determine when AI/ML solutions are not appropriate

- **Cost-benefit analysis**
  - ML development, data labeling, infrastructure, and maintenance have real costs
  - Simple rule-based or SQL solutions may achieve the same outcome cheaper
  - Consider total cost of ownership vs. expected business value

- **Insufficient or poor-quality data**
  - Not enough historical data to train a reliable model
  - Data is biased, incomplete, or not representative of production scenarios
  - No clear path to obtain or label the data needed

- **Need for deterministic, exact outcomes**
  - ML produces probabilistic predictions, not guarantees
  - When a specific, auditable, repeatable outcome is required (legal compliance, safety-critical logic)
  - Use explicit business rules or traditional software instead

- **Explainability requirements**
  - Regulated industries may require fully interpretable decisions (some lending, healthcare)
  - Black-box deep learning models may not meet compliance standards
  - Consider simpler models or explainability tools (SHAP, SageMaker Clarify)

- **Problem is fully solvable with rules**
  - If experts can write complete, stable rules, ML adds unnecessary complexity
  - Example: tax bracket calculation — use formulas, not a model

- **Rapidly changing environments**
  - If patterns shift faster than models can be retrained, predictions become stale
  - Concept drift requires ongoing monitoring and retraining investment

### Select the appropriate AI/ML techniques for specific use cases

- **Regression**
  - Predict a continuous numeric value
  - Use cases: sales forecasting, price estimation, demand planning
  - Algorithms: linear regression, gradient boosting (XGBoost), neural networks

- **Classification**
  - Assign input to one of several predefined categories
  - Use cases: spam detection, disease diagnosis, sentiment (positive/negative/neutral)
  - Algorithms: logistic regression, decision trees, SVMs, neural networks

- **Clustering**
  - Group data points by similarity without predefined labels
  - Use cases: customer segmentation, anomaly grouping, document organization
  - Algorithms: k-means, DBSCAN, hierarchical clustering

- **Ranking / Recommendation**
  - Order items by relevance or likelihood of interest
  - Use cases: product recommendations, search result ranking, content feeds
  - Algorithms: collaborative filtering, learning-to-rank, two-tower models

- **Anomaly detection**
  - Identify data points that deviate significantly from normal patterns
  - Use cases: fraud detection, equipment failure, network intrusion
  - Algorithms: isolation forest, autoencoders, statistical methods

- **NLP tasks**
  - Text classification, entity extraction, summarization, translation, Q&A
  - Traditional ML for simple tasks; LLMs/foundation models for complex language tasks

- **Computer vision tasks**
  - Image classification, object detection, segmentation, OCR
  - Deep learning (CNNs, vision transformers) is standard approach

- **Generative tasks**
  - Create new content: text, images, code, audio
  - Use foundation models via prompting, fine-tuning, or RAG

### Identify examples of real-world AI applications

- **Computer vision**
  - Manufacturing defect detection on assembly lines
  - Autonomous vehicle perception
  - Medical image analysis (X-rays, MRIs)

- **NLP**
  - Sentiment analysis of product reviews
  - Contract clause extraction and summarization
  - Multilingual customer support chatbots

- **Speech recognition**
  - Voice-controlled assistants and IVR systems
  - Meeting transcription and note-taking
  - AWS: Amazon Transcribe

- **Recommendation systems**
  - E-commerce product suggestions (Amazon Personalize)
  - Streaming content recommendations (Netflix, Spotify)
  - News and social media feeds

- **Fraud detection**
  - Real-time transaction scoring for credit cards
  - Insurance claim anomaly detection
  - Account takeover prevention

- **Forecasting**
  - Retail demand and inventory planning (Amazon Forecast)
  - Energy load prediction
  - Financial market trend analysis

- **Knowledge bases**
  - Enterprise search over documents with Q&A (Amazon Kendra, Bedrock Knowledge Bases)
  - RAG-powered internal assistants grounded in company data

- **Agentic AI**
  - Autonomous customer service agents that look up orders and process refunds
  - DevOps agents that diagnose incidents and suggest fixes
  - Research agents that gather, synthesize, and report on topics

### Explain the capabilities of AWS managed AI/ML services

- **Amazon SageMaker AI**
  - End-to-end ML platform: data preparation, training, tuning, deployment, monitoring
  - Built-in algorithms, Jupyter notebooks, feature store, model registry
  - Supports custom training, distributed training, and MLOps pipelines
  - Model hosting: real-time, batch, async, and serverless endpoints

- **Amazon Transcribe**
  - Automatic speech recognition (ASR) — audio/video to text
  - Supports multiple languages, custom vocabularies, speaker identification
  - Use cases: call center analytics, subtitle generation, meeting notes

- **Amazon Translate**
  - Neural machine translation between 75+ languages
  - Real-time and batch translation
  - Custom terminology for domain-specific accuracy

- **Amazon Comprehend**
  - NLP service for text analysis without ML expertise
  - Sentiment analysis, entity recognition, key phrase extraction, PII detection
  - Custom classification and entity models with your labeled data

- **Amazon Lex**
  - Build conversational interfaces (chatbots, voice bots)
  - Powered by the same technology as Alexa
  - Integrates with Lambda for fulfillment logic
  - Supports multi-turn conversations and slot filling

- **Amazon Polly**
  - Text-to-speech (TTS) service
  - Natural-sounding voices in many languages
  - Use cases: accessibility, voice-enabled apps, IVR prompts

- **Other notable services**
  - **Amazon Rekognition**: image and video analysis (faces, objects, moderation)
  - **Amazon Textract**: extract text and data from documents (OCR + forms/tables)
  - **Amazon Bedrock**: access to foundation models via unified API
  - **Amazon Personalize**: real-time recommendation engine
  - **Amazon Forecast**: time-series forecasting

### Identify when traditional ML models or foundation models (FMs) are appropriate

- **Use traditional ML when**
  - Problem is well-defined with structured/tabular data (fraud scoring, churn)
  - Explainability and auditability are required (regulated industries)
  - Training data is limited but sufficient for a focused task
  - Low latency and predictable cost per prediction are critical
  - Domain-specific features are already engineered and well understood
  - Model size must be small (edge deployment, embedded devices)

- **Use foundation models when**
  - Task involves complex language understanding or generation
  - Unstructured data (long documents, images, multi-modal content)
  - Rapid prototyping — FM + prompting avoids lengthy custom training
  - Task requires broad world knowledge not captured in a small dataset
  - Use cases: summarization, Q&A, code generation, content creation, agents

- **Regulatory and compliance considerations**
  - FMs may be harder to explain; traditional models preferred when audit trails are mandatory
  - PII and data residency: consider whether data can be sent to FM APIs
  - SageMaker Clarify for bias detection; model cards for documentation

- **Operational constraints**
  - FM inference can be expensive at scale; traditional ML may be more cost-effective for high-volume simple tasks
  - Latency: smaller traditional models often faster than large FMs
  - Fine-tuning FMs bridges the gap when prompting alone is insufficient

- **Hybrid approaches**
  - FM for understanding/generation + traditional ML for structured scoring
  - RAG: FM grounded in retrieved documents for domain-specific accuracy
  - FM extracts features; traditional model makes final classification

## Task Statement 1.3: Describe the AI/ML development lifecycle.

### Describe and differentiate components of an AI/ML pipeline

- **Problem definition**
  - Define business objective, success metrics, and constraints
  - Determine if ML is the right approach
  - Identify stakeholders and compliance requirements

- **Data collection and ingestion**
  - Gather raw data from databases, APIs, streams, files, IoT devices
  - AWS: S3, Kinesis, Glue, DataBrew, AppFlow

- **Data exploration and analysis (EDA)**
  - Understand distributions, missing values, correlations, outliers
  - Visualize data to inform feature engineering and algorithm choice

- **Data preprocessing and feature engineering**
  - Clean data: handle missing values, remove duplicates, fix errors
  - Transform features: encoding, scaling, normalization, embedding
  - Split data into training, validation, and test sets

- **Model selection and training**
  - Choose algorithm or foundation model based on problem type
  - Train on training set; tune hyperparameters on validation set
  - AWS: SageMaker Training, Bedrock fine-tuning

- **Model evaluation**
  - Assess performance on held-out test set using appropriate metrics
  - Check for bias, fairness, and robustness
  - Compare against baseline and business requirements

- **Model deployment**
  - Package model and serve predictions in production
  - Options: endpoints, batch jobs, serverless, edge devices
  - AWS: SageMaker endpoints, Lambda, Bedrock, IoT Greengrass

- **Monitoring and maintenance**
  - Track prediction quality, latency, throughput, and data drift
  - Retrain when performance degrades or data distributions shift
  - AWS: SageMaker Model Monitor, CloudWatch

### Describe sources of FM models

- **Open source pre-trained models**
  - Publicly available models: Meta Llama, Mistral, Hugging Face model hub
  - Free to use (check license terms); self-host or access via Bedrock
  - Can fine-tune on custom data for domain adaptation

- **AWS-provided foundation models**
  - Available through Amazon Bedrock: Anthropic Claude, Amazon Titan, AI21, Cohere, Stability AI
  - Managed infrastructure; no server provisioning
  - Pay per token (input + output)

- **Train custom models**
  - Fine-tune an existing FM on proprietary data (SageMaker, Bedrock customization)
  - Train from scratch (rare; requires massive data and compute)
  - Full control over architecture, data, and intellectual property

- **Third-party model marketplaces**
  - Models from partners available through AWS (Bedrock marketplace)
  - Pre-validated for security and integration

- **Choosing a source**
  - License and IP considerations
  - Data privacy (can proprietary data be used for fine-tuning on a shared platform?)
  - Performance requirements and model size
  - Cost of inference at expected scale

### Describe methods to use a model in production

- **Managed API service**
  - Call a fully managed endpoint with no infrastructure management
  - AWS: Bedrock InvokeModel, Comprehend DetectSentiment, Rekognition DetectLabels
  - Pros: fast to deploy, auto-scaling, low ops burden
  - Cons: less control, potential vendor lock-in, per-call pricing

- **Self-hosted API**
  - Deploy model on your own compute (EC2, EKS, SageMaker endpoints)
  - Full control over instance type, scaling, networking, and security
  - Pros: customization, data stays in your VPC, predictable cost at scale
  - Cons: you manage infrastructure, scaling, and updates

- **Embedded / edge deployment**
  - Run model on-device (IoT, mobile, local servers)
  - AWS: SageMaker Edge Manager, IoT Greengrass
  - Use when low latency, offline capability, or data privacy requires local inference

- **Batch processing**
  - Run inference on large datasets offline
  - AWS: SageMaker batch transform, Glue + custom jobs
  - No real-time endpoint needed; cost-efficient for periodic jobs

- **Serverless**
  - Invoke model via Lambda or SageMaker Serverless Inference
  - Scales to zero; pay per request
  - Good for variable traffic; watch cold-start latency

### Identify relevant AWS services and features for each stage of an AI/ML pipeline

- **Data ingestion and storage**
  - Amazon S3 (data lake), AWS Glue (ETL), Amazon Kinesis (streaming)
  - AWS DataBrew (visual data prep), Amazon AppFlow (SaaS connectors)

- **Data labeling**
  - Amazon SageMaker Ground Truth (human-in-the-loop labeling)

- **Exploration and preprocessing**
  - SageMaker Data Wrangler, SageMaker Processing, AWS Glue DataBrew
  - Amazon Athena (SQL on S3), Amazon EMR (big data)

- **Training and tuning**
  - Amazon SageMaker Training (built-in and custom algorithms)
  - SageMaker Automatic Model Tuning (hyperparameter optimization)
  - Amazon Bedrock (FM fine-tuning and customization)

- **Experiment tracking and model management**
  - SageMaker Experiments, SageMaker Model Registry
  - MLflow integration

- **Deployment**
  - SageMaker real-time, async, batch, and serverless endpoints
  - Amazon Bedrock (FM inference)
  - AWS Lambda (lightweight models)
  - Amazon ECS/EKS (containerized models)

- **Generative AI and agents**
  - Amazon Bedrock (FMs, Knowledge Bases, Agents, Guardrails)
  - Amazon Q (generative AI assistant for business and developers)

- **Business intelligence and reporting**
  - Amazon Quick (BI tool with generative AI capabilities for data analysis)
  - Amazon QuickSight (dashboards, ML insights)

- **Development tools**
  - Kiro (AI-powered IDE for building applications)
  - SageMaker Studio (integrated ML development environment)
  - AWS CodePipeline + CodeBuild (CI/CD for ML)

- **Monitoring**
  - SageMaker Model Monitor (data drift, quality)
  - Amazon CloudWatch (metrics, logs, alarms)

### Describe fundamental concepts of ML operations (MLOps)

- **Experimentation**
  - Systematically track training runs, hyperparameters, metrics, and artifacts
  - Reproducibility: same data + code + config = same results
  - Tools: SageMaker Experiments, MLflow

- **Repeatable processes**
  - Automate data prep, training, evaluation, and deployment pipelines
  - Version control for code, data, and models
  - CI/CD for ML: trigger retraining on new data or code changes

- **Scalable systems**
  - Infrastructure scales with data volume and inference demand
  - Distributed training for large datasets
  - Auto-scaling endpoints for production traffic

- **Managing technical debt**
  - ML systems accumulate debt from data dependencies, pipeline complexity, and model entanglement
  - Mitigate with modular pipelines, clear interfaces, automated testing, and documentation

- **Achieving production readiness**
  - Model meets accuracy, latency, and fairness requirements
  - Security: encryption, IAM, VPC, input validation
  - Disaster recovery and rollback plans
  - Load testing and failure mode analysis

- **Model monitoring**
  - Track inference latency, error rates, and throughput
  - Detect data drift (input distribution changes) and concept drift (relationship changes)
  - Monitor prediction distributions for anomalies
  - AWS: SageMaker Model Monitor, CloudWatch

- **Model re-training**
  - Scheduled retraining on fresh data (weekly, monthly)
  - Triggered retraining when monitoring detects performance degradation
  - Champion/challenger testing: compare new model against production model before promotion
  - Automated pipelines: SageMaker Pipelines, Step Functions

### Describe model performance metrics and business metrics

- **Classification metrics**
  - **Accuracy**: proportion of correct predictions (misleading with imbalanced classes)
  - **Precision**: of positive predictions, how many were correct (minimize false positives)
  - **Recall (Sensitivity)**: of actual positives, how many were found (minimize false negatives)
  - **F1 Score**: harmonic mean of precision and recall (balances both)
  - **Confusion matrix**: visualizes true/false positives and negatives
  - **AUC-ROC**: model's ability to distinguish classes across thresholds

- **Regression metrics**
  - **MAE** (Mean Absolute Error): average absolute difference between predicted and actual
  - **MSE / RMSE** (Mean Squared / Root Mean Squared Error): penalizes large errors more
  - **R-squared**: proportion of variance explained by the model

- **Ranking / recommendation metrics**
  - **Precision@K**: relevance of top K recommendations
  - **NDCG** (Normalized Discounted Cumulative Gain): ranking quality with position weighting
  - **MAP** (Mean Average Precision): average precision across queries

- **Generative AI metrics**
  - BLEU, ROUGE (text overlap with reference)
  - Human evaluation (fluency, relevance, safety)
  - Task-specific benchmarks (MMLU, HumanEval for code)

- **Business metrics**
  - **Cost per user / per prediction**: infrastructure and API costs divided by usage
  - **Development costs**: data labeling, engineering time, training compute
  - **Customer feedback**: satisfaction scores, NPS, support ticket reduction
  - **Return on Investment (ROI)**: (business value gained − total cost) / total cost
  - **Revenue impact**: conversion rate lift, churn reduction, upsell from recommendations

- **Choosing the right metrics**
  - Align ML metrics with business objectives
  - Fraud detection: optimize recall (catch fraud) even at cost of precision (some false alarms)
  - Medical screening: high recall to avoid missed diagnoses
  - Spam filter: high precision to avoid blocking legitimate emails
  - Always consider both technical performance and business outcome
