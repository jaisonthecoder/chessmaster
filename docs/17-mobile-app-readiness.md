# 17. Mobile App Readiness

**Goal:** the app starts as a web app, and can be published later as **iPhone/iPad, Android and Amazon Fire apps**
without rewriting it.

**How:** one TypeScript codebase, wrapped for the app stores with **Capacitor** (which runs the web app inside a native
app shell and gives it access to native features through plugins). This only works smoothly if the code follows a
few rules **from the first day**. This document lists them.

---

## 17.1 The strongest guarantee: build the mobile shells from day one

Don't wait until "later" to try mobile. In **Phase 0 (week 1–2)**:
1. Create the Capacitor iOS and Android projects next to the web app.
2. Run the 3D board prototype on a real iPad, a cheap Android tablet and a school Chromebook.
3. From then on, **every automated build produces three outputs**: the web app, an Android app and an iOS app.
   Testers install the mobile builds (TestFlight for iOS, Play internal testing for Android) every week.

The apps don't have to be *published* early, but they are always *buildable and tested*. Converting later is then
just a store submission.

## 17.2 Architecture rules that keep the app portable

| Rule | Why |
|---|---|
| **Core logic has no browser code.** `chess-core`, `lesson-runtime`, `adaptive`, `engine` (rules, lessons, mastery, bots) are pure TypeScript with no access to the page, browser storage or network | They run unchanged in a web page, in Capacitor, or even in a different mobile framework if one is ever needed |
| **One "platform adapter" for anything device-specific** | Every feature that differs between web, iOS and Android goes through one interface (17.3). The rest of the app never calls browser or native APIs directly |
| **Touch-first design** | No hover-only actions; 48 dp buttons; tap-tap moves (document 6) |
| **Works in portrait and landscape** | Phones mostly portrait, tablets both |
| **Safe areas respected** | Layout keeps clear of notches, rounded corners and home bars (CSS `env(safe-area-inset-*)`) |
| **In-app navigation only** | Never rely on the browser's back/forward buttons or address bar. Android's hardware back button is mapped to the app's own back/home logic and never exits mid-lesson without saving |
| **Pause and resume handled** | When the app goes to the background, the lesson or Boss pauses and saves; on return it resumes exactly (document 11) |
| **Relative asset paths and offline packs** | Lessons, audio and 3D packs load the same way from the web server, from inside the app, or from a downloaded kingdom pack |
| **Single-threaded chess engine by default** | Multi-threaded WebAssembly needs special web-server headers that the app shell can't easily provide (document 7) |
| **Low-end performance budget** | The 3D quality tiers and automatic 2D fallback (document 6) protect cheap phones and tablets |

## 17.3 The platform adapter: what differs per platform

| Capability | Web (PWA) | iOS and Android apps (Capacitor) |
|---|---|---|
| **Saving progress** | IndexedDB with persistent-storage request | Native SQLite database (safe from browser storage clean-up) |
| **Voice and sound** | Web Audio | Web Audio plus a small native setting so the voice assistant plays reliably (iOS's silent switch can mute web audio; decide the behaviour in play-tests) |
| **Voice commands** (optional) | Not offered unless an on-device option exists | A native plugin using on-device speech recognition only (document 16) |
| **Text-to-speech for dynamic lines** | Pre-made audio files; server-generated audio for live AI answers | The same, so Pip sounds identical everywhere |
| **Purchases** | Web payments, for parents only | **Apple and Google in-app purchases** for digital subscriptions (store rules), with "Restore purchases". The parent account links them all |
| **Downloads of kingdom packs** | Cache storage | Native file storage, with a downloads manager (H13) |
| **Haptics (gentle vibration feedback)** | Limited | Native haptics plugin |
| **Keep screen awake during lessons** | Screen Wake Lock where supported | Native keep-awake plugin |
| **Sharing a certificate** (behind the parent gate) | Download a PDF | Native share sheet |
| **Network status** | Browser online/offline events | Native network plugin |
| **AR board** (phase 3) | WebXR on Android Chrome | Android: WebXR / ARCore. iOS: a separate native module (document 6) |
| **Electronic chessboards** (phase 3) | Web Bluetooth where available | Native Bluetooth plugin |
| **Notifications** | None for children | None in the child app; parents get email and the parent web dashboard (document 15) |

Each capability has one TypeScript interface (for example `Storage`, `Audio`, `Purchases`, `Speech`) with a web
implementation and a native implementation. Switching platform means switching the implementation, not the app.

## 17.4 App-store requirements to prepare early

| Requirement | Store | Preparation |
|---|---|---|
| Kids Category / Families policy rules | Apple, Google, Amazon | SDK allow-list, parent gates, no third-party analytics (document 15) |
| Privacy details | Apple privacy labels and privacy manifest file; Google Data Safety form | Keep a live list of all data collected and every SDK used |
| In-app purchase for digital subscriptions, plus "Restore purchases" | Apple, Google | Purchases adapter from the first paid release |
| Minimum and target OS versions | Google requires a recent target Android version each year | Update the Android target yearly; minimums in document 7 |
| App size | All | Keep the installed app small (about 50 MB or less); kingdoms, voices and languages are downloaded inside the app as content |
| Updates | All | New *code* ships through store updates. Lessons, audio, 3D packs and translations are *content* and can be downloaded without a store update. Any over-the-air update of app code must follow each store's current rules |
| Screenshots and previews per language | All | Produce store images in English, Malayalam, Hindi and Arabic |
| Accessibility | All | VoiceOver (iOS) and TalkBack (Android) tested on the 2D board and all menus |

## 17.5 Build and release pipeline

- **One repository**, with `apps/client` (the web app), and the generated `ios/` and `android/` Capacitor projects committed alongside it.
- **Continuous integration** builds the web app, the Android app and the iOS app on every merge (iOS builds need a macOS build machine).
- **Signing:** Apple certificates and the Android signing key are stored in the CI secret store, never in the repository.
- **Release automation** (for example fastlane) uploads to TestFlight, Google Play internal testing and the Amazon Appstore.
- **Device testing:** a small device lab (recent iPad, older iPad, budget Android phone, budget Android tablet, Fire tablet, Chromebook) runs the end-to-end tests before each release.

## 17.6 If the WebView ever isn't fast enough

The 3D board is the only part that could need more performance than a WebView gives on some devices. The plan already handles this in layers:
1. Quality tiers and automatic 2D mode (document 6).
2. If a future version needs it, only the **3D board view** would be rebuilt natively. Because the rules, lessons, adaptive learning and engine are pure TypeScript (17.2), they would be reused, not rewritten.

## 17.7 Checklist for developers (every pull request)

- [ ] No direct use of browser storage, audio, speech, payments or file APIs outside the platform adapter.
- [ ] Works with touch only, in portrait and landscape, on a 360-dp-wide phone.
- [ ] Respects safe areas.
- [ ] Handles pause/resume and the Android back button.
- [ ] No new third-party SDK without the allow-list review.
- [ ] Tested in the Android and iOS builds produced by CI, not only in a desktop browser.
