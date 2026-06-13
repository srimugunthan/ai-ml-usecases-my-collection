Here's a structured breakdown of AI/ML use cases at MakeMyTrip:

---

## Search & Ranking

- **Flight search ranking** — personalized re-ranking of flight results based on user history, price sensitivity, airline preference, travel class patterns
- **Hotel search ranking** — learning-to-rank models on hotel inventory using relevance signals (location match, amenity fit, review scores, booking velocity)
- **Query understanding** — NLP to parse ambiguous travel queries ("beach vacation under 20k next month", "flights to somewhere cold")
- **Autocomplete and search suggestion** — ML-driven suggestions that go beyond prefix match to intent prediction
- **Cross-sell search** — surfacing hotel when user searches flight, and vice versa, based on predicted bundling propensity

---

## Pricing & Yield Management

- **Dynamic fare display** — predicting whether a shown fare will increase or decrease to nudge booking urgency ("prices rising — book now")
- **Hotel rate recommendation** — ML models that recommend optimal nightly rates to hotel partners based on demand signals, competitor pricing, seasonality
- **Holiday package pricing** — dynamic pricing of curated packages based on component availability and demand
- **Ancillary pricing** — seat selection, meal, insurance add-on pricing optimization
- **Fare prediction** — predicting future airfare movement for user-facing "wait or book" features

---

## Personalization & Recommendations

- **Destination recommendation** — collaborative filtering + content-based models suggesting destinations based on travel history, peer group behavior, seasonal trends
- **Hotel recommendations** — embedding-based similarity (your Hotel2Vec angle) for "similar properties" and homepage personalization
- **Ancillary upsell recommendation** — predicting which users are likely to buy travel insurance, cab transfers, forex
- **Holiday package recommendation** — matching users to curated packages based on past travel style, group composition, budget signals
- **Re-engagement recommendations** — predicting the right destination/deal to surface in push notifications and email to lapsed users

---

## Demand Forecasting

- **Route-level demand forecasting** — predicting search and booking volume by route and travel date for inventory planning and marketing budget allocation
- **Hotel demand forecasting** — property-level occupancy prediction for dynamic pricing and revenue management
- **Seasonal surge prediction** — identifying emerging demand spikes (new direct flight routes, visa relaxation events, festivals) before they hit mainstream
- **Cancellation forecasting** — predicting cancellation probability at booking time for overbooking strategy and refund reserve planning

---

## Fraud & Trust

- **Payment fraud detection** — real-time scoring of transactions at checkout (stolen cards, account takeover)
- **Fake booking detection** — identifying bookings made to block inventory or trigger promotional credits fraudulently
- **Coupon and promo abuse** — detecting multi-accounting, referral fraud, cashback abuse
- **Refund fraud** — classifying refund requests likely to be fraudulent (claim of no-show when travel occurred)
- **Fake review detection** — NLP + graph-based detection of inauthentic hotel or experience reviews
- **Bot traffic detection** — identifying scraper bots and fare aggregators hitting their search APIs

---

## Customer Support Automation

- **Cancellation and refund automation** — LLM-powered agents that handle the full cancellation + refund workflow without human intervention
- **Rebooking agent** — agentic systems that proactively rebook affected passengers when flights are cancelled or delayed
- **Complaint classification and routing** — NLP to classify support tickets and route to the right team with predicted resolution SLA
- **Policy QA** — LLM that answers "what is the cancellation policy for this booking" from structured policy data
- **Sentiment analysis on reviews and support chats** — tracking hotel and airline quality signals from unstructured text

---

## Travel Planning & Discovery

- **Itinerary generation** — LLM-based agents that generate day-by-day itineraries given destination, duration, group type, budget (your Travel Agent project)
- **Trip inspiration** — generative content for destination pages, "best time to visit", "what to do in 3 days in Goa"
- **Voice travel assistant** — voice-driven search and booking for mobile-first, tier-2/3 India users
- **Visa and documentation assistant** — LLM that tells users exactly what documents they need for a destination based on nationality and travel purpose
- **Travel budget estimator** — ML model that estimates total trip cost (flights + hotel + activities + meals) for a destination and travel style

---

## Supply Side (Hotel & Airline Partner Tools)

- **Revenue management dashboard for hotels** — ML-driven rate recommendations and occupancy forecasting for hotel partners on their extranet
- **Content quality scoring** — ML model that scores hotel listings on completeness, photo quality, description richness and prompts partners to improve
- **Review response generation** — LLM that drafts hotel responses to guest reviews
- **Demand signals for airline partners** — sharing aggregated search demand data to help airlines optimize schedules and pricing

---

## Infrastructure & Operations

- **Search latency optimization** — ML-driven caching and pre-computation of likely search queries
- **A/B test analysis automation** — ML models that detect significance and interaction effects in product experiments faster than classical statistics
- **Ad spend optimization** — bidding models for Google/Meta performance marketing campaigns, predicting conversion probability at keyword/audience level
- **Seat map and availability prediction** — predicting seat availability changes on flights to time booking recommendations

---

## Emerging / LLM-era

- **Conversational travel booking** — end-to-end chat interface where users describe their trip and the agent handles search, comparison, and booking
- **Multimodal destination discovery** — users upload photos of places they want to visit and the system identifies and recommends similar destinations
- **Dynamic packaging agent** — agentic system that assembles flight + hotel + activity bundles in real time based on user constraints
- **Travel document extraction** — VLM for parsing itineraries, visas, boarding passes from photos (your FinVision angle applies here)

---


| Conversational booking | Travel Plan Agent + LLM API tuning |

The demand forecasting, pricing, and supply-side tooling areas are the gaps in your current portfolio relative to MMT's problem space — worth keeping in mind if you want to build something MMT-specific.
