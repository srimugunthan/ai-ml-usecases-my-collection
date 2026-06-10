
CRED:
- credit score
- Fraud models: Transaction anamoly detection using GNNs
- Real time fraud detection system
- Document AI classifying bank statments, income statements and kyc
- Churn prediction


Paytm:
- Document AI for merchant onboarding
- Customer support agent
- Credit  risk and scoring


Capital one
-GraphML for Fraud detection
-Digital customer embeddings
-Real time fraud detection
-Credit and risk managment



Stripe
- Credit risk
- ID verfication in real time
- Graph ML for fraud
- MCP (Model Context Protocol) server tooling that allows AI agents to interact directly with the Stripe API and search the knowledge base.
- Payments Foundation Model (self-supervised, trained on transaction sequences)

JusPay
- Agentic commerce
- payment routing
- Fraud and risk models


SELECTED:
Three use cases that cut across all or most of these companies:

---

## 1. Graph ML for Fraud Detection

CRED, Capital One, Stripe, and Juspay all run graph-based fraud models. The core problem is identical: transactions, accounts, devices, and merchants form a network, and fraud rings are detectable as structural anomalies — dense subgraphs, shared entity nodes, unusual connectivity patterns — that flat tabular models miss entirely. GNNs (GraphSAGE, GAT, or custom message-passing architectures) over bipartite transaction graphs are the standard approach. The signal is relational, not just feature-based.

**Why it's universal:** Every payments player eventually hits the ceiling of per-transaction feature engineering and needs network-level signals to catch coordinated fraud and synthetic identity rings.

---

## 2. Real-Time Credit Risk and Scoring

CRED, Paytm, Capital One, and Stripe all run credit risk models at the core of their lending or underwriting stack. The ML problem involves combining bureau signals, behavioral embeddings (transaction history, repayment patterns), and document-extracted features (bank statements, income proofs via Document AI) into a scoring model that runs at origination and continues to monitor exposure post-disbursement. Gradient boosted trees (LightGBM/XGBoost) remain dominant here, often stacked with neural embeddings for behavioral sequences.

**Why it's universal:** Any company that touches credit — issuing, BNPL, merchant lending, or card limits — needs a risk model. The regulatory and business incentives align perfectly.

---

## 3. Document AI for KYC and Onboarding

CRED, Paytm, Capital One, and Stripe all use document classification and extraction pipelines for onboarding — classifying document types (PAN, Aadhaar, bank statements, income proofs), extracting structured fields, and running verification checks. The ML stack typically involves a document classification head, an OCR/layout model (LayoutLM or Donut-style), and a downstream NER or extraction layer. Stripe's real-time ID verification and Paytm's merchant onboarding Document AI are essentially the same pipeline applied to different customer segments.

**Why it's universal:** Regulated financial entities cannot onboard customers or merchants without identity and income verification. Automating this at scale is both a cost and a compliance play.

---

These three — **Graph Fraud**, **Credit Risk**, and **Document AI** — form what you could call the foundational ML triad in fintech. Every serious player has all three, and the differentiation is in the sophistication of execution rather than the choice of use case.
