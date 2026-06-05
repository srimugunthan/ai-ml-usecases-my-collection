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
