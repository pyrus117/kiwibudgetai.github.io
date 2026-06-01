---
layout: default
title: Kiwi Budget AI — Privacy Policy
---

# Kiwi Budget AI — Privacy Policy

**Last updated:** 1 June 2026
**Effective from:** 1 June 2026

This policy explains how the Kiwi Budget AI mobile application ("the App", "we", "us") handles your personal information. It is written to comply with the New Zealand **Privacy Act 2020** and its thirteen Information Privacy Principles (IPPs).

If you would prefer to read this policy in plain English, the **Summary** section below covers the essentials. The remainder of the document maps our practices to each of the Privacy Act's IPPs.

---

## Summary (plain English)

- **Your bank data stays on your phone.** The App connects to your bank accounts through Akahu using tokens that you generate yourself. Those tokens, your account balances, your transactions and all derived data (categorisations, budgets, goals) are stored **only on the device you install the App on**. We do not host them.
- **AI features call Google Gemini using your own API key.** When you ask the AI assistant a question, or when the App auto-categorises transactions, your transaction description and amount are sent to Google's Gemini API using a key **you** supply. We never see those requests.
- **You sign in with your Google account.** Sign-in is handled by Google / Firebase Authentication. We receive a unique user ID and the email address you sign in with so we can keep your settings tied to your account.
- **Ads are served by Google AdMob.** AdMob may collect a device advertising identifier subject to Google's privacy policy and your device's ad personalisation settings.
- **Bug reports.** If you submit a bug report from the Settings page, the text you write plus your platform/version/user agent is sent to our Firebase database. Your Akahu tokens, Gemini key, and transaction data are **never** included in bug reports.
- **No analytics, no advertising profile built by us, no data sold.** We do not run analytics SDKs, we do not build profiles of you for advertising, and we do not sell, rent, or trade any personal information.

If you have questions, complaints, or want to exercise your rights (e.g. access or correction), contact **tooty.fruity.tooty@gmail.com**.

---

## 1. Who we are

The "agency" operating the App for the purposes of the Privacy Act 2020 is the App's publisher (Farrow Counselling / Kiwi Budget AI maintainer), contactable at **tooty.fruity.tooty@gmail.com**.

The App is published from New Zealand and is primarily intended for New Zealand users (because it integrates with Akahu, the NZ open-banking aggregator). The App is available on Google Play.

---

## 2. What information we collect, and what we don't

### 2.1 Information stored only on your device (we never receive it)

The following data is stored exclusively on your Android device using encrypted on-device preferences (`@capacitor/preferences`) and the WebView's local storage:

- Your Akahu **App Token** and **User Token**
- Your **Gemini API key**
- Your bank **accounts**, **balances**, and **transactions** retrieved from Akahu
- Your **categories**, **budgets**, **goals**, **subscriptions**, and any manual category overrides
- **Receipt images and PDFs** you attach to transactions. When you choose to attach a receipt, the App reads the photo, image, or PDF you select (via your device's camera or photo library) and stores it inside the App's own private data folder. Receipts never leave your device.
- **Notification preferences and budget-alert state** used to schedule spending alerts. Notifications are composed and fired entirely on your device. No notification content is sent off-device.

We have no servers that hold this data. If you uninstall the App or use the in-app "Clear local credentials" option in Settings, this data is removed from your device.

The App requests the following Android permissions to support the features above:

- **Camera** and **Photos / Media access** — only used when you attach a receipt to a transaction. The App never opens the camera or reads your photo library in the background.
- **Post notifications** — required from Android 13 onwards to display the budget-alert and reminder notifications you opt into in Settings.
- **Biometric / device credential** — only used when you turn on App Lock in Settings, so the App can ask your phone's biometric/PIN before unlocking. No biometric data leaves your device or is ever shared with us.

### 2.2 Information we (or our processors) do receive

- **Authentication identifiers**: when you sign in with Google, Firebase Authentication (operated by Google) provides us with your unique Firebase user ID and the email address associated with your Google account. We use this only to keep your in-app settings tied to your account.
- **Bug reports**: any text you type into the "Report a bug" form in Settings, plus a small block of diagnostic information (operating system, app version, user agent string, your Firebase user ID and email so we can reply). We store these in a Firebase Firestore collection that is **not readable from any device** — only the developer can read them, via the Firebase admin console.
- **Crash and ad-serving signals** collected by Google AdMob when the App shows ads. See section 6.

### 2.3 Information sent to third parties when you use specific features

- When the App calls the **Akahu API** to fetch your accounts and transactions, your Akahu tokens are sent directly from your device to `api.akahu.io` over HTTPS. We do not proxy or observe these calls.
- When the App calls the **Google Gemini API** for chat or auto-categorisation, your Gemini API key and the request payload (the transaction descriptions/amounts being categorised, or the chat message you typed plus the financial context you have chosen to share in chat) are sent directly from your device to Google. Refer to Google's privacy policy for how Gemini processes inputs.

---

## 3. Mapping to the Privacy Act 2020 Information Privacy Principles

### IPP 1 — Purpose of collection
We collect personal information only for these purposes: (a) authenticating you so we can scope your settings to your Google account; (b) responding to bug reports you submit; (c) serving advertisements through AdMob to support development of a free app. Bank, transaction, and AI prompt data is never collected by us.

### IPP 2 — Source of personal information
Personal information is collected directly from you (when you sign in, type a bug report, or enter API tokens) and from Google Firebase Authentication (which authenticates you on our behalf).

### IPP 3 — Collection of information from the subject
This policy itself, together with on-screen notices during sign-in and on the Settings page, informs you what is collected, why, who receives it, and your rights. The notices appear before collection occurs.

### IPP 4 — Manner of collection
We collect information only by lawful, fair and non-intrusive means. We do not deceive you about what we collect or use hidden tracking.

### IPP 5 — Storage and security
- On-device data (Akahu tokens, Gemini key, transactions) is stored in the Android Keystore-backed encrypted preferences store and the App's private WebView local storage. It cannot be read by other apps.
- Off-device data (Firebase authentication records, bug reports) is stored in Google Firebase services subject to Google's security commitments (encryption in transit and at rest, ISO 27001 / SOC 2 / SOC 3).
- Firestore security rules restrict bug reports so that no client can read or modify them once created.
- We do not back up Akahu tokens, your Gemini key, or your transactions to any cloud service.

### IPP 6 — Access to personal information
You can:
- See your in-app data at any time within the App.
- Email **tooty.fruity.tooty@gmail.com** to request a copy of any personal information we hold about you off-device (Firebase auth record, bug reports you submitted). We aim to respond within 20 working days as required by the Privacy Act.

### IPP 7 — Correction of personal information
If any information we hold about you is wrong, email **tooty.fruity.tooty@gmail.com** and we will correct it or attach a statement of correction.

### IPP 8 — Accuracy
We rely on Google for the accuracy of authentication details. For bug reports, we rely on what you submit. We do not derive analytical conclusions about you.

### IPP 9 — Retention
- **On-device data** persists until you uninstall the App or clear it via Settings.
- **Firebase authentication records** persist until you ask us to delete your account.
- **Bug reports** are retained for up to 24 months from receipt to allow follow-up, then deleted.

### IPP 10 — Use of personal information
We use personal information only for the purpose for which it was collected (section 2 above). We do not repurpose it.

### IPP 11 — Disclosure of personal information
We do not disclose personal information to third parties except:
- to Google, in its capacity as our authentication provider (Firebase Auth), database provider (Firestore for bug reports), and ad network (AdMob);
- to Akahu, only when you initiate a call from your device using tokens you supplied;
- when required by law.

We do **not** sell, rent, or trade personal information.

### IPP 12 — Disclosure outside New Zealand
Firebase services (authentication, Firestore for bug reports) are operated by Google and may store data on servers located outside New Zealand, primarily in the United States and the European Union. Google is bound by its own privacy commitments and, where applicable, the EU-US Data Privacy Framework. Akahu is a New Zealand company and processes data within New Zealand. Google AdMob may transfer ad-serving data internationally subject to Google's policies.

By using the App you consent to these international transfers. If you do not consent, please discontinue use of the App.

### IPP 13 — Unique identifiers
We assign no unique identifier of our own. The Firebase user ID provided to us by Google is the only such identifier and is used solely to keep your settings tied to your account.

---

## 4. Children

The App is not directed at children under the age of 13 and we do not knowingly collect information from them. AdMob is configured for general (non-child-directed) treatment.

---

## 5. Cookies and tracking

The App's WebView uses local storage to hold the cached items listed in section 2.1. The App does **not** use third-party analytics, third-party cookies, or cross-app tracking SDKs.

---

## 6. Advertising (Google AdMob)

The App displays a banner ad at the top of the screen via Google AdMob. AdMob may collect:

- An advertising identifier provided by your device (you can reset or limit this in Android Settings → Privacy → Ads);
- Coarse usage information (impressions, clicks, IP-derived approximate location, device model);
- Other signals described in Google's privacy policy at <https://policies.google.com/privacy>.

AdMob operates as an independent controller for the data it collects. You can opt out of personalised advertising in your Google Account settings or via the Android device's ad-personalisation toggle. The App requests non-personalised ads where possible.

---

## 7. Your rights under the Privacy Act 2020

You have the right to:

1. Ask what personal information we hold about you (IPP 6).
2. Ask us to correct that information (IPP 7).
3. Withdraw consent and request deletion of off-device data we hold about you.
4. Complain to the Office of the Privacy Commissioner (<https://www.privacy.org.nz/>) if you believe we have breached the Privacy Act.

Contact us first at **tooty.fruity.tooty@gmail.com** — we aim to resolve concerns within 20 working days.

---

## 8. Security incidents

If we become aware of a privacy breach that is likely to cause serious harm to you, we will notify you and the Privacy Commissioner as required by Part 6 of the Privacy Act 2020. Because we hold so little of your data, the practical risk surface is limited; the most material risk is loss of your Akahu tokens through compromise of your device, which is why we never transmit those tokens off your device.

---

## 9. Changes to this policy

We may update this policy from time to time. Material changes will be highlighted in the App's release notes. The current published version is always available at **<https://pyrus117.github.io/kiwibudgetai.github.io/>** and is also linked from the App's Settings page.

---

## 10. Contact

**Kiwi Budget AI**
Email: **tooty.fruity.tooty@gmail.com**

For privacy complaints you may also contact:
**Office of the Privacy Commissioner**
PO Box 10094, Wellington 6143
<https://www.privacy.org.nz/>
