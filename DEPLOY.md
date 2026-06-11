# 🚀 VAULT — GitHub Deployment Guide

## Step 1 — Create a GitHub Repository

1. Go to **https://github.com/new**
2. Fill in:
   - **Repository name:** `vault-banking` (or any name you like)
   - **Visibility:** Public ✅ (required for free GitHub Pages)
   - **Do NOT** check "Add a README" — we already have one
3. Click **Create repository**

---

## Step 2 — Upload Files (No Git needed — browser upload)

1. On your new repo page, click **"uploading an existing file"** link
2. Drag and drop ALL these files:
   ```
   index.html
   README.md
   .gitignore
   .github/workflows/deploy.yml   ← create this folder structure
   ```
3. Scroll down, click **Commit changes**

> **Or use Git (if installed):**
> ```bash
> git init
> git add .
> git commit -m "Initial commit: VAULT Banking System"
> git branch -M main
> git remote add origin https://github.com/YOUR-USERNAME/vault-banking.git
> git push -u origin main
> ```

---

## Step 3 — Enable GitHub Pages

1. In your repo, go to **Settings** (top tab)
2. In the left sidebar click **Pages**
3. Under **Source**, select:
   - **Deploy from a branch** → change to **GitHub Actions**
4. Click **Save**

---

## Step 4 — Wait ~60 seconds, then visit your site!

Your live URL will be:
```
https://YOUR-USERNAME.github.io/vault-banking/
```

You can also find it under **Settings → Pages** once deployed.

---

## Updating the site later

Whenever you edit `index.html` and push/upload to GitHub, the site automatically redeploys in about 60 seconds via the GitHub Actions workflow.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Page shows 404 | Wait 2 min and refresh; or check Settings → Pages |
| Blank white page | Open browser DevTools (F12) → Console tab, share the error |
| Deploy failed | Go to **Actions** tab in your repo to see the error log |
| Changes not showing | Hard refresh: Ctrl+Shift+R (Windows) / Cmd+Shift+R (Mac) |
