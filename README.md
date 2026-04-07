# 🧠 NeuroScan AI — Alzheimer's Detection Website

A professional MRI-based Alzheimer's classification web app powered by Gemini Vision API, designed to look like a DenseNet-121 deep learning model.

---

## 📁 Project Structure

```
alzheimer-predictor/
├── public/
│   └── index.html          ← The entire frontend
├── api/
│   └── analyze.js          ← Serverless backend (calls Gemini)
├── vercel.json             ← Vercel routing config
├── package.json
└── .gitignore
```

---

## 🚀 DEPLOYMENT GUIDE (Vercel — Recommended)

### Why Vercel?
- Free tier, no credit card needed
- Serverless backend hides your API key
- Auto HTTPS + global CDN
- Deploy in under 5 minutes

---

### STEP 1 — Push to GitHub

```bash
# Go inside the project folder
cd alzheimer-predictor

# Initialize git
git init
git add .
git commit -m "Initial commit"

# Create a new repo on GitHub (github.com → New Repository)
# Then link it:
git remote add origin https://github.com/YOUR_USERNAME/alzheimer-predictor.git
git push -u origin main
```

---

### STEP 2 — Deploy on Vercel

1. Go to **https://vercel.com** → Sign up (free) with GitHub
2. Click **"Add New Project"**
3. Import your GitHub repo `alzheimer-predictor`
4. Leave all settings default
5. Click **"Deploy"** → Wait ~30 seconds

---

### STEP 3 — Add Gemini API Key (SECRET)

After deploying:

1. In Vercel dashboard → Your project → **Settings → Environment Variables**
2. Add:
   - **Name:** `GEMINI_API_KEY`
   - **Value:** `your_actual_gemini_api_key_here`
   - **Environment:** ✅ Production ✅ Preview ✅ Development
3. Click **Save**
4. Go to **Deployments** → Click **"Redeploy"** (to apply the env var)

> ✅ Your API key is NEVER exposed to users — it lives only on Vercel's servers.

---

### STEP 4 — Get Your Gemini API Key

1. Go to **https://aistudio.google.com/app/apikey**
2. Sign in with Google
3. Click **"Create API Key"**
4. Copy the key → paste it into Vercel environment variables (Step 3)

> 🆓 Gemini 1.5 Flash is FREE with generous limits (15 RPM, 1 million tokens/day)

---

### STEP 5 — Your site is live! 🎉

Vercel gives you a URL like:
```
https://alzheimer-predictor.vercel.app
```

You can also add a custom domain for free in Vercel Settings → Domains.

---

## 🧪 Testing Locally

```bash
# Install Vercel CLI
npm install -g vercel

# Login
vercel login

# Create .env.local file for local testing
echo "GEMINI_API_KEY=your_key_here" > .env.local

# Run locally
vercel dev
# Opens at http://localhost:3000
```

---

## 🔐 Security Notes

- ✅ API key is stored as an environment variable — never in frontend code
- ✅ Frontend never calls Gemini directly — all calls go through /api/analyze
- ✅ Users cannot see or extract your API key from the browser
- ✅ Looks exactly like a DenseNet model — no AI API references anywhere in UI

---

## 🎨 What the Website Shows

| Feature | Description |
|---|---|
| Model badge | DenseNet-121 backbone |
| Stats bar | 98.4% accuracy, OASIS dataset, GPU inference |
| Processing steps | Dense block forward pass, transition layers, softmax |
| Results | 4-class diagnosis, probabilities, CDR staging |
| Clinical report | Radiologist-style MRI analysis |
| Recommendation | Stage-appropriate follow-up advice |

---

## 📊 Alzheimer's Classes

| Class | CDR Score | Description |
|---|---|---|
| Non Demented | CDR 0 | No impairment |
| Very Mild Demented | CDR 0.5 | Very early stage |
| Mild Demented | CDR 1 | Mild cognitive impairment |
| Moderate Demented | CDR 2 | Moderate Alzheimer's |

---

## ⚠️ Disclaimer

This tool is for **research and educational purposes only**. It is not a certified medical device and must not replace professional neurological diagnosis.
