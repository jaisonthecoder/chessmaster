# 15. Business, Legal & Compliance

This document covers what could block a launch: the product name, licences, children's privacy law,
app-store rules for kids' apps, school requirements, and the business model.

> This is a planning checklist, not legal advice. Every item marked ⚖️ needs confirmation by qualified counsel
> in each launch country before release.

---

## 15.1 Product name ⚖️

"Chessmaster" is a long-running chess video-game brand (including a chess-tutorial title), so **"ChessMaster Academy"
is high-risk** as a product name.

- Run a trademark clearance search in every launch market (for example US, EU, UK, India, UAE, Saudi Arabia) before any branding work.
- Shortlist alternative names now, so a rename doesn't delay design work.
- Until cleared, treat "ChessMaster Academy" as a working title only.

Other names to avoid or check:

| Name | Issue | Action |
|---|---|---|
| "Candy Land" (board theme) | A toy company's trademark | Renamed to **Sweet Treats** |
| "Puzzle Rush" | A feature name used by a major chess site | Renamed to **Puzzle Dash Jr.** |
| "FIDE", federation logos | Must not suggest endorsement | Use the name only in factual descriptions; no logos |
| In-app "titles" | Could be confused with FIDE titles | Call them **ranks** or badges in the app, never "GM", "IM" and so on |

## 15.2 Open-source and asset licences ⚖️

| Component | Licence (verify at adoption) | What it means for us |
|---|---|---|
| **Stockfish** (engine) | GPLv3 | Distributing it requires the licence text and the source code, and GPL terms can apply to a combined work. App-store terms have conflicted with the GPL before, and the Stockfish authors have enforced their licence. **Get a legal opinion.** Keep the engine as a separate, replaceable component, publish its source, and check the licence of the neural-network files too |
| Maia models (if used) | GPL-3.0 | Same considerations as Stockfish |
| chess.js | BSD-2-Clause | Attribution |
| Lichess puzzle database | CC0 (public domain) | Free to use; attribution appreciated |
| Three.js, React Three Fiber, drei, Zustand, XState, Howler.js, i18next, Capacitor | MIT | Attribution |
| Dexie | Apache-2.0 | Attribution, notice file |
| GSAP | Its own no-charge licence (not open source) | Read the terms; consider an MIT alternative |
| Rive runtimes | Check current licence | Attribution |
| Noto fonts | SIL Open Font License | Attribution |
| Rhubarb Lip Sync (tool) | Check current licence | Used offline in the pipeline |
| 3D models, HDRIs, sound effects, music | Per asset | Every asset in a **licence register**, with source, licence and proof of purchase |

The app has an **"Open-source licences and credits"** screen (H12).

## 15.3 Children's privacy ⚖️

| Law | Key requirements for us |
|---|---|
| **COPPA (US)**, including the 2025 rule changes (compliance required by April 2026) | Verifiable parental consent before collecting personal data from children under 13; **separate consent** before disclosing children's data to third parties (for example the AI provider, text-to-speech provider, email service); a **written information-security programme**; a **written data-retention policy** (keep data only as long as needed). Consider joining a COPPA Safe Harbor programme |
| **GDPR (EU) and UK GDPR** | The age of digital consent is 13–16 depending on the country; parental consent below it. A **data-protection impact assessment (DPIA)** is required. Data-processing agreements with every processor; documented international transfers |
| **UK Age Appropriate Design Code (Children's Code)** | High-privacy defaults, no nudging, data minimisation, a DPIA, child-friendly privacy information |
| **India: Digital Personal Data Protection Act 2023** | "Child" means under 18; **verifiable parental consent** for all children's data; no tracking, behavioural monitoring or targeted advertising directed at children. Important for the Hindi and Malayalam launch |
| **UAE Personal Data Protection Law** (and Saudi PDPL if targeted) | Consent, purpose limitation, cross-border transfer rules |

**Design consequences (already in the plan):**
- Local-only play needs no personal data: avatar, age band and progress, on the device.
- Analytics IDs are pseudonymous (personal data), so they are covered by consent and the DPIA, not described as "anonymous".
- No names, photos or free-text chat from children. Certificate names are typed by a parent into the PDF on the device and never stored.
- Voice commands use on-device speech recognition only; children's voices are never sent to a server.
- Live AI features for under-13s need a parent opt-in, which is also the separate third-party consent.
- Every processor (hosting, email, text-to-speech, AI provider, crash reporting) is listed in the privacy notice and has a data-processing agreement.

## 15.4 App-store kids-category compliance ⚖️

| Store | Requirements | How we comply |
|---|---|---|
| **Apple App Store, Kids Category** | No third-party analytics or advertising SDKs; a parental gate before links outside the app, purchases and requests for permission; privacy "nutrition labels"; age rating questions (including AI features) | First-party analytics only; self-hosted crash reporting; parent PIN for purchases and settings; simple gate for links |
| **Google Play, Families policy** | Only SDKs certified for families; a target-audience and content declaration; the Data Safety form; consider the "Teacher Approved" programme | SDK allow-list reviewed before every release |
| **Amazon Appstore (Fire tablets)** | Kids content requirements and privacy | Same build rules as Google Play |
| **All stores** | IARC content rating; a working "Restore purchases" button; clear subscription terms | Screens H10 and G12 |

**SDK allow-list rule:** no third-party SDK enters the child app without a privacy and store-policy review. **The child app sends no push notifications**; parents get notifications through the parent web dashboard and email.

## 15.5 Schools ⚖️

| Requirement | Action |
|---|---|
| **FERPA** and the COPPA school-authorisation route (US) | Schools can consent on parents' behalf only for educational use; school data is never used for marketing |
| **US state student-privacy laws** (for example California SOPIPA, New York Education Law 2-d) | Sign state or national student data-privacy agreements (for example the SDPC National Data Privacy Agreement) |
| **Security expectations** | Plan for SOC 2 or ISO 27001 as school sales grow |
| **Accessibility** | Publish an accessibility conformance report (VPAT) against WCAG 2.2 AA; US public schools must meet the ADA Title II web-accessibility rule; the European Accessibility Act applies to consumer e-commerce flows |
| **Shared classroom devices** | Class sign-in with picture passwords or QR badges (I8); rostering through Google, Microsoft, Clever, ClassLink or OneRoster (I9); teacher verification (I11) |

## 15.6 Online safety and AI rules ⚖️

- **UK Online Safety Act:** friend games (even with emotes only) and classroom-shared content make the app a user-to-user service, so a children's risk assessment is needed before those features launch.
- **EU AI Act:** from August 2026, people must be told when they are interacting with AI. Live AI answers are marked "✨ written by AI" (document 13).
- **AI provider terms:** review Anthropic's usage policies for products used by minors, the required safeguards, and data-retention options for the chosen model before launch.

## 15.7 Real people and voices ⚖️

- **Real chess players:** Hall of Legends uses historical facts and published games. Living players' names, likenesses or voices are not used as characters or in marketing without written permission, and nothing suggests their endorsement.
- **Voice actors:** adult performers voice child characters (or child-performer law is followed). Contracts cover all four languages, use alongside text-to-speech, union terms where applicable, and **forbid voice cloning or synthetic voices built from the actor without separate consent and payment**.

## 15.8 Advertising to children ⚖️

Marketing follows children's advertising rules in each market (for example CARU guidelines and FTC rules in the US, ASCI in India, and UAE media rules). No promises of becoming a master or of rating gains; claims about learning are backed by the pilot study data.

---

## 15.9 Business model (proposal)

| Item | Proposal |
|---|---|
| **Free forever** | Levels 0–3 (every rule of chess), in all languages; bots up to Rocky; Daily Puzzle; no ads, ever |
| **Family subscription** | Monthly and yearly plans covering up to 4 child profiles; a 7-day free trial started by a parent |
| **Regional pricing** | Prices set per market (for example lower in India than in the Gulf), based on research with parents |
| **School licence** | Per student per year, or per school; free or discounted licences for under-resourced schools |
| **If a subscription lapses** | Nothing is taken away: progress, stars, badges and earned items stay forever. Locked kingdoms can still be reviewed; new lessons wait until the plan is renewed |
| **Across devices** | Entitlements belong to the parent account, so a purchase works on web, iOS and Android, following each store's current rules on external purchases |
| **Codes** | Gift and school codes redeemed by a parent (H10) |
| **Live AI** | Included in the subscription, within the per-child daily budget (document 13) |
| **Never** | Ads, loot boxes, in-app currency, paid hints, pay-to-win, purchase prompts aimed at children |

## 15.10 Launch checklist

1. Trademark clearance done; final name chosen.
2. Legal opinion on Stockfish (GPL) and the app stores; licence register complete; credits screen in the app.
3. Privacy notice, DPIA, data-retention policy, security programme, processor agreements, parental-consent flow (per country).
4. Kids-category review: SDK allow-list, parental gates, store forms.
5. Accessibility report (WCAG 2.2 AA).
6. Voice contracts signed for all four languages.
7. AI: usage-policy review, data-retention confirmed, "written by AI" label, under-13 opt-in.
8. School pack (for school pilots): data-privacy agreement, class sign-in, teacher verification.
