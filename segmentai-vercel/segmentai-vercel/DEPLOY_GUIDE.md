# SegmentAI — Vercel Deployment Guide

## What's in this folder

```
segmentai-vercel/
├── index.html       The full SegmentAI app
├── api/
│   └── chat.js      Serverless function — proxies Anthropic API calls
├── vercel.json      Vercel routing config
└── DEPLOY_GUIDE.md  This file
```

---

## How to deploy (10 minutes, no coding needed)

### Step 1 — Create a free Vercel account
Go to https://vercel.com and sign up with GitHub, Google, or email.

### Step 2 — Deploy the project

**Option A — Drag and drop (easiest):**
1. Go to https://vercel.com/new
2. Click "Browse" or drag the entire `segmentai-vercel` folder onto the page
3. Click "Deploy"
4. Wait ~30 seconds — Vercel builds and deploys automatically

**Option B — Via GitHub:**
1. Push this folder to a GitHub repository
2. Go to https://vercel.com/new
3. Import the repository
4. Click "Deploy"

### Step 3 — Add your API key (REQUIRED)

After deploying, the app will load but AI features won't work yet.

1. In the Vercel dashboard, click your project
2. Go to **Settings** → **Environment Variables**
3. Click **Add New**
4. Name: `ANTHROPIC_API_KEY`
5. Value: your Anthropic API key (starts with `sk-ant-...`)
6. Click **Save**

### Step 4 — Redeploy to apply the key

1. Go to the **Deployments** tab in your Vercel project
2. Click the three dots `...` on the latest deployment
3. Click **Redeploy**
4. Wait ~20 seconds

Your app is now live at the URL Vercel assigned (e.g. `your-project.vercel.app`).

---

## Updating the app later

If you make changes to `index.html` or `api/chat.js`, just redeploy:
- Drag and drop again, or push to GitHub — Vercel redeploys automatically.

---

## Troubleshooting

**AI chat says "Something went wrong"**
→ Check the API key is set correctly in Environment Variables and that you redeployed after adding it.

**Page loads but looks broken**
→ Make sure you uploaded the entire folder, not just index.html.

**"Method not allowed" error**
→ The api/chat.js file is missing or wasn't included in the upload. Check the folder structure.
