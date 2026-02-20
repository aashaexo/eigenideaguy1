# EigenIdeaGuy — EigenCompute Opportunity Analyzer

Paste any idea. Get an honest breakdown of where EigenCompute makes it stronger.

---

## Project Structure

```
eigenideaguy/
  index.html       ← the entire frontend
  api/
    analyze.js     ← serverless function (keeps your API key secret)
  vercel.json      ← routing config for Vercel
  package.json     ← project metadata
  .gitignore
```

---

## Deploy in 5 steps

### Step 1 — Get your Anthropic API key

1. Go to https://console.anthropic.com
2. Sign up or log in
3. Go to **API Keys** in the sidebar
4. Click **Create Key** → give it a name → copy it

It looks like: `sk-ant-api03-xxxxxxxxxxxxxxxxxxxx`

---

### Step 2 — Push to GitHub

```bash
# in your terminal, inside the eigenideaguy folder
git init
git add .
git commit -m "eigenideaguy initial"
```

Then go to https://github.com/new, create a new repo called `eigenideaguy`, and run:

```bash
git remote add origin https://github.com/YOUR_USERNAME/eigenideaguy.git
git branch -M main
git push -u origin main
```

---

### Step 3 — Deploy on Vercel

1. Go to https://vercel.com and sign up (free)
2. Click **Add New → Project**
3. Import your `eigenideaguy` GitHub repo
4. Leave all settings as default
5. Click **Deploy**

Vercel will build and give you a URL like `eigenideaguy.vercel.app`

---

### Step 4 — Add your API key (this is the important step)

Your API key must NEVER go in the code. Vercel stores it securely.

1. In your Vercel project → go to **Settings → Environment Variables**
2. Add a new variable:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-api03-xxxxxxxxxxxx` (your actual key)
   - **Environment:** Production, Preview, Development (check all three)
3. Click **Save**
4. Go to **Deployments** → click the three dots on your latest deploy → **Redeploy**

---

### Step 5 — Done

Your site is live. Share the Vercel URL with anyone.

---

## Cost

Claude Sonnet 4.6 costs ~$0.003 per analysis.
1,000 analyses = ~$3. Very cheap.

Set a spend limit in https://console.anthropic.com/settings/billing if you want a cap.

---

## Local development

To test locally before pushing:

```bash
npm install -g vercel
vercel dev
```

Then open http://localhost:3000

It will ask you to link to your Vercel project — say yes, it'll pull your env vars automatically.
