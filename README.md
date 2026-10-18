# Graphic Designer Portfolio & Brand Showcase

A production-grade, responsive Graphic Designer & Brand Showcase web application built with **React 19**, **Vite**, **TypeScript**, **Tailwind CSS**, and **Google Cloud Firestore**.

---

## 🌟 Key Features

1. **9 Full-Site Switchable Aesthetic Templates**:
   - Swiss International Studio
   - Executive Slate Minimal
   - Pakistan Independence Day (with animated flag and green bunting garland overlays)
   - Eid al-Fitr (with glowing lanterns)
   - Eid al-Adha
   - Ramadan Kareem
   - Luxury Gold
   - Neo-Brutalist
   - Cyber Future Neon
2. **Cloud Firestore Persistent Global Sync**:
   - Every change made in the Admin Control Panel (theme, biography, pricing, projects, custom colors) is saved directly to Google Cloud Firestore (`portfolio/data`).
   - Automatically loaded in real time on all devices, smartphones, and browsers worldwide.
3. **Owner-Exclusive Admin Panel**:
   - Access restricted to the portfolio owner (`abdul415018@gmail.com`) via Google Firebase Authentication or private master credentials.
   - Quick access via keyboard shortcut `Ctrl + Shift + A`, URL hash `#admin`, or the footer link.
4. **WhatsApp Instant Client Inquiries**:
   - Contact form sends inquiries to Cloud Firestore and opens a pre-formatted chat directly to the designer's WhatsApp number (`+92 310 1234567`).
   - Direct email mailto backup link included.
5. **Interactive Portfolio Showcase**:
   - Interactive Before/After image retouching slider.
   - High-resolution project lightbox modal.
   - Dynamic custom color palette engine.

---

## 🚀 Publish on GitHub Pages

1. Create a GitHub repository and push this project to the `main` branch.
2. **Settings → Pages → Source → GitHub Actions**.
3. The included workflow (`.github/workflows/deploy.yml`) builds and deploys automatically on every push.
   Your site will be at `https://<username>.github.io/<repository-name>/`.
4. Firebase console → **Authentication → Settings → Authorized domains** → add `<username>.github.io` (needed for the admin Google login).

Other hosts (Netlify, Vercel, Firebase Hosting) are also supported; see `DEPLOYMENT.md`.

---

## 💻 Running on Windows (Windows 10 / 11)

1. **Install Node.js**:
   - Ensure Node.js (v18, v20, or v22 LTS) is installed from [https://nodejs.org/](https://nodejs.org/).
2. **Extract Project**:
   - Extract the ZIP file into a folder (e.g., `C:\Projects\portfolio`).
3. **Open Terminal**:
   - Open PowerShell or Command Prompt in the folder.
4. **Install and Run**:
   ```powershell
   # 1. Install dependencies
   npm install

   # 2. Run local development server
   npm run dev

   # 3. Build for production
   npm run build

   # 4. Preview production build locally
   npm run preview
   ```

---

## 🔒 Security & Cloud Firestore

> **Important:** rules in `firestore.rules` only take effect after you publish them in the Firebase console
> (Firestore Database → Rules → paste → Publish). Do this before sharing the site publicly.
> Admin changes are saved only while signed in with the owner's Google account.


- Firestore database configuration is located in `firebase-applet-config.json`.
- Security rules are defined in `firestore.rules`.
- Read access to `portfolio/data` is public so that your visitors always see your latest portfolio updates.
- Write access to `portfolio/data` is restricted to your verified Google account (`abdul415018@gmail.com`).
