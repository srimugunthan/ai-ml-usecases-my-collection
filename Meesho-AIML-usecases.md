Here's a structured overview of Meesho's AI/ML use cases, spanning customer-facing, seller-facing, platform infrastructure, and research:

---

## Meesho AI/ML Use Cases

### 1. BharatMLStack — In-House ML Platform

This is arguably Meesho's biggest infrastructure bet. Developed over the past two years, BharatMLStack is Meesho's internal ML platform that processed ~1.91 PB of data daily on average in FY2025, resulting in 66.90 trillion feature retrievals and 3.12 trillion real-time inferences at peak.

BharatMLStack was purpose-built to support real-time ML applications across user and seller-facing systems, with modular components supporting fraud detection, personalized search, ranking systems, and automated product tagging. Meesho open-sourced it in mid-2025, making it available to the broader Indian startup ecosystem.

---

### 2. Search, Ranking, and Feed Personalization

Meesho uses state-of-the-art ML and deep learning models for recommendation systems and precision-driven ranking algorithms, crafting tailored experiences that align with each user's unique preferences — particularly important given the platform's user diversity across geographies and languages.

Meesho also built a generalized feed ranker using Amazon SageMaker inference, developed by a team with backgrounds spanning recommender systems, NLP, and image AI from institutions including IISc and IIT.

---

### 3. LLMs for Vernacular Search and Query Understanding

LLMs provided significant gains in handling long-tail search queries, particularly for Meesho users from Tier 3+ cities — correcting misspellings, removing redundant words, and translating queries from Indian languages to English. This improved retrieval and ranking efficacy across the board.

LLMs also proved superior for address translation — intelligently determining when to translate versus transliterate names, and handling code-mixed addresses effectively, reducing delivery failures.

---

### 4. Customer Review Synthesis

LLMs are used to generate comprehensive summaries of customer reviews, allowing users to quickly gather information about products. They extract key points and sentiments around different product aspects from thousands of reviews — surpassing previous NLP approaches.

---

### 5. Seller-Facing AI: Catalog and Pricing

AI-powered solutions simplify the listing process for small sellers who lack expertise in pricing and cataloging. A seller can click an image and fill in essential details to list a product. Meesho also uses AI to guide sellers on correct pricing and marketing strategies, which are unique to each seller.

---

### 6. Fraud Detection

Meesho uses AI to identify and stop fraudulent transactions, providing buyers and sellers with a secure and reliable platform. The BharatMLStack feature store is specifically designed to support fraud detection use cases at low latency.

---

### 7. Address Resolution and Delivery Optimization

Meesho uses AI capabilities to resolve issues like incomplete addresses and minimize delivery failures — a particularly hard problem in India where addresses are unstructured and highly variable across languages and regions.

---

### 8. Developer Productivity via GenAI

Meesho adopted GitHub Copilot across its engineering teams. The tool transforms natural language comments into functional code snippets, accelerating coding speed and minimizing errors. Developer surveys showed significant time savings and a high likelihood of recommending Copilot — reflecting enhanced development experience.

---

**Relevance to your work:** The BharatMLStack feature store architecture (real-time feature serving at 66 trillion retrievals/day) is a strong system design reference for your MLOps and portfolio stress-testing agent work. Meesho's LLM-for-vernacular-search problem — code-mixed queries, transliteration vs. translation decisions, Tier 3 long-tail users — is also an interesting application domain that maps loosely onto noise-robust learning challenges.

---

---
Meesho operates as one of India's largest e-commerce marketplaces, specifically targeting first-time internet users, value-conscious buyers, and small-scale sellers across Tier 2, Tier 3, and rural markets. Because their demographic relies heavily on non-text discovery, low-cost alternatives, and unbranded items, their AI/ML use cases are engineered to handle high operational ambiguity, messy data, and extreme scale.

Meesho leverages its custom **BharatMLStack** to manage real-time embedding searches, low-latency model serving, and high-throughput feature retrieval.

---

### 1. Real-Time Discovery & Feed Personalization

* **Generalized Feed Ranker (GFR):** Unlike premium e-commerce apps where search queries dominate, over 75% of orders on Meesho are influenced by personalized feeds. The GFR processes individual browsing history, geographic parameters, and time-sensitive contextual cues via Amazon SageMaker and Dask-on-EMR clusters. The underlying Learning to Rank (LTR) models continuously output the Probability of Click ($P_{\text{CTR}}$) and Probability of Purchase ($P_{\text{CVR}}$) to balance trending products (*exploit*) with novel discovery (*explore*).
* **Low-Latency Online Feature Store:** To handle over 1 million Queries Per Second (QPS) during mega sales without performance degradation, Meesho engineered a custom **Model Proxy** graph-driven feature retrieval system. They moved away from JVM-based setups to GoLang and replaced Cassandra with ScyllaDB and Dragonfly caching to resolve entity relationships (e.g., user $\times$ category affinities) dynamically.

### 2. Multi-Lingual Voice & Vernacular Commerce

* **Vaani (Voice-Led Shopping Assistant):** A massive portion of Meesho's user base struggles with text-based search queries or typing in English/Hindi. To lower this barrier, Meesho introduced *Vaani*, an AI-powered voice assistant capable of processing code-mixed vernacular Indian languages and heavy dialects. It scales to handle over 60,000 voice interactions daily, leading to a measurable 22% improvement in conversion rates for digitally native or semi-literate shoppers.
* **Vernacular Address Parsing:** A notorious operational challenge in India is the lack of standardized postal addresses (e.g., "Behind Hanuman temple, next to the yellow house"). Meesho uses custom NLP models to parse highly unstructured, semi-vernacular text strings into accurate, structured delivery coordinates, significantly reducing last-mile delivery failures and courier return-to-origin (RTO) rates.

### 3. Trust, Quality Control, and Counterfeit Mitigation

* **Project Vishwas (Systemic Fraud Detection):** In late 2023, rapid growth led to a surge in counterfeit products and rogue sellers. Meesho deployed upgraded AI verification pipelines under *Project Vishwas* to block automated scam attempts. The system utilizes:
* **Computer Vision:** To flag photoshopped logos and detect visual similarities across unauthorized replica goods.
* **NLP for Evasion:** To catch keyword evasion tactics (e.g., creative spacing, intentional misspellings like "R0lex" or "A d i d a s").
* **Anomalous Pricing Models:** To automatically flag extreme outliers (e.g., an unbranded supplier listing a "genuine leather jacket" for ₹150).


* **Behavioral Fraud Ring Analysis:** The platform tracks graph-based behavioral patterns to identify malicious seller networks that spin up hundreds of transient, temporary SIM card accounts to bypass mobile verification and manipulate review scores.

### 4. Semantic & Visual Search

* **Reverse Image Search (Visual Matching):** Because many users see products on social media platforms like Instagram or WhatsApp before buying, Meesho relies heavily on visual representation learning. Users upload screenshots, and deep convolutional neural networks (CNNs) map the images into a high-dimensional vector space to return visually identical or highly similar products from the catalog instantly.
* **Search Intent Disambiguation:** Traditional keyword matching fails when users type phonetic words (e.g., writing "chappal" instead of "slippers"). Meesho's search backend uses semantic embeddings to map raw, messy query strings directly to the intended product category rather than relying on exact string matches.

### 5. Autonomous Internal Workflows

* **AI-Driven Software Development Lifecycle (SDLC):** Meesho has deeply embedded generative AI into its internal engineering operations, with over 70% of production code featuring AI generation or assistance. Large Language Models (LLMs) are leveraged for autonomous unit test generation, pull request reviews, deployment bug fixing, and continuous infrastructure telemetry monitoring.
* **Optimized Inference Infrastructure:** To run these massive generative models cost-effectively without inflating cloud spend, Meesho built an internal runtime layer optimizing metrics like **Time to First Token (TTFT)** using prefix caching and **Inter-Token Latency (ITL)** via Triton Inference Server and vLLM architectures.

---

> **The Tech Stack Trade-off:** While many enterprises adopt off-the-shelf commercial LLM APIs, Meesho’s data science strategy focuses heavily on open-source model fine-tuning (like Llama architectures) combined with high-performance C++/Go-based inference proxies to keep compute costs down while maintaining low-latency serving across millions of concurrent sessions.

---
