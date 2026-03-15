# Craft Mode - Fully Automated AI Agency Architecture

## Executive Summary

This document outlines a complete end-to-end automation architecture for Craft Mode, an AI-powered digital agency. The goal is to minimize manual intervention while maintaining quality and customer satisfaction.

**Target State:** 90%+ automation across the entire customer journey

---

## System Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         MARKETING & ATTRACTION                              │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐          │
│  │   SEO    │ │  Social  │ │   Ads    │ │ Content  │ │ Referral │          │
│  │  Engine  │ │  Media   │ │  Engine  │ │  Engine  │ │  System  │          │
│  └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘          │
└───────┼────────────┼────────────┼────────────┼────────────┼────────────────┘
        └────────────┴────────────┴────────────┴────────────┘
                                   │
                                   ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           LEAD CAPTURE HUB                                  │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐       │
│  │   Website    │ │    Email     │ │    Chat      │ │    Phone     │       │
│  │    Form      │ │   Parser     │ │     AI       │ │   (VoIP)     │       │
│  └──────┬───────┘ └──────┬───────┘ └──────┬───────┘ └──────┬───────┘       │
└─────────┼────────────────┼────────────────┼────────────────┼────────────────┘
          └────────────────┴────────────────┴────────────────┘
                                   │
                                   ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                        CENTRAL ORCHESTRATOR (n8n)                           │
│                                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │Lead Scoring │  │  CRM Sync   │  │ Notification│  │  Analytics  │        │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────────────────────────┬───────────────────────────────────────┘
                                      │
                    ┌─────────────────┼─────────────────┐
                    ▼                 ▼                 ▼
┌──────────────────────┐ ┌──────────────────┐ ┌──────────────────┐
│   QUALIFICATION      │ │    DISCOVERY     │ │    PROPOSAL      │
│       ENGINE         │ │     ENGINE       │ │     ENGINE       │
│  ┌────────────────┐  │ │ ┌──────────────┐ │ │ ┌──────────────┐ │
│  │AI Qualification│  │ │ │Requirements  │ │ │ │  Template    │ │
│  │   Chatbot      │──┼─┼▶│   Analysis   │─┼─┼▶│   Engine     │ │
│  └────────────────┘  │ │ └──────────────┘ │ │ └──────────────┘ │
└──────────────────────┘ └──────────────────┘ └──────────────────┘
                                                       │
                                                       ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           PAYMENT & CONTRACTS                               │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐       │
│  │   Stripe     │ │   PandaDoc   │ │   Calendly   │ │   Notion     │       │
│  │   Payment    │ │  E-Signature │ │  Scheduling  │ │  Project DB  │       │
│  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘       │
└─────────────────────────────────────┬───────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         AI DELIVERY PIPELINE                                │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                    PROJECT MANAGEMENT SYSTEM                        │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  │   │
│  │  │  Design  │ │   Code   │ │  Content │ │  Review  │ │  Deploy  │  │   │
│  │  │  (v0)    │ │ (Cursor) │ │ (Claude) │ │  (AI)    │ │(Vercel)  │  │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────┘  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                    AUTOMATED COMMUNICATION                          │   │
│  │  Status Updates │ Milestone Alerts │ Revision Requests │ Feedback   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                          DELIVERY & SIGNOFF                                 │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐       │
│  │   Final      │ │   Signoff    │ │  Handover    │ │  Warranty    │       │
│  │   Payment    │ │  Collection  │ │   Docs       │ │  Period      │       │
│  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘       │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         POST-DELIVERY AUTOMATION                            │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐       │
│  │  Testimonial │ │  Referral    │ │ Maintenance  │ │  Upsell      │       │
│  │   Request    │ │   Program    │ │   Offers     │ │  Campaign    │       │
│  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘       │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Phase 1: Marketing & Attraction Automation

### 1.1 SEO Engine

**Purpose:** Generate organic traffic through automated content

**Option A: Content at Scale (Budget: $100-500/mo)**
- **Tool:** Jasper AI / Copy.ai + Surfer SEO
- **Process:**
  1. AI identifies trending keywords
  2. Generates blog posts automatically
  3. Optimizes for SEO scores
  4. Publishes to website
- **Pros:** Fast setup, good quality
- **Cons:** Monthly subscription, less control

**Option B: Self-Hosted Pipeline (Budget: $50/mo + API costs)**
- **Stack:** Claude API + n8n + WordPress/Website
- **Process:**
  1. n8n fetches keyword opportunities (via API)
  2. Claude generates articles
  3. n8n publishes to blog
  4. Auto-generates meta tags, schema
- **Pros:** Full control, lower long-term cost
- **Cons:** More setup required

**Option C: Hybrid Human+AI (Budget: $500-1000/mo)**
- **Stack:** AI draft + human editor + Ghost/WordPress
- **Process:** AI generates, human refines, schedules publishing
- **Pros:** Highest quality
- **Cons:** Requires human time

**Recommended: Option B** (self-hosted for full automation)

**Implementation:**
- n8n workflow runs weekly
- Fetches keywords from Google Search Console API
- Generates 2-4 blog posts
- Auto-publishes to /blog section
- Submits to Google for indexing

---

### 1.2 Social Media Engine

**Purpose:** Maintain presence on LinkedIn, Twitter/X without manual posting

**Option A: Buffer/Hootsuite (Budget: $15-100/mo)**
- **Pros:** Easy UI, analytics
- **Cons:** Limited AI generation

**Option B: n8n + AI Generation (Budget: API costs only)**
- **Stack:** n8n + Claude + Social Media APIs
- **Process:**
  1. n8n triggers daily at 9am
  2. Claude generates post from content calendar
  3. n8n publishes to LinkedIn/Twitter
  4. Tracks engagement
- **Pros:** Fully automated, AI-generated content
- **Cons:** API rate limits

**Option C: Repurpose.io (Budget: $25/mo)**
- Automatically repurposes blog content into social posts
- **Pros:** Set and forget
- **Cons:** Less original content

**Recommended: Option B** (full automation)

**Implementation:**
- Content calendar in Notion/Airtable
- n8n reads calendar daily
- Generates post variations
- Publishes with relevant hashtags

---

### 1.3 Paid Ads Engine

**Purpose:** Generate immediate leads via Google Ads, LinkedIn Ads

**Option A: Fully Managed (Budget: Agency fee $500+/mo + ad spend)**
- Hire agency to manage
- **Pros:** Expert optimization
- **Cons:** Expensive, less automated

**Option B: Smart Campaigns + n8n (Budget: Ad spend only)**
- Use Google's Smart Campaigns (automated bidding)
- n8n pulls lead data
- **Pros:** Low maintenance
- **Cons:** Less control

**Option C: Hybrid Approach (Budget: $200/mo tools + ad spend)**
- Use Google Ads API + n8n for automated rules
- Auto-pause underperforming ads
- Auto-increase budget for winning ads

**Recommended: Option B initially** (scale to C later)

---

## Phase 2: Lead Capture Hub

### 2.1 Website Form (Already Built)

**Current State:** ✅ n8n-integrated form
**Enhancement Needed:**
- Exit-intent popup (offer free mockup)
- Sticky CTA buttons
- Live chat + AI chatbot (already built)

### 2.2 Email Parser

**Purpose:** Handle leads who email directly

**Tool:** n8n Email Trigger (IMAP)
**Process:**
1. Monitor hello@craftmode.co
2. Parse incoming emails
3. Extract: sender, subject, body
4. Use AI to classify intent
5. Auto-respond or route to sales queue
6. Create HubSpot contact

**Cost:** Free (included in n8n)

### 2.3 AI Phone Agent

**Purpose:** Handle incoming calls 24/7

**Option A: Bland.ai (Budget: $0.09/minute)**
- AI voice agent answers calls
- Qualifies leads
- Books appointments
- **Pros:** Natural conversation
- **Cons:** Per-minute pricing

**Option B: Vapi.ai (Budget: $0.05/minute)**
- Similar to Bland, slightly cheaper
- Good integration options

**Option C: Twilio + AssemblyAI (Budget: $0.03/minute)**
- Self-hosted solution
- More complex setup
- **Pros:** Lowest cost
- **Cons:** More dev work

**Recommended: Option A (Bland.ai)** for launch

**Script Flow:**
```
"Hello, thank you for calling Craft Mode. I'm an AI assistant.
How can I help you today?"
→ Capture: Service needed, budget, timeline
→ If qualified: "I can connect you with our team. When's a good time?"
→ Book via Calendly API
→ Send confirmation
```

---

## Phase 3: Lead Qualification Engine

### 3.1 Lead Scoring

**Purpose:** Automatically score leads 1-100

**Criteria:**
| Factor | Weight | Data Source |
|--------|--------|-------------|
| Company size | 20% | Clearbit API (from email) |
| Budget mentioned | 25% | Form/chat |
| Service type | 15% | Form/chat |
| Timeline | 20% | Form/chat |
| Source quality | 10% | Referral > Organic > Ad |
| Engagement | 10% | Email opens, site visits |

**Implementation:**
- n8n workflow scores on capture
- >70 = Hot lead (immediate follow-up)
- 40-70 = Warm lead (nurture sequence)
- <40 = Cold lead (automated nurture)

### 3.2 Automated Qualification Chat

**Purpose:** Pre-qualify before human call

**Flow:**
1. Lead fills form → Instant AI chat opens
2. AI asks qualifying questions:
   - "What's your current website?"
   - "What's your budget range?"
   - "When do you need this done?"
3. AI scores responses
4. If qualified → Book Calendly
5. If not → Add to nurture sequence

**Tool:** Already built (website chatbot)

---

## Phase 4: Discovery & Requirements Engine

### 4.1 AI Discovery Questionnaire

**Purpose:** Gather detailed requirements without calls

**Tool:** Tally.so (free) or Typeform ($25/mo) + n8n

**Questionnaire Flow:**
```
Section 1: Business Info (auto-filled from lead data)
Section 2: Current State
  - Current website URL
  - What do you like/dislike?
  - Competitor websites you admire
Section 3: Goals
  - Primary objective (leads/sales/awareness)
  - Target audience
  - Must-have features
Section 4: Technical
  - Integrations needed
  - E-commerce? (products, payment)
  - Content management needs
Section 5: Design
  - Brand guidelines
  - Color preferences
  - Examples of liked designs
```

**AI Analysis:**
- n8n sends responses to Claude
- Claude generates:
  - Technical requirements doc
  - Suggested tech stack
  - Effort estimate
  - Risk assessment

### 4.2 Competitor Research Automation

**Purpose:** Analyze competitor websites automatically

**Tool:** n8n + ScrapingBee/ScrapingAnt ($49/mo)

**Process:**
1. Extract competitor URLs from questionnaire
2. Scrape each website
3. AI analyzes:
   - Design patterns
   - Features present
   - Content structure
   - SEO elements
4. Generates comparison report

---

## Phase 5: Proposal & Quote Engine

### 5.1 Dynamic Pricing Calculator

**Purpose:** Generate accurate quotes instantly

**Variables:**
| Service | Base Price | Multipliers |
|---------|------------|-------------|
| Website | $1,500 | +$500/mo for rush, +$300/page over 5 |
| E-commerce | $3,500 | +$10/product, +$500/custom features |
| Web App | $5,000 | +$1,000/complex feature |
| Marketing | $1,000/mo | +$500/additional channel |

**Implementation:**
- n8n workflow calculates based on requirements
- Applies multipliers automatically
- Generates line-item breakdown

### 5.2 AI Proposal Generator

**Purpose:** Create professional proposals in minutes

**Tool:** PandaDoc API ($19/mo) + n8n + Claude

**Process:**
1. n8n receives requirements analysis
2. Claude generates proposal content:
   - Executive summary
   - Project scope
   - Timeline
   - Investment breakdown
   - Terms & conditions
3. n8n populates PandaDoc template
4. Generates PDF
5. Sends to client via email
6. Tracks opens/views

**Template Structure:**
```
Cover Page → Executive Summary → Our Process →
Scope of Work → Timeline → Investment →
Terms → Acceptance Page (e-signature)
```

### 5.3 E-Signature

**Option A: PandaDoc** (Built-in, $19/mo)
**Option B: DocuSign** ($10/mo, more trusted)
**Option C: SignWell** (Free tier available)

**Recommended:** PandaDoc (all-in-one)

---

## Phase 6: Payment Processing

### 6.1 Stripe Integration

**Already set up** - enhance with:
- Automated invoicing
- Payment reminders
- Failed payment retry logic

**Payment Structure:**
- 50% advance on sign
- 50% on delivery
- Option: 100% upfront (10% discount)

### 6.2 Automated Invoicing

**Tool:** Stripe + n8n

**Workflow:**
1. Proposal signed → Trigger invoice
2. n8n creates Stripe invoice
3. Email sent to client
4. Payment received → Update HubSpot
5. Payment failed → Retry sequence (Day 1, 3, 7)

---

## Phase 7: AI Delivery Pipeline

This is the core engine. We need a structured project management system.

### 7.1 Project Management System

**Option A: Notion (Free)**
- Project database with statuses
- Task templates
- Client portal view
- **Pros:** Free, flexible
- **Cons:** Less automation

**Option B: Airtable ($20/mo)**
- Better automation
- More integrations
- Gantt views

**Option C: Linear ($8/user/mo)**
- Built for software projects
- GitHub integration
- Fast UI

**Recommended:** Notion (integrates well with n8n)

**Project Template:**
```
Project Card:
- Client Info
- Requirements Doc (link)
- Proposal (link)
- Contract (link)
- Invoice Status
- Design Phase (checklist)
- Development Phase (checklist)
- Content Phase (checklist)
- Review Phase (checklist)
- Launch Phase (checklist)
- Status: Discovery → Design → Development → Review → Launch → Complete
```

### 7.2 Design Automation

**Tool:** v0.dev + Figma AI

**Process:**
1. Requirements feed into prompt generator
2. Claude generates v0 prompts
3. AI generates design mockups
4. Export to Figma
5. Client review link generated

### 7.3 Development Automation

**Tool:** Cursor IDE + Claude + GitHub

**Process:**
1. Designs approved → Create GitHub repo
2. Cursor AI generates initial code
3. AI writes: components, pages, API routes
4. Automated testing (Playwright)
5. Deploy to Vercel preview

### 7.4 Content Automation

**Tool:** Claude + n8n

**Process:**
1. Extract content from client (questionnaire)
2. AI refines/rewrites for web
3. Generates: headlines, CTAs, meta descriptions
4. Creates image prompts for Midjourney

### 7.5 Review & QA Automation

**Tool:** Playwright + Lighthouse CI

**Process:**
1. Automated accessibility checks
2. Performance testing
3. Cross-browser testing
4. Mobile responsiveness check
5. Generate QA report

---

## Phase 8: Communication Automation

### 8.1 Client Updates

**Tool:** n8n + Gmail + Slack

**Automated Touchpoints:**
| Milestone | Trigger | Action |
|-----------|---------|--------|
| Project start | Payment received | Welcome email + kickoff doc |
| Design complete | Status change | Review link sent |
| Development 50% | Timer/burndown | Progress update |
| Ready for review | Status change | Review request + Loom video |
| Revisions requested | Status change | Acknowledge + timeline |
| Launch | Deploy complete | Celebration email + handover |

### 8.2 Revision Management

**Tool:** Figma comments + n8n + Notion

**Process:**
1. Client comments in Figma
2. n8n webhook receives notification
3. AI categorizes: Design/Code/Content
4. Creates tasks in Notion
5. Notifies via Slack
6. Auto-assigns based on type

---

## Phase 9: Delivery & Signoff

### 9.1 Automated Delivery

**Process:**
1. Final QA passes
2. Deploy to production (Vercel)
3. Generate handover documentation
4. Send completion email with:
   - Live site URL
   - Admin access credentials
   - Training video (Loom)
   - Support info

### 9.2 Final Payment

**Process:**
1. Delivery email sent
2. Final invoice auto-generated
3. 7-day payment term
4. Payment reminders (Day 3, 6)
5. Payment received → Signoff doc sent

### 9.3 Signoff Collection

**Tool:** PandaDoc simple signoff

**Document:**
```
"I confirm that Craft Mode has delivered the project
as per the agreed scope. The website is live and
functioning as expected.

[Client Signature] [Date]"
```

---

## Phase 10: Post-Delivery Automation

### 10.1 Testimonial Request

**Timeline:** 14 days after launch

**Email Sequence:**
- Day 14: "How's the new site performing?"
- Day 21: Request for testimonial (G2/Clutch/LinkedIn)
- Day 30: Case study request (offer discount on next project)

### 10.2 Maintenance Upsell

**Offer:** $200/mo maintenance plan
- Hosting + SSL
- Security updates
- Monthly backups
- 2 hours of changes/month

**Automation:**
- Proposal expires in 30 days
- Automated follow-up sequence

### 10.3 Referral Program

**Tool:** ReferralCandy ($47/mo) or manual n8n

**Offer:** $500 credit for each referred client who signs

**Process:**
1. Client signs off → Referral email sent
2. Unique referral link generated
3. New lead uses link → Referrer notified
4. Deal closes → Credit applied

---

## Tech Stack Summary

### Core Infrastructure
| Component | Tool | Cost |
|-----------|------|------|
| Orchestrator | n8n Cloud | $20/mo |
| CRM | HubSpot Free | $0 |
| PM/Documentation | Notion | $0 |
| Email | Google Workspace | $6/mo |
| Hosting | Vercel | $0 |
| Domain | Namecheap | $12/yr |
| DNS/SSL | Cloudflare | $0 |

### Marketing
| Component | Tool | Cost |
|-----------|------|------|
| SEO Content | Claude API | ~$50/mo |
| Social Media | n8n | Included |
| Ads | Google Ads | Variable |
| Analytics | GA4 + Search Console | $0 |

### Sales
| Component | Tool | Cost |
|-----------|------|------|
| Scheduling | Calendly Free | $0 |
| Proposals | PandaDoc | $19/mo |
| E-Signature | PandaDoc | Included |
| Payments | Stripe | 2.9% + 30¢ |
| Phone Agent | Bland.ai | Usage-based |

### Delivery
| Component | Tool | Cost |
|-----------|------|------|
| Design | v0.dev | $20/mo |
| Development | Cursor | $20/mo |
| Code Repository | GitHub | $0 |
| Testing | Playwright | $0 |
| Images | Midjourney | $10/mo |

### Communication
| Component | Tool | Cost |
|-----------|------|------|
| Team Chat | Slack Free | $0 |
| Video | Loom Free | $0 |
| Screen Share | Zoom Free | $0 |

**TOTAL FIXED COSTS: ~$145/mo**
**TOTAL WITH ADS + AI USAGE: ~$300-500/mo**

---

## Implementation Roadmap

### Week 1: Foundation
- [ ] Set up n8n Cloud
- [ ] Import form + chatbot workflows
- [ ] Configure Gmail credentials
- [ ] Test form → email flow

### Week 2: Sales Automation
- [ ] Set up PandaDoc templates
- [ ] Create proposal generator workflow
- [ ] Set up Calendly integration
- [ ] Test full sales flow

### Week 3: Delivery System
- [ ] Create Notion project template
- [ ] Set up GitHub project templates
- [ ] Create Cursor prompts library
- [ ] Test end-to-end project creation

### Week 4: Communication
- [ ] Build automated email sequences
- [ ] Set up milestone notifications
- [ ] Create revision management workflow
- [ ] Test client communication flow

### Week 5: Marketing Automation
- [ ] Set up content generation workflow
- [ ] Configure social media automation
- [ ] Set up lead scoring
- [ ] Launch first campaign

### Week 6: Optimization
- [ ] Test entire flow with fake project
- [ ] Identify bottlenecks
- [ ] Add phone agent (Bland.ai)
- [ ] Document all processes

---

## Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| AI quality issues | Medium | High | Human review checkpoints |
| Client wants human touch | High | Medium | Offer hybrid option |
| n8n failures | Low | High | Monitoring + alerts |
| Payment failures | Medium | Medium | Automated retry logic |
| Scope creep | High | Medium | Clear contracts + change orders |

---

## Success Metrics

### Month 1 Targets
- 100+ website visitors
- 10+ qualified leads
- 3+ proposals sent
- 1+ client signed

### Month 3 Targets
- 500+ monthly visitors
- 30+ qualified leads
- 10+ proposals sent
- 5+ clients signed
- $15,000+ revenue

### Month 6 Targets
- 2,000+ monthly visitors
- 100+ qualified leads
- 25+ proposals sent
- 15+ clients signed
- $50,000+ revenue
- 50%+ referral rate

---

## Next Steps

1. **Review this plan** and choose your preferred options
2. **Set up n8n Cloud** and import the workflows
3. **Configure credentials** (Gmail, Anthropic, etc.)
4. **Test the complete flow** with a mock project
5. **Launch marketing** once automation is solid

Ready to implement? I can help with any specific phase.
