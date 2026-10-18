# 🚀 Hosting & Publishing Guide (ہوسٹنگ اور پبلش کرنے کا طریقہ)

This portfolio website for **Abdul Rehman** is built with React 19, Vite, Tailwind CSS, and Firebase Firestore. It is 100% production-ready and optimized for instant hosting on any platform.

---

## ⚡ Option 1: Vercel (Recommended — Fastest 1-Click Setup)
Vercel is the easiest and highest-performance hosting provider for React Vite SPAs:

1. Push your repository to **GitHub**.
2. Go to [vercel.com](https://vercel.com) and log in with your GitHub account.
3. Click **"Add New Project"** and select your repository.
4. Framework Preset will auto-detect as **Vite**.
5. Click **"Deploy"**.
6. That's it! Your site will be live with a free SSL certificate (`https://your-portfolio.vercel.app`) in under 30 seconds.
7. *Note:* The repository already includes `vercel.json` for seamless SPA page refresh and asset caching.

---

## 🌐 Option 2: GitHub Pages (مفت ہوسٹنگ گٹ ہب پر)

The repository already contains `.github/workflows/deploy.yml`, which builds and publishes the site automatically.

1. Create a new repository on GitHub and push this project to the `main` branch.
2. In the repository go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.
3. Push (or re-run the workflow from the **Actions** tab). After about a minute the site is live at
   `https://<your-username>.github.io/<repository-name>/`.
4. **Admin Google sign-in:** in the Firebase console open **Authentication → Settings → Authorized domains** and add `<your-username>.github.io`. Without this the Google login popup is blocked.
5. **Firestore rules:** copy the contents of `firestore.rules` into Firebase console → Firestore → Rules → **Publish** (see README, "Security").

Custom domain? Add it under Settings → Pages, then change `SITE_URL` logic in the workflow's "Set site URL" step.

---

## 💎 Option 3: Netlify

1. Drag and drop the `dist/` folder into [app.netlify.com/drop](https://app.netlify.com/drop) OR connect your GitHub repository.
2. Build command: `npm run build`
3. Publish directory: `dist`
4. *Note:* The repository already includes `public/_redirects` (`/* /index.html 200`) for Netlify.

---

## 🔥 Option 4: Firebase Hosting

1. Install Firebase CLI: `npm install -g firebase-tools`
2. Run `firebase login`
3. Run `firebase init hosting`:
   - Public directory: `dist`
   - Single-page app: `Yes`
4. Run `npm run build && firebase deploy`

---

## 🛠️ Verification Checklist (تمام ٹیسٹنگ کی تفصیل)
- [x] **TypeScript Compilation**: `npm run lint` (`tsc --noEmit`) passes with 0 errors.
- [x] **Production Bundle**: `npm run build` builds clean chunks in <1.5s.
- [x] **SEO & Social Meta**: OpenGraph, Twitter Cards, and Schema.org JSON-LD configured.
- [x] **Crawler & Indexing**: `robots.txt` and `sitemap.xml` included in `public/`.
- [x] **App Manifest & Favicon**: `favicon.svg` and `manifest.json` included in `public/`.
- [x] **SPA Fallbacks**: `404.html` and `_redirects` included in `public/`.
- [x] **Admin Authentication**: Securely locked to `abdul415018@gmail.com`.
- [x] **Cloud Sync**: Firebase Firestore real-time listener and cloud synchronization active.
