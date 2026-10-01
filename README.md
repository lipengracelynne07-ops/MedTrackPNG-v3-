# MedTrackPNG v2.0.0 — Kimadan (WebView final)

**Integrated Health Centre, Clinical & Pharmacy Management System**

Offline-first Android app for Papua New Guinea facilities (Kimadan Health Center and similar).

This is the **preferred final build**: a native Android **WebView shell** that loads the full offline UI from `assets/index.html`. Data is stored in the device **browser localStorage** (no internet required for day-to-day use).

---

## Why this build

| Point | Detail |
|-------|--------|
| Matches your working APKs | Same architecture as the debug APKs you built |
| Full UI in one HTML file | Easier to update screens without large Java UI code |
| Offline | `file:///android_asset/index.html` + `localStorage` |
| GitHub Actions | Push to `main` → builds debug APK |

---

## Open and build

1. Unzip this archive  
2. Open folder **`MedTrackPNG-WebView-FINAL`** in **Android Studio**  
3. Gradle sync → Run on phone (Android 6.0+ / API 23+)

```bash
./gradlew assembleDebug
# APK: app/build/outputs/apk/debug/
```

### Upload to GitHub

```bash
cd MedTrackPNG-WebView-FINAL
git init
git add .
git commit -m "MedTrackPNG Kimadan v2.0.0 WebView final"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/MedTrackPNG.git
git push -u origin main
```

---

## App identity

| Field | Value |
|-------|--------|
| applicationId | `pg.medtrack.png.v2` |
| versionName | `2.0.0` |
| versionCode | `200` |
| minSdk | 23 |

---

## Project layout

```text
MedTrackPNG-WebView-FINAL/
├── app/src/main/
│   ├── assets/index.html          ← full offline UI + local data
│   ├── java/.../MainActivity.java ← WebView shell
│   ├── AndroidManifest.xml
│   └── res/
├── .github/workflows/build-apk.yml
├── docs/                          ← design PDF (if present)
├── README.md
├── COPYRIGHT.md / AUTHORS.md
└── LICENSE
```

---

## Important notes

- **Data lives on the device** in WebView localStorage. Clearing app data wipes the facility database.  
- For long-term production, plan **export/backup** (the UI includes export where implemented) and later a stronger SQLite backend if needed.  
- Change any demo passwords/users before live clinical use.  
- This is a **facility tool candidate** — still requires local testing and acceptance.

---

## Co-creators

- **Ends** — Project Creator / Co-Author  
- **Francis Lui** — Co-Author; Pharmacy Assistant, Kimadan Health Center, PS06 NIPHA, Kavieng Provincial Pharmacy  

© 2026 MedTrackPNG Project
