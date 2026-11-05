# Dooars Daily Basket - GitHub & Vercel Deployment Guide

Is project ko bina kisi change ke **GitHub** aur **Vercel** par 100% error-free deploy karne ke liye sabhi jaruri files set up kar di gayi hain:

1. **`vercel.json`**: SPA Rewrites configured hai taaki `/admin`, `/market`, `/delivery`, `/login` par refresh karne par **404 error na aaye**.
2. **`package.json`**: Production build command `npm run build` optimized hai.
3. **`.gitignore`**: `node_modules`, `dist`, local cache files ko ignore karta hai.

---

## Step 1: GitHub Par Code Push Karein

Apne computer (VS Code ya Terminal) me ye commands run karein:

```bash
# 1. Git initialize karein (agar pehle se nahi hai)
git init

# 2. Files add karein
git add .

# 3. Commit karein
git commit -m "Dooars Daily Basket Production Ready"

# 4. Branch name main set karein
git branch -M main

# 5. Apna GitHub repository connect karein (Apna username aur repo name dalein)
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/<YOUR_REPO_NAME>.git

# 6. Push karein
git push -u origin main
```

---

## Step 2: Vercel Par 1-Click Deploy Karein

1. [Vercel](https://vercel.com) par login karein (Apne GitHub account se login karein).
2. Dashboard par **"Add New..."** > **"Project"** par click karein.
3. Apni GitHub repository select karke **"Import"** par click karein.
4. **Build & Output Settings** (Vercel automatically detect kar lega):
   - **Framework Preset**: Vite
   - **Root Directory**: `./` (Default)
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
5. **Deploy** button par click karein!

Kuch hi seconds me aapka project bina kisi error ke live ho jayega aur aapko ek live URL (e.g. `https://your-project.vercel.app`) mil jayega.

---

## Key Benefits of This Setup:
- ✅ **No 404 on Refresh**: `vercel.json` ke rewrites ke kaaran `/admin/dashboard`, `/market`, `/delivery` paths seedha sahi open honge.
- ✅ **Firebase Realtime Sync**: Firestore, Authentication aur database Vercel par bina kisi configuration ke direct chalega.
- ✅ **Automatic Updates**: Future me jab bhi aap GitHub par `git push` karenge, Vercel automatically new version live kar dega.
