# RupeeStream Showcase

Public showcase website, privacy policy, and support documentation for **RupeeStream** — a privacy-focused, local-first personal finance manager for Android.

- **Developer:** Sayan Biswas
- **Android Package:** `sayan.apps.rupeestream`
- **Developer & Support Email:** [sbiswas001.tech@gmail.com](mailto:sbiswas001.tech@gmail.com)
- **Firebase Project ID:** `rupeestream`
- **Live Showcase URL:** [https://rupeestream.web.app](https://rupeestream.web.app) *(or custom domain `https://rupeestream.app`)*

---

## 🔒 About RupeeStream

RupeeStream is an Android personal finance application built on a strict **local-first** architecture:
- **Zero Remote Financial Database:** All transaction records, accounts, budgets, and categories are stored and processed solely on the user's Android device.
- **On-Device Intelligence:** Transaction prediction, categorization assistance, Safe-to-Spend calculations, and Financial Health assessments run locally without sending personal data to remote AI APIs.
- **Encrypted Backups:** Optional Google Drive backups are encrypted on-device with **AES-256-GCM** before upload, stored exclusively within the application's isolated `appDataFolder`.
- **Zero Surveillance:** No advertising SDKs, no ad identifiers, no trackers, and no third-party data brokers.
- **RupeeStream+:** An optional one-time lifetime purchase (₹99) for extended personalization handled via Google Play Billing.

---

## 📁 Repository Scope & Architecture

> [!IMPORTANT]
> This repository is strictly the **public-facing static website and documentation**.
> The Android application source code, private signing keys, keystores, and internal build tooling are **intentionally kept in a separate private repository** to uphold security and isolation.

### Directory Structure

```text
rupeestream-showcase/
├── index.html                           # Landing showcase page
├── privacy-policy.html                  # Official 15-section Privacy Policy
├── support.html                         # Support, FAQs & troubleshooting guides
├── about.html                           # Developer & product philosophy
├── 404.html                             # Not found fallback page
│
├── assets/
│   ├── branding/
│   │   ├── logo.svg                     # RupeeStream emblem & logo
│   │   └── favicon.svg                  # High-DPI browser favicon
│   ├── css/
│   │   └── style.css                    # Modern design system (Material 3 & #10B981)
│   ├── js/
│   │   └── main.js                      # Theme switcher (Light/Dark) & mobile navigation
│   ├── icons/                           # Crisp vector SVG icons for features
│   └── screenshots/                     # Vector UI mockups and architectural diagrams
│
├── .github/workflows/
│   └── firebase-hosting-merge.yml       # Continuous Deployment to Firebase Hosting
│
├── firebase.json                        # Firebase Hosting routing & security headers
├── .firebaserc                          # Firebase project binding (rupeestream)
├── .gitignore                           # Git ignore rules for OS & credential files
└── README.md                            # Documentation
```

---

## 💻 Local Preview & Development

Because this site is built using vanilla HTML, CSS, and modern JavaScript, no build step or package installation is strictly required.

You can preview it locally using any static web server:

### Option 1: Python (Built-in)
```bash
# In the repository root:
python -m http.server 8000
```
Then visit `http://localhost:8000` in your browser.

### Option 2: Firebase CLI
```bash
# Install Firebase CLI if needed:
npm install -g firebase-tools

# Login and test locally:
firebase login
firebase emulators:start --only hosting
# or:
firebase serve --only hosting
```
Then visit `http://localhost:5000`.

### Option 3: Node.js `serve`
```bash
npx serve .
```

---

## 🚀 Architecture & Deployment Workflow

Firebase Hosting is the **canonical public website** for RupeeStream. GitHub is the **source of truth** and version control repository.

```text
GitHub (rupeestream-showcase)
        │
        │ push to main
        ▼
GitHub Actions (.github/workflows/firebase-hosting-merge.yml)
        │
        ▼
Firebase Hosting
        │
        └── https://rupeestream.web.app (Canonical Website & Privacy Policy)
```

### 1. Manual CLI Deployment
```bash
# In the rupeestream-showcase directory:
firebase deploy --only hosting
```

Your website will be live immediately at:
- `https://rupeestream.web.app`
- `https://rupeestream.firebaseapp.com`

### 2. Automated Continuous Deployment via GitHub Actions
A GitHub Actions workflow is provided at `.github/workflows/firebase-hosting-merge.yml`.

To connect GitHub Actions to Firebase Hosting:
1. Obtain the Firebase Service Account deployment credentials:
   - Run `firebase init hosting:github` or download a service account key from the [Firebase Console](https://console.firebase.google.com/) under **Project settings > Service accounts**.
2. In your GitHub repository settings under **Settings > Secrets and variables > Actions**, add the secret:
   - Name: `FIREBASE_SERVICE_ACCOUNT_RUPEESTREAM`
   - Value: *(paste the service account JSON content directly into GitHub Secrets)*
3. **Important:** Never commit the service account JSON file to the repository. The workflow only references `${{ secrets.FIREBASE_SERVICE_ACCOUNT_RUPEESTREAM }}`.
4. Any push or pull request merged into `main` will automatically deploy the latest version to Firebase Hosting.

### 3. Optional Mirror: GitHub Pages
While Firebase Hosting is the canonical production host, all internal links and asset paths are fully relative, allowing the repository to be mirrored on GitHub Pages if desired (Repository **Settings > Pages > Deploy from branch** `main` / `/ (root)`).


---

## 📄 License & Attribution

- Application Name: **RupeeStream**
- Developer: **Sayan Biswas**
- Copyright © 2025 Sayan Biswas. All rights reserved.
