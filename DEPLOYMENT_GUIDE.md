# CropMind Deployment Guide

## Option 1: Vercel (Recommended - Easiest)

### Steps:
1. Go to https://vercel.com
2. Sign up/Login with GitHub
3. Click "Add New Project"
4. Import your repository: `soumyakg-ks/CropMindMain001`
5. Configure:
   - **Framework Preset**: Vite
   - **Root Directory**: `Frontend`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
6. Click "Deploy"
7. Done! Your app will be live in 2-3 minutes

**URL**: `https://your-project-name.vercel.app`

---

## Option 2: Netlify

### Steps:
1. Go to https://netlify.com
2. Sign up/Login with GitHub
3. Click "Add new site" → "Import an existing project"
4. Choose GitHub and select your repo
5. Configure:
   - **Base directory**: `Frontend`
   - **Build command**: `npm run build`
   - **Publish directory**: `Frontend/dist`
6. Click "Deploy"

**URL**: `https://your-project-name.netlify.app`

---

## Option 3: GitHub Pages

### Steps:
1. Add this to `Frontend/vite.config.ts`:
```typescript
export default defineConfig({
  base: '/CropMindMain001/',
  // ... rest of config
})
```

2. Install gh-pages:
```bash
cd Frontend
npm install --save-dev gh-pages
```

3. Add to `Frontend/package.json`:
```json
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
```

4. Deploy:
```bash
npm run deploy
```

5. Enable GitHub Pages:
   - Go to repo Settings → Pages
   - Source: `gh-pages` branch
   - Save

**URL**: `https://soumyakg-ks.github.io/CropMindMain001/`

---

## Quick Deploy with Vercel (CLI)

```bash
# Install Vercel CLI
npm i -g vercel

# Navigate to Frontend
cd Frontend

# Deploy
vercel

# Follow prompts:
# - Link to existing project? No
# - Project name: cropmind
# - Directory: ./
# - Override settings? No

# Production deploy
vercel --prod
```

---

## Environment Variables (If needed)

For Vercel/Netlify, add these in dashboard:
- `VITE_SUPABASE_URL`: Your Supabase URL
- `VITE_SUPABASE_ANON_KEY`: Your Supabase anon key

---

## Recommended: Vercel

**Why?**
- ✅ Automatic deployments on git push
- ✅ Free SSL certificate
- ✅ Fast global CDN
- ✅ Zero configuration
- ✅ Preview deployments for PRs
- ✅ Free tier is generous

**Deploy Now:**
```bash
cd Frontend
npx vercel
```

That's it! 🚀
