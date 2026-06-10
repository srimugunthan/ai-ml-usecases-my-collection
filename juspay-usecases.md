Juspay integrates Machine Learning (ML) primarily to optimize the "plumbing" of the payment ecosystem—focusing on success rates, latency, and fraud prevention. Given your background in high-performance AI and agentic RAG, you’ll find their approach to **Intelligent Orchestration** particularly interesting, as it functions as a real-time decisioning engine for billions of transactions.

### 1. Predictive Smart Routing
Juspay’s core ML application is its dynamic routing engine. Instead of relying solely on static rules, it uses predictive models to decide which Payment Service Provider (PSP) or gateway to use for a specific transaction.

* **Failure Prediction:** Their models analyze real-time data from hundreds of thousands of concurrent sessions to predict if a gateway is undergoing "silent" downtime or degraded performance. They claim a **95% accuracy** in predicting payment failures before they occur.
* **Ranking Logic:** The engine ranks eligible PSPs based on over 35 parameters, including historical success rates, real-time latency (aiming for $< 15\text{ms}$), and current processing costs.
* **Adaptive 3DS:** It intelligently routes between 3DS 2.0 and older flows based on the issuer's success probability, shifting liability while minimizing friction.

### 2. HyperSense (AIOps for Payments)
Juspay uses a dedicated observability stack called **HyperSense** that employs ML for automated reconciliation and anomaly detection.

* **Log Parsing:** It uses ML to ingest unstructured and diversified payment reports from various banks and PSPs, transforming them into structured data for 3-way reconciliation.
* **Anomaly Detection:** It monitors the payment funnel in real-time. If the conversion rate for a specific bank-BIN combination drops below a statistical threshold, the system automatically triggers alerts or reroutes traffic.

### 3. Fraud and Risk Management (FRM)
While Juspay is aggregator-agnostic, it provides an ML-driven FRM layer that merchants can plug into.

* **Behavioral Analysis:** It monitors transaction patterns to identify unusual activities, such as high-velocity card testing or account takeovers.
* **Velocity Checks:** Predictive models evaluate the risk of a transaction based on the user's historical behavior and device fingerprinting.

### 4. Personalization & Checkout Optimization
On the frontend (HyperCheckout), ML is used to reduce cognitive load and increase conversion:

* **QuickPay:** This feature uses ML to predict a user's preferred payment method based on past behavior (80% of users stick to one habitual method). It then surfaces this option as a "1-click" experience.
* **Native OTP:** By using ML to auto-read and submit OTPs within the app (avoiding bank page redirections), they’ve seen conversion uplifts of up to **10%**.

### 5. Tech Stack Context
For someone with your technical expertise, it’s worth noting that Juspay builds a significant portion of its infrastructure using **PureScript** and **Haskell**. Their ML models are often integrated into these high-concurrency environments to ensure the "intelligence" doesn't introduce latency into the critical payment path.

---
**Summary Table: ML impact at Juspay**

| Feature | ML Application | Key Metric |
| :--- | :--- | :--- |
| **Smart Routing** | Dynamic gateway selection | +10% Authorization Rates |
| **Failure Prediction** | Outage and downtime detection | 95% Prediction Accuracy |
| **HyperSense** | AIOps & Anomaly Detection | Real-time observability |

--
The generic results aren't helpful. Let me search specifically for Juspay.Good enough to give a thorough, Juspay-specific answer. Let me compile it.

Here's a breakdown of Juspay's AI/ML use cases, drawing from their engineering docs, product pages, and blog content:

---

## 1. Dynamic Gateway Routing — Multi-Armed Bandit / RL

This is Juspay's most technically interesting ML use case. Dynamic gateway ordering is an alternative to rule-based ordering and inputs real-time success rates into consideration for each combination of payment instruments, type of transaction, network, platform, transaction origin country, etc. It leverages Reinforcement Learning and Statistical Distribution, and the problem of selecting the best gateway is mapped to a Non-stationary Multi-Armed Bandit (MAB) problem with Delayed Feedback, where each gateway is an "arm."

The AI/ML algorithm constantly monitors and learns high payment failures across the payment ecosystem along with merchant context and makes fully automatic routing decisions. It is granular — taking into account all possible combinations of payment gateways and payment methods — platform-level, looking at global information across merchants, and real-time, identifying potential downtimes within a minute.

**ML angle:** Non-stationary MAB with delayed rewards is a hard problem — authorization outcomes arrive seconds to minutes after routing decisions, and PSP failure patterns are non-stationary (sudden downtimes, issuer-specific outages). Contextual bandits with Thompson Sampling or UCB are common approaches here.

---

## 2. Smart Retries for Revenue Recovery

Juspay's Revenue Recovery product minimizes churn using data and machine learning, and maximizes success rates with smart retry strategies with configurable retry logic.

This is the subscription/recurring payments analog of what Stripe's Adaptive Acceptance does — an ML classifier that decides *when* and *how* to retry failed transactions (timing, channel, PSP selection) to maximize recovery probability without triggering issuer blocks.

---

## 3. ML-Driven Success Rate Optimization

Success rate based routing uses ML-driven optimization that learns from authorization outcomes across PSPs and dynamically adjusts routing to maximize approval rates. This is distinct from the MAB routing — it's a supervised/semi-supervised model trained on historical authorization outcomes to predict the best PSP for a given transaction fingerprint.

---

## 4. HyperSense — AIOps for Payment Analytics

HyperSense is an AI-driven payment analytics dashboard with features like anomaly detection, automated root cause analysis (RCA), and a conversational interface. It simplifies analysis of payment processing costs and trends and caters to various user personas — from CTOs and CFOs to data analysts — allowing each to view data from their unique perspective.

HyperSense ingests unstructured, diversified payment reports from multiple sources and formats, transforming them into structured, actionable analytics output.

**ML angle:** Anomaly detection over time-series payment metrics (success rates, latency, cost per transaction), automated RCA via causal inference or decision trees, plus an LLM-based conversational layer on top.

---

## 5. Adaptive 3DS Authentication

Juspay's 3DS product uses ML to decide when to trigger strong authentication vs. request exemptions. Dynamic routing evaluates real-time signals including uptime, performance, card brand, geography, processing costs, time of day/week patterns, and fraud risk scores — no longer depending on if-then logic but adapting instantly to current conditions. Applied to 3DS, this translates to a risk-scoring model that determines frictionless vs. challenge flows, shifting liability while minimizing customer drop-off.

---

## 6. Agentic Commerce Infrastructure

Juspay's leadership points to building guard rails for agentic commerce — where AI agents search, optimize costs, book entire trips, and handle payment end-to-end. The reference point is India's experience with Visa/Mastercard biometric authentication that set strict limits like transaction caps or frequency limits to build consumer confidence.

This is an emerging area for them — the ML problems here involve agent intent verification, anomaly detection on agent-initiated transactions (versus human-initiated), and fraud scoring for non-human payment actors.

---

## Summary Table

| Use Case | ML Technique | Business Metric |
|---|---|---|
| Dynamic Gateway Routing | Non-stationary MAB / RL | Authorization rate |
| Smart Retries | Retry timing classifier | Revenue recovery |
| Success Rate Optimization | Supervised ranking model | PSP approval rates |
| HyperSense AIOps | Anomaly detection + LLM | Cost observability |
| Adaptive 3DS | Risk scoring / binary classifier | Fraud vs. friction tradeoff |
| Agentic Commerce | Anomaly detection, intent classification | Fraud prevention |

---

**From your positioning perspective:** Juspay's MAB routing engine, adaptive 3DS risk scoring, and HyperSense anomaly detection are all strong parallels to what you've built — the fraud GNN work, noise-robust loss functions, and the ATM replenishment optimization all map cleanly onto these problem spaces if you're benchmarking or targeting roles in this ecosystem.

--
# References:
Alloy (2026) Financial fraud detection using machine learning. Available at: https://www.alloy.com/blog/data-and-machine-learning-in-financial-fraud-prevention (Accessed: 14 April 2026).

Ganesh, A. (2024) ‘How can AI Ops in payment analytics solve cost observability for merchants?’, Juspay Blog, September. Available at: https://juspay.io/blog (Accessed: 14 April 2026).

Juspay (2025) A control-theoretic approach to dynamic payment routing for success rate optimization. arXiv:2510.16735. Available at: https://arxiv.org/pdf/2510.16735 (Accessed: 14 April 2026).

Juspay (2025) DOTP 2.0 - Seamless Card Payments. Available at: https://juspay.io/en-in/blog/dotp-2-0-seamless-card-payments (Accessed: 14 April 2026).

Juspay (2026) Quick Pay - Juspay Developer Docs. Available at: https://juspay.io/sea/docs/quick-pay-sea/overview (Accessed: 14 April 2026).

Kuppili, S. and Sharma, D. (2025) ‘Payment Orchestration: An Operating System for Streamlining Payments’, Juspay Blog, January. Available at: https://juspay.io/blog (Accessed: 14 April 2026).

Mishra, M. (2026) ‘Agentic Commerce: Understanding the Shift and What It Means for the Payments Ecosystem’, Juspay Blog, January. Available at: https://juspay.io/blog (Accessed: 14 April 2026).

ResearchGate (2022) An AI-powered Smart Routing Solution for Payment Systems. Available at: https://www.researchgate.net/publication/357815497_An_AI-powered_Smart_Routing_Solution_for_Payment_Systems (Accessed: 14 April 2026).
| **QuickPay** | User preference modeling | 1.2x better success rates |
