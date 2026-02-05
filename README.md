
# CreatorShield

**Real-time protection against hate speech on Instagram**

CreatorShield is a Chrome extension designed to protect content creators from harmful comments **before they read them**.

It focuses on:

* **Hate speech detection first**
* **Subtle discouraging harassment** as an additional layer
* **Speed, privacy, and creator control**

This repository contains a **demo-ready build** for hackathon evaluation.

---

## 🚨 The problem

Creators regularly face:

* Explicit insults and slurs
* Abusive and dehumanizing language
* Repeated discouraging comments

Platform moderation is often **reactive**.
Creators usually see the comment **before** it gets removed.

**The harm is already done.**

---

## 🛡️ What CreatorShield does

CreatorShield applies a **layered protection pipeline** in real time:

```
Comment appears
       ↓
Instant local checks
(profanities + creator-defined keywords)
       ↓
Hate speech → detected by our primary model
→ escalated to OpenAI moderation only when needed
Soft discouraging harassment → blurred or flagged by our SetFit model
       ↓
Creator control and feedback
(to unhide, correct mistakes, and improve future decisions)
```

---

## ✨ Key features

* Real-time comment filtering on Instagram
* Hate speech detection with fallback safety layer
* Soft discouraging harassment detection (non-profane)
* Local keyword-based blurring for fast mitigation
* Creator-controlled allow / unhide actions

---

## ⚙️ Architecture overview

* **Chrome Extension**

  * Observes Instagram comments in the DOM
  * Applies local rules and visual blurring
* **Backend (Self-hosted)**

  * Handles AI inference and orchestration
* **AI Models**

  * Hate speech model
  * SetFit model for subtle discouraging harassment
  * OpenAI moderation used only as fallback for edge cases

---

## 🔒 Privacy & trust

* Backend is **self-hosted**
* No third-party moderation dashboards
* No permanent storage of comments in the demo
* Designed to reduce exposure before analysis

---

## 🚀 Install the demo extension (IMPORTANT)

⚠️ **The Chrome extension must be loaded from the `dist/` folder.**

The source code is included for reference,
but **only the built build will work correctly in Chrome**.

### Steps (takes < 1 minute)

1. Open Chrome and go to:

   ```
   chrome://extensions
   ```
2. Enable **Developer mode** (top-right)
3. Click **Load unpacked**
4. **Select the `dist/` folder** from this repository
   ❗ *Do NOT select the root folder*

Once loaded, the CreatorShield icon should appear in the toolbar.

---

## 🧪 Demo notes

* This is a **demo environment**
* Accuracy is intentionally conservative
* False positives and false negatives are expected
* The demo focuses on **responsible handling of mistakes**

---

## 📎 Repository structure

```
creatorshield-demo/
├── dist/              ← LOAD THIS FOLDER IN CHROME
│   ├── manifest.json
│   ├── popup.html
│   ├── popup.css
│   ├── background.js
│   └── assets/
│       └── logo.png
├── src/               ← source code (reference only)
├── README.md
└── INSTALL.txt
```

---

## 🏁 Status

CreatorShield is an **active prototype** developed for hackathon evaluation.

---
