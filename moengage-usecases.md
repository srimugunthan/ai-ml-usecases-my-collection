Here's a comprehensive breakdown of the AI/ML use cases in MoEngage, organized by capability area. MoEngage bundles all its AI under the brand **Merlin AI** (rebranded from Sherpa AI in late 2025).

---

## Merlin AI — MoEngage's AI/ML Suite

### 1. Predictive AI

**Predictive Segmentation / Predictions**
MoEngage Predictions powered by Merlin AI offers actionable forecasts related to customer behaviour, including its Predictive Segments feature which predicts customer behavior — conversions, churn, and retention. It can predict any customer behaviour including conversion, renewals, churn, uninstalls, and more.

**Best Time to Send (BTS)**
BTS predicts the optimal time for each customer and channel to maximize engagement and response rates. This feature helped JibJab achieve an 82% higher click-through rate.

**Product Recommendations**
Merlin AI recommends relevant products to customers on any channel. A UK budget hotel brand used this to craft post-purchase upsell strategies, boosting revenue by 354%.

---

### 2. Generative AI

**Merlin AI Copywriter**
Merlin AI is a generative and predictive AI engine that helps marketers create content (email copies or subject lines) and creatives within minutes. Merlin learns from past campaigns to improve its copies — whether to avoid specific keywords or optimize tone, based on conversion goals.

**Merlin AI Designer / Studio**
Merlin AI Designer now includes omni-channel image generation. MoEngage added support for multiple aspect ratios (16:9, 4:3, 1:1, 3:4, 9:16) for email, on-site messages, and social media. Social-optimized formats cover TikTok, Reels, Instagram, and LinkedIn.

**Jinja Assistant**
MoEngage enhanced Merlin AI Jinja Assistant to simplify the creation of complex logic and personalized content.

---

### 3. NLP-Based Segment Building

**Segment Assist**
Merlin AI Segment Assist lets you create complex audience segments in seconds using simple natural language prompts, with options to improve targeting over time.

**Flow Assist**
Merlin AI Flow Assist allows users to articulate a desired customer journey as a natural language prompt, and it instantly translates the concept into a tangible, ready-to-deploy flow.

---

### 4. Decisioning Agents (Agentic AI)

**Campaign Decisioning Agent**
The Campaign Decisioning agent delivers true 1:1 personalization by dynamically selecting the product, channel, message, and timing for each customer. By defining campaign objectives (like driving repeat purchases) and operational guardrails (such as budget limitations), the Decisioning Agent draws on comprehensive customer profiles and real-time behavioral data to make these choices.

**Offer Decisioning Agent**
MoEngage's Offer Decisioning agent uses AI to deliver 1:1 offers to each customer on the app, web, and beyond.

---

### 5. Journey & Path Optimization

**Intelligent Path Optimizer (IPO)**
IPO tests up to 5 different paths and automatically directs customers to the best-performing path.

**Multi-Armed Bandit Experiments**
MoEngage uses multi-armed bandit experiments to determine the best journey path, including the channels and timing, for each customer.

---

### 6. Analytics & Insights

Merlin AI is also used to run various A/B/n tests, and it learns from customer behavior to predict the best channels to communicate with customers, dynamically selecting the most optimal path to conversion in a customer journey. The platform also tracks ROI-driven insights, click-through and open rates, and North Star metrics to help teams focus on growth drivers.

---

## Summary Table

| Category | Use Case |
|---|---|
| Predictive ML | Churn prediction, conversion propensity, retention scoring |
| Predictive ML | Best time to send per customer |
| Recommendation | Product/offer recommendation across channels |
| Generative AI | Email copywriting, subject line generation |
| Generative AI | Campaign creative / image generation |
| NLP | Natural language segment building |
| NLP | Natural language flow/journey creation |
| Agentic AI | 1:1 Campaign decisioning (channel + message + timing) |
| Agentic AI | Offer decisioning |
| Optimization | Intelligent path optimizer (multi-path A/B) |
| Optimization | Multi-armed bandit for journey paths |
| Analytics | Campaign ROI attribution, engagement analytics |

---

The **Decisioning Agent** architecture and the **Predictive Segments** pipeline would be the most technically interesting areas — both involve real-time inference at scale with online learning components, which maps well to the fraud/AML work you've done.
