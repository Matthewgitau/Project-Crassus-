# Project-Crassus-
Tackling dynamic pricing and the greed of major retailers whilst empowering the little guys by encouraging a more competitive marketplace. If we make money we hope to hire talent to produce the best features and very affordable prices!
> **The open-source mobile platform helping local shops and consumers beat big-store "Surge Pricing".**

Large retail corporations are increasingly using automated AI systems to constantly change prices based on supply, demand, and user data. This means everyday items cost more when you need them most. 

**Project-Crassus** is an open-source project designed to fix this. We are building a mobile application that tracks these price changes, gives independent shops a free way to run enterprise-grade loyalty schemes, and drives customers back to local businesses.

---

## 🎯 The Competitor Landscape (What We Are Up Against)
To beat corporate pricing algorithms, we have to study how they work. Developers should research these enterprise platforms to understand how big retail handles automated data tracking:

*   **Omnia Retail / Retailgrid:** These corporate engines crawl competitor websites hourly to adjust prices automatically and maximize profit margins.
*   **Electronic Shelf Labels (ESLs):** Large chains use digital price tags linked to internal algorithms. This allows them to instantly change grocery prices during peak hours.

---

## 🏗️ System Architecture Layout

To protect our data and keep operational costs incredibly low, the project uses a highly secure, serverless backend structure.

Use code with caution.
┌────────────────────────────────────────────────────────┐
│                   FLUTTER MOBILE APP                   │
│  (Displays local deals, handles free loyalty QR codes) │
└───────────────────────────┬────────────────────────────┘
│
│ Secure HTTPS Requests
▼
┌────────────────────────────────────────────────────────┐
│                SUPABASE EDGE FUNCTIONS                 │
│  (Acts as a secure firewall. Hides all master keys)   │
└───────────────────────────┬────────────────────────────┘
│
│ Internal Data Query
▼
┌────────────────────────────────────────────────────────┐
│              SUPABASE POSTGRES DATABASE                │
│  (Stores price logs. Uses Row-Level Security [RLS])    │
└────────────────────────────────────────────────────────┘

### Why This Architecture Works:
*   **No Exposed Keys:** The Flutter mobile application never connects directly to the raw database. It only speaks to secure **Edge Functions**. If someone extracts the app code, they will never find our database passwords or hidden keys.
*   **Row-Level Security (RLS):** This internal database rule guarantees that users can only view or edit their own profile information, preventing malicious data scraping or hacks.

---

## 🧭 Step-by-Step Implementation Roadmap

We have broken this project down into small, structured milestones that a small team can build systematically.

### Milestone 1: Setup & Mobile Foundations
*   [ ] **Task 1.1:** Initialize a fresh Flutter project repository and configure standard folder paths (`/lib/views`, `/lib/controllers`, `/lib/models`).
*   [ ] **Task 1.2:** Configure a public Supabase instance, create basic data tables for users and shop profiles, and explicitly turn ON Row-Level Security (RLS).
*   [ ] **Task 1.3:** Build a clean Flutter UI interface containing a dashboard screen, a profile page, and a tab for scanning digital QR codes.

### Milestone 2: Core White-Label Features & Discovery
*   [ ] **Task 2.1: Geo-Location Services:** Integrate native device GPS tracking to locate users and accurately measure their distance to surrounding shops.
*   [ ] **Task 2.2: Explore Page:** Design a discovery feed displaying nearby, newly registered independent shops based on the user's geographic location.
*   [ ] **Task 2.3: Offers & Deals Hub:** Create dedicated interface sections for vendors to publish active discounts, promotions, and stable-price alternatives.

### Milestone 3: Loyalty & Vendor Support Tools
*   [ ] **Task 3.1: QR Loyalty Scheme:** Build a digital card generator that spits out a standardized QR code containing an encrypted User ID for zero-cost point collection.
*   [ ] **Task 3.2: Digital Tip Jars:** Create an optional digital tipping interface allowing users to support their favorite small business employees directly through the app.
*   [ ] **Task 3.3: Vendor Web App:** Build a basic web dashboard tool so store owners can scan customer QR codes and manage their live deals using any cheap tablet or phone.

### Milestone 4: Crowd-Sourced Price Tracking
*   [ ] **Task 4.1:** Design a user-friendly form where shoppers can quickly log the price of essential items (like milk or bread) while visiting major supermarkets.
*   [ ] **Task 4.2:** Write a backend calculation script inside Supabase Edge Functions to automatically detect sudden corporate surge pricing spikes.

---

## 📈 Sustainable Monetization Plan
To hire full-time developers and maintain global infrastructure without charging local shops an arm and a leg, Project-Crassus uses three low-impact revenue streams:

1.  **Low-Fee Payment Processing (Optional):** If a local vendor chooses to accept in-app mobile pre-orders or use the built-in tip jar features, we take a tiny, highly competitive transaction micro-fee (e.g., 0.5% to 1%) to directly fund core platform developers.
2.  **Anonymous Market Insights:** We can package our clean, aggregated, and fully anonymous supermarket price trends into industry reports. These reports can be sold to consumer advocacy groups and independent market analysts.
3.  **Community Crowdfunding:** Utilizing platforms like Open Collective and GitHub Sponsors allows people who care about ethical retail models to financially back our hosting and engineering efforts.

---

## 🤝 How to Onboard & Contribute
We are looking for passionate engineers, designers, and data organizers to join our core syndicate. Check out our open task board, pick a ticket from Milestone 1, and submit a pull request!
