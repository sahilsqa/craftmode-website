# Craft Mode — Complete Agency Integrations Setup

## 📧 STEP 1: Email Setup (Priority #1)

### Option A: Google Workspace (Recommended)
**Cost:** $6/user/month (~$6/month for hello@craftmode.co)
**URL:** https://workspace.google.com

**Setup Steps:**
1. Go to https://workspace.google.com/signup/businessstarter
2. Enter business name: "Craft Mode"
3. Choose domain: "I already have a domain" → craftmode.co
4. Verify domain ownership (add TXT record in Namecheap)
5. Create user: `hello@craftmode.co`
6. Set up MX records in Namecheap:
   ```
   ASPMX.L.GOOGLE.COM (Priority 1)
   ALT1.ASPMX.L.GOOGLE.COM (Priority 5)
   ALT2.ASPMX.L.GOOGLE.COM (Priority 5)
   ALT3.ASPMX.L.GOOGLE.COM (Priority 10)
   ALT4.ASPMX.L.GOOGLE.COM (Priority 10)
   ```

**Features You Get:**
- Professional email (hello@craftmode.co)
- Google Drive (30GB)
- Google Calendar
- Google Meet (video calls)
- Gmail with custom domain

### Option B: Zoho Mail (Free Option)
**Cost:** FREE for up to 5 users
**URL:** https://www.zoho.com/mail

**Setup Steps:**
1. Go to https://www.zoho.com/mail/zohomail-pricing.html
2. Select "Forever Free Plan"
3. Add domain: craftmode.co
4. Verify domain (TXT record or CNAME)
5. Add MX records (Zoho provides these)
6. Create hello@craftmode.co

**Limitations:**
- 5GB storage per user
- No Google Workspace integrations
- Good for starting, migrate later

---

## 🔗 STEP 2: Core Integrations (After Email Setup)

### 1. Calendly — Scheduling
**Purpose:** Client booking, consultation calls
**Cost:** Free tier available
**URL:** https://calendly.com

**Setup:**
1. Sign up with hello@craftmode.co
2. Create event type: "Free Consultation (15 min)"
3. Set availability: Business hours
4. Add intake questions:
   - Company name
   - What do you need? (Website/App/Marketing)
   - Current website (if any)
   - Budget range
5. Connect to Google Calendar
6. Copy booking link for website

**Integration:**
- Embed on website: `<iframe>` or button
- Add to email signature
- Include in LinkedIn/Twitter bio

---

### 2. Stripe — Payments & Invoicing
**Purpose:** Client payments, invoicing
**Cost:** 2.9% + 30¢ per transaction
**URL:** https://stripe.com

**Setup:**
1. Sign up with hello@craftmode.co
2. Complete business verification
3. Set up products:
   - Starter Website ($1,500)
   - Growth Package ($3,500)
   - Custom App ($5,000+)
   - Marketing Retainer ($1,000-$2,500/month)
4. Enable invoicing
5. Connect bank account for payouts
6. Set up payment links for each service

**Workflow:**
- Send invoice via Stripe → Client pays → Automatic receipt
- Or use payment links in proposals

---

### 3. HubSpot CRM — Client Management
**Purpose:** Lead tracking, deal pipeline, client communication
**Cost:** FREE tier (very capable)
**URL:** https://www.hubspot.com

**Setup:**
1. Sign up with hello@craftmode.co
2. Go to Settings → Users → Add team members
3. Configure deal stages:
   ```
   - New Lead
   - Contacted
   - Meeting Scheduled
   - Proposal Sent
   - Negotiation
   - Closed Won
   - Closed Lost
   ```
4. Create contact properties:
   - Company size
   - Industry
   - Service needed
   - Budget
   - Source (LinkedIn, Referral, etc.)
5. Connect email (hello@craftmode.co)
6. Install browser extension

**Integrations:**
- Connect Calendly (meetings auto-log)
- Connect email (conversations tracked)
- Connect website (form submissions)

---

### 4. Notion — Project Management & Documentation
**Purpose:** Project tracking, SOPs, content calendar
**Cost:** FREE for personal use, $8/member for teams
**URL:** https://notion.so

**Setup:**
1. Sign up with hello@craftmode.co
2. Create workspace: "Craft Mode Agency"
3. Essential pages to create:
   - **Project Dashboard:** Active projects, status, deadlines
   - **Client Database:** Contact info, contracts, notes
   - **Content Calendar:** Blog, social posts, newsletters
   - **SOPs:** Processes, templates, workflows
   - **Finance Tracker:** Revenue, expenses, invoices
   - **Ideas & Brainstorming:** Future services, improvements

**Templates to Add:**
- Client onboarding checklist
- Project brief template
- Content creation workflow
- Monthly review template

---

### 5. Slack — Team Communication
**Purpose:** Internal team chat, client notifications
**Cost:** FREE tier
**URL:** https://slack.com

**Setup:**
1. Create workspace: craftmode.slack.com
2. Channels to create:
   - #general (announcements)
   - #projects (project updates)
   - #sales (leads, deals)
   - #content (marketing ideas)
   - #random (team chat)
3. Integrations to add:
   - HubSpot (deal notifications)
   - Calendly (booking alerts)
   - Stripe (payment notifications)
   - GitHub (code updates)
   - Google Drive (file sharing)

---

### 6. Google Analytics 4 — Website Analytics
**Purpose:** Track website visitors, conversions
**Cost:** FREE
**URL:** https://analytics.google.com

**Setup:**
1. Sign in with hello@craftmode.co
2. Create property: "Craft Mode Website"
3. Add data stream: Web → https://craftmode.co
4. Copy GA4 tracking ID (G-XXXXXXXXXX)
5. Add to website `<head>` section
6. Set up conversion events:
   - Form submission
   - Calendly booking
   - Contact button click

**Key Metrics to Track:**
- Visitors per day/week
- Traffic sources
- Bounce rate
- Conversion rate (form submissions)
- Popular pages

---

### 7. Google Search Console — SEO Monitoring
**Purpose:** Search performance, indexing, SEO issues
**Cost:** FREE
**URL:** https://search.google.com/search-console

**Setup:**
1. Sign in with hello@craftmode.co
2. Add property: craftmode.co
3. Verify domain ownership (TXT record in Namecheap)
4. Submit sitemap: https://craftmode.co/sitemap.xml
5. Connect to Google Analytics

**Monitor:**
- Search queries bringing traffic
- Click-through rates
- Indexing issues
- Core Web Vitals
- Mobile usability

---

### 8. Mailchimp — Email Marketing
**Purpose:** Newsletters, nurture sequences, announcements
**Cost:** FREE up to 500 subscribers
**URL:** https://mailchimp.com

**Setup:**
1. Sign up with hello@craftmode.co
2. Create audience: "Craft Mode Subscribers"
3. Signup forms:
   - Website popup (for blog visitors)
   - Footer form
   - Landing page form
4. Email templates:
   - Welcome sequence (3 emails)
   - Monthly newsletter
   - Launch announcements
   - Client case studies

**Integration:**
- Connect to website
- Connect to HubSpot
- Connect to Calendly (no-shows get follow-up)

---

### 9. Buffer — Social Media Scheduling
**Purpose:** Schedule LinkedIn, Twitter posts
**Cost:** FREE up to 3 channels
**URL:** https://buffer.com

**Setup:**
1. Sign up with hello@craftmode.co
2. Connect accounts:
   - LinkedIn (Company Page)
   - LinkedIn (Personal)
   - Twitter/X
3. Create posting schedule:
   - LinkedIn: Daily at 9am
   - Twitter: 2x daily
4. Queue content from `launch-content.md`

**Content Buckets:**
- Educational (40%)
- Social proof (30%)
- Promotional (20%)
- Engagement (10%)

---

### 10. 1Password or Bitwarden — Password Management
**Purpose:** Secure password storage for all accounts
**Cost:** 1Password ($2.99/mo), Bitwarden (FREE)
**URL:** https://bitwarden.com (recommended - free)

**Setup:**
1. Sign up with personal email
2. Create vault: "Craft Mode"
3. Store all credentials:
   - Google Workspace
   - Stripe
   - HubSpot
   - Notion
   - Namecheap
   - Vercel
   - GitHub
   - Social media accounts
4. Enable 2FA wherever possible

---

### 11. Cloudflare — DNS & Performance
**Purpose:** Faster DNS, SSL, CDN, security
**Cost:** FREE tier
**URL:** https://cloudflare.com

**Setup:**
1. Sign up with hello@craftmode.co
2. Add site: craftmode.co
3. Update nameservers in Namecheap to Cloudflare
4. Enable:
   - SSL/TLS (Full)
   - Auto minify (HTML, CSS, JS)
   - Brotli compression
   - Always Online

**Benefits:**
- Faster global load times
- Free SSL certificate
- DDoS protection
- Analytics

---

### 12. Zapier — Automation
**Purpose:** Connect apps, automate workflows
**Cost:** FREE up to 100 tasks/month
**URL:** https://zapier.com

**Essential Zaps:**
1. **Calendly → HubSpot**
   - New booking → Create/update contact + deal
2. **Website Form → HubSpot + Slack**
   - Form submission → Create lead + Slack notification
3. **Stripe → HubSpot + Slack**
   - New payment → Update deal to "Closed Won" + notification
4. **HubSpot → Mailchimp**
   - New contact → Add to newsletter list

---

## 📋 STEP 3: Complete Setup Checklist

### Week 1: Foundation
- [ ] Email setup (Google Workspace or Zoho)
- [ ] Google Drive folder structure
- [ ] Calendly booking page
- [ ] Stripe account + payment links
- [ ] HubSpot CRM configured
- [ ] Notion workspace created
- [ ] Password manager vault

### Week 2: Marketing & Analytics
- [ ] Google Analytics installed on website
- [ ] Google Search Console verified
- [ ] Mailchimp audience created
- [ ] Buffer connected to social accounts
- [ ] Cloudflare DNS configured
- [ ] Zapier automations set up

### Week 3: Team & Operations
- [ ] Slack workspace active
- [ ] All SOPs documented in Notion
- [ ] Email templates created
- [ ] Proposal templates ready
- [ ] Contract templates ready

---

## 🔐 Security Checklist

- [ ] 2FA enabled on all critical accounts
- [ ] Password manager in use
- [ ] Backup codes saved offline
- [ ] Team access documented
- [ ] Regular access review scheduled

---

## 📊 Integration Architecture

```
WEBSITE (craftmode.co)
    ↓
    ├─→ Google Analytics (tracking)
    ├─→ Google Search Console (SEO)
    ├─→ Calendly (booking)
    └─→ Mailchimp (newsletter signup)

CALENDLY BOOKING
    ↓
    ├─→ Google Calendar (availability)
    ├─→ HubSpot (lead created)
    └─→ Slack (team notification)

STRIPE PAYMENT
    ↓
    ├─→ HubSpot (deal closed)
    ├─→ Slack (revenue notification)
    └─→ Google Drive (receipt saved)

EMAIL (hello@craftmode.co)
    ↓
    ├─→ HubSpot (conversation tracked)
    ├─→ Slack (shared inbox)
    └─→ Google Drive (attachments)

HUBSPOT CRM (Central Hub)
    ↓
    ├─→ Notion (project created)
    ├─→ Slack (updates)
    └─→ Mailchimp (nurture sequence)
```

---

## 💰 Monthly Costs Summary

| Tool | Cost | Notes |
|------|------|-------|
| Google Workspace | $6 | Professional email |
| Notion | $0 | Free tier sufficient |
| HubSpot | $0 | Free CRM |
| Calendly | $0 | Free tier |
| Stripe | Variable | 2.9% + 30¢ per transaction |
| Mailchimp | $0 | Until 500 subscribers |
| Buffer | $0 | 3 channels free |
| Bitwarden | $0 | Free password manager |
| Cloudflare | $0 | Free tier |
| Zapier | $0 | 100 tasks free |
| Slack | $0 | Free tier |
| **Total Fixed** | **$6/month** | + transaction fees |

---

## 🚀 Quick Start Order

**Today (30 minutes):**
1. Set up Zoho Mail (free) for hello@craftmode.co
2. Create Calendly account
3. Sign up for HubSpot CRM

**This Week:**
4. Set up Google Analytics + Search Console
5. Create Notion workspace
6. Set up password manager

**Next Week:**
7. Connect all integrations via Zapier
8. Set up Mailchimp
9. Configure Buffer for social scheduling

---

**Questions? Need help with any specific integration?**
