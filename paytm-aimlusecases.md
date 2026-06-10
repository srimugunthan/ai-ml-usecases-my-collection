Here's a solid rundown of AI/ML use cases that Paytm has worked on, covering both their internal ML platforms and user-facing products:

---

## Paytm AI/ML Use Cases

### Fraud & Risk Detection

Paytm runs **Paytm Pi**, an in-house fraud and risk detection platform that leverages AI to automate fraud detection, merchant segmentation, and pricing optimisation. They also partnered with Groq in late 2025 to deploy GroqCloud for faster, cost-efficient AI inference to support transaction processing, risk assessment, and fraud detection at scale.

### Merchant Onboarding & KYC

Paytm uses AI-driven quality checks for onboarding merchants, including image and text recognition (OCR), name matching, and automatic deduction of Merchant Category Code (MCC) from storefront photos.

### Merchant Analytics — Paytm ARMS

**Paytm ARMS** (a merchant lifecycle insights platform) uses AI to automate merchant segmentation, lifecycle management, and pricing decisions.

### AI Soundbox — Conversational Voice AI

Paytm launched India's first AI-enabled Soundbox that lets merchants ask payment-related questions in 12 Indian languages via voice. They are also developing Small Language Models (SLMs) tailored for business use cases, enabling merchants to get CFO-like financial insights in their native languages via voice agents — aimed particularly at small and micro enterprises.

### AI Router for Payment Optimisation

Paytm built an **AI Router** that optimises payment routing for higher transaction success rates and lower operational costs.

### Text-to-SQL / NL-to-Database Queries

Paytm developed a proprietary AI system that translates natural language into complex database queries (Text-to-SQL), used by developers, tech ops, and analysts for analytics and decision making at scale. This system was recognised on the Spider 2.0 Snow leaderboard, making Paytm the first Indian company on that global benchmark.

### Consumer App — Spend Analytics & Personalisation

The redesigned Paytm app integrates AI for expense tracking, balance management, and personalised financial insights, with automatic categorisation of expenses across categories like shopping, bills, travel, and utilities.

### Conversational AI / Customer Support

Paytm uses conversational AI agents to provide personalised assistance to customers via text and voice across 11 languages. They built the **Paytm Assistant** — a hybrid bot framework combining conversational AI and rule-based bots — deployed both for end users and as a productivity tool for support agents.

### Credit / Small Ticket Lending

Paytm has been distributing small digital loans to consumers and merchants using AI-driven credit assessment, building an India-scale AI system for financial institutions to capture risks and fraud, including new risks arising from advances in AI itself.



---

**Summary by domain:**

| Domain | Key Use Case |
|---|---|
| Fraud & Risk | Paytm Pi, real-time transaction scoring |
| Merchant KYC | OCR, MCC detection, name matching |
| Merchant Analytics | ARMS — segmentation, lifecycle, pricing |
| Voice AI | AI Soundbox, multilingual SLMs |
| Routing Optimisation | AI Router for payment success rates |
| NLP / Text-to-SQL | Spider 2.0-ranked query system |
| Consumer Personalisation | Spend categorisation, insights |
| Customer Support | Multilingual conversational agents |
| Credit Decisioning | Small loan disbursement with ML scoring |


---
Paytm has systematically shifted to an **AI-first architecture**, heavily embedding machine learning models and generative AI agents into its operations to drive its recent profitability turnaround. Its AI/ML use cases are divided between real-time financial transaction intelligence and enterprise-scale workflow automation.

---

## 1. Financial Risk & Transaction Intelligence

Operating at massive transaction volumes, Paytm relies on real-time machine learning inference for core financial operations:

* **Payments Intelligence & Fraud Detection Engines:** Deployed at scale to run milliseconds-level risk modeling. The engine evaluates hundreds of real-time features—such as device IP, transaction region, historical velocity, and unsuccessful attempts—to compute a fraud probability score before a payment is authorized.
* **Credit Risk & Alternative Scoring Models:** For its digital lending vertical, Paytm utilizes ML-driven credit scoring systems that bypass traditional, document-heavy scoring. It analyzes ecosystem data (e.g., wallet history, merchant transaction velocity) to offer instant micro-loan and working capital approvals for underserved consumers and small-to-medium enterprises (SMEs).
* **AI-Powered Collections Engines:** Predictive modeling identifies risk buckets for loan repayments and optimizes collection pipelines, prioritizing accounts based on behavioral patterns and repayment likelihood.

---

## 2. Agentic AI & Enterprise Automation ("Paytm Inference")

Paytm has commercialized its internal AI developments into a production-grade enterprise platform, moving beyond traditional chatbots toward autonomous **Agentic AI** that orchestrates workflows across CRM, ERP, and API frameworks:

* **AI-First Inbound Support Agents:** Deployed across payments, lending, and merchant care channels. These hybrid systems utilize three layers: rule-based systems for instant compliance, ML models for statistical optimization, and Small Language Models (SLMs)/LLMs for human-like reasoning. The system handles over 10 million monthly queries, managing roughly 89% of inbound text and voice support without human intervention.
* **Outreach Managers & CLM (Customer Lifecycle Management) Agents:** Domain-specific agents designed to automate customer journeys across sales and operations. These agents reach out to merchants, closing deals and maintaining a 22% higher retention rate compared to human-led outreach.
* **LLM-as-a-Judge Evaluation Pipeline:** Every customer interaction is automatically scored using an internal LLM evaluation framework to measure resolution accuracy, empathy, and intent fulfillment, continually fine-tuning prompts and models.

---

## 3. Engineering & Infrastructure Optimization

To support its high-concurrency needs while keeping operational costs low, Paytm has embedded AI into its engineering and cybersecurity infrastructure:

* **Cloud Security Automation ("Code Armor"):** Built in collaboration with Microsoft using GitHub Copilot and Azure OpenAI, this internal solution automates public cloud infrastructure monitoring and security compliance. It dropped the turnaround time required to provision and secure new cloud accounts from 2–3 man-days to just 2–3 minutes (a 95% efficiency unlock).
* **AI-Driven Software Development Life Cycle (SDLC):** Generative AI agents are embedded directly within their development pipelines to handle automated code generation, test case writing, and continuous deployment (CI/CD) optimization.
* **Low-Latency Hardware Partnerships:** To minimize the inference cost of their custom SLMs, Paytm partners with infrastructure providers like **Groq** (using Language Processing Units, or LPUs) to achieve ultra-low-latency real-time insights across their platform at a fraction of standard GPU costs.

Given your background in financial services ML and adversarial AI, the Paytm Pi fraud detection platform and their credit scoring work would be most relevant — both are areas where your experience with GNN-based transaction networks and noise-robust learning would map directly.
