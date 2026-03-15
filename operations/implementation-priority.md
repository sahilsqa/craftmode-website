# Craft Mode - Implementation Priority Guide

## The 80/20 Rule: Focus on What Matters

You don't need everything day one. Here's the prioritized roadmap to get you operational and revenue-generating quickly.

---

## Phase 1: MVP (Week 1) - GET PAID

**Goal:** Close your first client with minimal automation

### Must-Have (Non-Negotiable):
| Component | Status | Action |
|-----------|--------|--------|
| Website with form | ✅ Done | Already deployed |
| AI Chatbot | ✅ Done | Already deployed |
| n8n form handler | 🔄 Next | Set up webhook + email |
| Calendly | ✅ Done | Already set up |
| Stripe | 🔄 Next | Create products + payment links |
| Manual proposal template | 🔄 Next | Create Google Doc template |

### Skip For Now:
- AI proposal generator
- PandaDoc integration
- Automated project onboarding
- Milestone notifications
- Phone agent (Bland.ai)

**Week 1 Action Items:**
1. [ ] Set up n8n Cloud (20 min)
2. [ ] Import form handler workflow (10 min)
3. [ ] Configure Gmail OAuth (15 min)
4. [ ] Update website with webhook URL (5 min)
5. [ ] Set up Stripe account (30 min)
6. [ ] Create proposal template in Google Docs (1 hour)
7. [ ] Post LinkedIn launch announcement (15 min)
8. [ ] Send 5 LinkedIn DMs (30 min)

**Target:** First lead → Manual proposal → Close deal

---

## Phase 2: Sales Automation (Week 2-3) - SCALE LEADS

**Goal:** Handle more leads without more work

### Priority Additions:
| Component | Why | Effort |
|-----------|-----|--------|
| AI Chatbot (n8n) | Qualify leads 24/7 | 2 hours |
| Lead scoring | Prioritize hot leads | 1 hour |
| Email parser | Handle email inquiries | 1 hour |
| Auto-responder sequences | Nurture cold leads | 2 hours |

### n8n Workflows to Add:
1. **Email Parser** - Parse hello@craftmode.co, classify intent
2. **Lead Scoring** - Score based on form data
3. **Nurture Sequence** - 5-email sequence for cold leads

**Week 2-3 Action Items:**
1. [ ] Set up n8n email trigger
2. [ ] Import chatbot workflow
3. [ ] Add Anthropic API key
4. [ ] Create nurture email sequence
5. [ ] Test complete lead flow

---

## Phase 3: Proposal Automation (Week 4-5) - CLOSE FASTER

**Goal:** Generate proposals in minutes, not hours

### Add When You Have 3+ Proposals/Week:
| Component | Why | Cost |
|-----------|-----|------|
| AI Proposal Generator | Instant proposals | API usage only |
| PandaDoc | Professional delivery | $19/mo |
| E-signature | Faster closes | Included |

**Decision Point:**
- If closing 1-2 deals/week → Manual proposals are fine
- If closing 3+ deals/week → Automate proposals

---

## Phase 4: Delivery Automation (Week 6-8) - DELIVER AT SCALE

**Goal:** Project management without manual work

### Add When You Have 2+ Active Projects:
| Component | Why | Cost |
|-----------|-----|------|
| Notion project template | Consistency | $0 |
| Project onboarding workflow | Auto-kickoff | Included |
| Milestone notifications | Client communication | Included |
| Slack integration | Team visibility | $0 |

---

## Phase 5: Full Automation (Month 3+) - OPTIMIZE

**Goal:** 90%+ automated operation

### Advanced Additions:
- Phone agent (Bland.ai)
- Content generation (SEO blog)
- Social media automation
- Referral program
- Maintenance upsells

---

## Decision Matrix: Build vs Buy vs Skip

| Component | Build (n8n) | Buy (SaaS) | Skip For Now |
|-----------|-------------|------------|--------------|
| Forms | ✅ Recommended | Formspree | - |
| Chatbot | ✅ Recommended | Intercom | - |
| Email | ✅ Recommended | Mailchimp | - |
| Proposals | ✅ After 3/wk | PandaDoc | Manual docs |
| CRM | - | ✅ HubSpot Free | - |
| PM | - | ✅ Notion Free | - |
| Phone | Skip | Bland.ai | Until 5+ calls/day |
| Accounting | - | ✅ Wave/QuickBooks | Manual |

---

## Quick Setup Commands

### n8n Cloud Setup (20 minutes):
```bash
# 1. Sign up at n8n.io/cloud
# 2. Create workflows
# 3. Get webhook URLs
# 4. Update website

cd ~/ai-agency/website
# Edit index.html with your webhook URLs
# Line ~1108: Form webhook
# Line ~1399: Chat webhook

git add index.html
git commit -m "Update n8n webhook URLs"
git push origin main
npx vercel --prod
```

### Stripe Setup:
```
1. Go to https://stripe.com
2. Create account with hello@craftmode.co
3. Create products:
   - Website Starter: $1,500
   - Website Growth: $3,500
   - Custom App: $5,000
   - Marketing Retainer: $1,000/mo
4. Create payment links for each
5. Add links to proposals
```

---

## Cost Breakdown by Phase

### Phase 1 (MVP): ~$26/mo
- Google Workspace: $6
- n8n Cloud: $20
- Domain: $1/mo (annual)

### Phase 2 (Sales Auto): ~$50/mo
- + Claude API usage: ~$20
- + Misc tools: ~$4

### Phase 3 (Proposal Auto): ~$70/mo
- + PandaDoc: $19

### Phase 4 (Delivery Auto): ~$90/mo
- + Cursor IDE: $20

### Phase 5 (Full Auto): ~$150/mo
- + Phone agent usage: ~$50
- + Additional APIs: ~$10

---

## Success Checkpoints

### Week 1:
- [ ] Website live with working form
- [ ] LinkedIn post published
- [ ] 5 DMs sent
- [ ] 1+ leads generated

### Week 2:
- [ ] n8n fully configured
- [ ] Automated email responses
- [ ] 10+ leads in pipeline

### Week 3:
- [ ] First discovery call completed
- [ ] First proposal sent
- [ ] Understanding of real pricing

### Week 4:
- [ ] First client signed
- [ ] First payment received
- [ ] Project started

### Month 2:
- [ ] 3+ clients signed
- [ ] Proposal automation live
- [ ] Project templates ready

### Month 3:
- [ ] 5+ active projects
- [ ] Referrals coming in
- [ ] System running smoothly

---

## Common Pitfalls to Avoid

### Don't:
1. **Over-automate early** - Build manual first, then automate
2. **Perfect the website** - Good enough is good enough
3. **Wait for everything** - Launch with MVP
4. **Ignore sales** - 50% of time should be outreach
5. **Underprice** - You're faster, not cheaper in value

### Do:
1. **Start selling immediately** - Everything else is secondary
2. **Document as you go** - SOPs for everything manual
3. **Get feedback fast** - First client teaches you the most
4. **Iterate quickly** - Improve after each project
5. **Focus on outcomes** - Clients pay for results, not features

---

## Your Next 24 Hours

### Today (2 hours):
1. [ ] Set up n8n Cloud
2. [ ] Configure form webhook
3. [ ] Test form submission
4. [ ] Create LinkedIn post
5. [ ] Send 5 DMs

### Tomorrow (2 hours):
1. [ ] Set up Stripe
2. [ ] Create proposal template
3. [ ] Set up HubSpot CRM
4. [ ] Send 5 more DMs
5. [ ] Follow up with connections

**Goal:** Get 3+ conversations started by end of week.

---

## Questions to Answer This Week

1. What's your actual closing rate? (Need 10+ conversations to know)
2. What objections come up most? (Add to FAQ)
3. What's the real timeline? (Track vs. estimate)
4. What do clients value most? (Ask them)
5. What can be productized? (Build templates)

---

## The Real Goal

Not automation for automation's sake.

**The goal is:** More revenue per hour of your time.

Everything else is a means to that end.

Start selling. Automate as you scale.

---

**Ready to start with Phase 1?**
