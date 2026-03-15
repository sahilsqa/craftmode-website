# Craft Mode - n8n Setup Guide

This guide walks you through setting up n8n for the fully AI-operated Craft Mode website.

## Overview

Two n8n workflows handle:
1. **Contact Form** - Receives form submissions, sends emails
2. **AI Chatbot** - Receives chat messages, calls Claude API, returns responses

## Option A: n8n Cloud (Easiest - $20/month)

1. **Sign up at** https://n8n.io/cloud
2. **Use email:** hello@craftmode.co
3. **Choose Starter plan** ($20/month for 2,500 executions)

### Setup Steps:

#### 1. Import Workflows

1. Go to your n8n dashboard
2. Click **"Add Workflow"**
3. Click the **menu (⋮)** → **Import from File**
4. Import `n8n-form-handler.json`
5. Repeat for `n8n-chatbot-handler.json`

#### 2. Configure Gmail Credentials

1. In n8n, go to **Settings** → **Credentials**
2. Click **"New"** → Search "Gmail OAuth2"
3. Click **"Connect"** and authorize with hello@craftmode.co
4. Copy the credential ID
5. Update both workflows:
   - Open workflow → Click "Send Email to Team" node
   - Select your Gmail credential
   - Repeat for "Send Confirmation Email" and "Send Lead Email" nodes

#### 3. Configure Claude API Credentials

1. Go to **Settings** → **Credentials**
2. Click **"New"** → Search "Anthropic"
3. Enter your API key (get from https://console.anthropic.com)
4. Select the credential in the "Claude API" node

#### 4. Get Webhook URLs

**Form Handler:**
1. Open "Craft Mode - Contact Form Handler" workflow
2. Click on "Form Webhook" node
3. Copy the **Production URL** (looks like: `https://your-instance.n8n.cloud/webhook/craftmode-form-submission`)
4. Save this for later

**Chatbot Handler:**
1. Open "Craft Mode - AI Chatbot Handler" workflow
2. Click on "Chat Webhook" node
3. Copy the **Production URL** (looks like: `https://your-instance.n8n.cloud/webhook/craftmode-chatbot`)
4. Save this for later

#### 5. Activate Workflows

1. Open each workflow
2. Toggle the **"Active"** switch in the top right
3. Both workflows are now live

---

## Option B: Self-Hosted n8n (Free, requires server)

### Requirements:
- VPS (DigitalOcean, Hetzner, etc.) - $5-10/month
- Docker installed
- Domain name (optional but recommended)

### Docker Compose Setup:

```yaml
version: "3"
services:
  n8n:
    image: n8nio/n8n:latest
    restart: always
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=your_secure_password
      - WEBHOOK_URL=https://n8n.yourdomain.com
    volumes:
      - ~/.n8n:/home/node/.n8n
```

Run: `docker-compose up -d`

Access at: `http://your-server-ip:5678`

### With HTTPS (Recommended):

Use nginx-proxy + letsencrypt-companion or Traefik.

---

## Website Configuration

Once you have your webhook URLs, update the website:

### 1. Update Form Webhook

Edit `index.html` line ~1108:
```html
<form id="contact-form" data-n8n-webhook="YOUR_FORM_WEBHOOK_URL">
```

Replace `YOUR_FORM_WEBHOOK_URL` with your actual form webhook URL.

### 2. Update Chatbot Webhook

Edit `index.html` in the chatbot script section (~line 1399):
```javascript
const CHAT_WEBHOOK_URL = 'YOUR_CHAT_WEBHOOK_URL';
```

Replace `YOUR_CHAT_WEBHOOK_URL` with your actual chat webhook URL.

### 3. Deploy Changes

```bash
cd ~/ai-agency/website
git add index.html
git commit -m "Update n8n webhook URLs"
git push origin main
npx vercel --prod
```

---

## Testing

### Test Contact Form:
1. Visit https://craftmode.co
2. Fill out the contact form
3. Submit
4. Check hello@craftmode.co for the lead email
5. Check your test email for the confirmation

### Test Chatbot:
1. Click the chat widget (bottom right)
2. Send a message like "How much for a website?"
3. Verify you get an AI response
4. After 2 messages, verify lead capture form appears

---

## Troubleshooting

### Webhook not responding:
- Check workflow is **Active** in n8n
- Verify webhook URL is correct in index.html
- Check n8n execution logs

### Emails not sending:
- Verify Gmail OAuth is connected
- Check spam folders
- Verify email addresses are correct

### Claude API errors:
- Check API key is valid
- Verify you have API credits
- Check rate limits

---

## Advanced Customizations

### Add Slack Notifications:

Add a "Slack" node after form validation to post new leads to your team channel.

### Add Airtable/Notion Database:

Add a node to store all leads in a database for tracking.

### Add HubSpot Integration:

Add a "HubSpot" node to create contacts automatically.

---

## Security Notes

1. **Webhook URLs** - Keep these private. Anyone with the URL can trigger your workflows.
2. **API Keys** - Store in n8n credentials, never in code.
3. **Rate Limiting** - Consider adding rate limiting if you get spam.

---

## Monthly Costs

| Option | Cost | Notes |
|--------|------|-------|
| n8n Cloud Starter | $20/mo | 2,500 executions, managed hosting |
| Self-hosted VPS | $5-10/mo | More work, unlimited executions |
| Claude API | ~$0.01-0.05/chat | Pay per use |
| Gmail | Free | Via Google Workspace |

---

Need help? The n8n community forum is great: https://community.n8n.io
