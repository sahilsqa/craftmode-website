# Vercel + GitHub Integration Setup

## ✅ COMPLETED

### Git Repository
- [x] Initialized git in `~/ai-agency/website`
- [x] Created GitHub repo: https://github.com/sahilsqa/craftmode-website
- [x] Pushed code to main branch
- [x] Added vercel.json configuration

### Vercel Project
- [x] Linked local directory to Vercel project: `sahilxportsofts-projects/website`
- [x] Production URL: https://website-nu-wheat-37.vercel.app

## 🔧 FINAL STEP: Connect GitHub to Vercel (Dashboard)

The CLI is having permission issues. Complete via Vercel dashboard:

### Step 1: Go to Vercel Dashboard
1. Visit: https://vercel.com/dashboard
2. Select project: **website**
3. Go to **Settings** tab

### Step 2: Connect Git Repository
1. Click **Git** in left sidebar
2. Under "Git Repository", click **Connect**
3. Select **GitHub**
4. Authorize Vercel if prompted
5. Search for: `craftmode-website`
6. Click **Connect** next to the repo

### Step 3: Configure Deployment
```
Production Branch: main
Framework: Other (Static HTML)
Build Command: (leave empty)
Output Directory: (leave empty)
Install Command: (leave empty)
```

Click **Save**

## 🚀 After Connection

### Automatic Deployments
- Every push to `main` → Production deployment
- Every Pull Request → Preview deployment

### Domain Setup
To connect craftmode.co:
1. In Vercel dashboard → Domains
2. Add `craftmode.co`
3. Follow DNS instructions (same as before)

## 📋 Git Commands Reference

```bash
# Make changes and deploy
cd ~/ai-agency/website
git add .
git commit -m "Your changes"
git push origin main

# Automatic deployment will trigger on Vercel
```

## 🔗 Important Links

| Resource | URL |
|----------|-----|
| GitHub Repo | https://github.com/sahilsqa/craftmode-website |
| Vercel Production | https://website-nu-wheat-37.vercel.app |
| Vercel Dashboard | https://vercel.com/dashboard |

## ✅ Verification Checklist

After dashboard setup:
- [ ] GitHub repo connected in Vercel settings
- [ ] Test push: edit index.html, commit, push
- [ ] Verify deployment appears in Vercel dashboard
- [ ] Check production URL shows changes
