# Privacy Policy for RupeeStream

**Last Updated**: October 24, 2026

**RupeeStream** ("we", "our", or "us") is committed to respecting and protecting your privacy. This Privacy Policy explains how data is handled when you use the RupeeStream mobile application on Android.

---

## 🔒 1. Local-First Architecture & Financial Records

RupeeStream is designed as a **local-first personal finance application**:

- **No Developer Application Servers**: RupeeStream does not operate external database servers or cloud infrastructure to collect, store, or process your personal financial records.
- **On-Device Storage**: Your transactions, account balances, categories, budgets, recurring items, financial goals, and app lock credentials are saved locally on your device within an isolated application database.
- **No Developer Collection**: We do not collect, view, sell, or store your personal financial data on our servers.

---

## 🤖 2. RupeeStreamAI & Speech Processing

RupeeStream includes on-device artificial intelligence and voice features:

- **Local NLU Model**: RupeeStreamAI uses an on-device ONNX Natural Language Understanding (NLU) model to interpret financial commands. Processing occurs entirely in memory on your device. Your financial prompts, draft transactions, and account details are never transmitted to remote AI cloud services or third-party Large Language Model (LLM) APIs.
- **On-Device Speech Recognition**: When you use voice input, RupeeStream utilizes Android's native on-device speech recognition on supported Android versions (Android 12+ / API 31+). On unsupported Android versions or devices without on-device voice model support, speech recognition is disabled to prevent unencrypted cloud voice routing, and natural language text input is used instead. Voice audio is not stored or collected by us.

---

## 📢 3. Advertising & Google Mobile Ads (AdMob)

To support the free tier of RupeeStream, the app displays banner advertisements and optional rewarded ads:

- **AdMob SDK**: Advertisements are served by Google Mobile Ads (AdMob).
- **Identifier Usage**: AdMob may process device identifiers, including the Android Advertising ID (`AD_ID`), IP address, coarse location, and ad interaction metrics for ad serving, frequency capping, ad performance reporting, and click fraud prevention.
- **Analytics ADID Distinction**: While Google Analytics Advertising ID collection (`google_analytics_adid_collection_enabled`) is explicitly disabled in our application manifest, Google Mobile Ads / AdMob independently processes `AD_ID` for ad serving in accordance with Google's Advertising policies.
- **Removing Ads**: Upgrading to **RupeeStream+** or activating a temporary trial disables ad requests and ad display within the app.

---

## 💳 4. In-App Purchases & Google Play Billing

RupeeStream offers an optional paid upgrade called **RupeeStream+**:

- **Payment Processing**: All purchases—including the **RupeeStream+** lifetime one-time upgrade—are processed securely through Google Play Billing.
- **Payment Security**: RupeeStream does not collect, receive, or store credit card numbers, debit card details, bank account info, or billing addresses. All payment transactions are handled exclusively by Google Play.
- **Entitlement Data**: We receive only purchase verification tokens and entitlement confirmation status from Google Play to unlock premium features.

---

## 📊 5. Diagnostic & Crash Reporting (Firebase)

RupeeStream includes diagnostic and crash reporting powered by Google Firebase (Firebase Analytics and Firebase Crashlytics) to help maintain application health:

- **Enabled by Default**: Diagnostic reporting is enabled by default on fresh installs to help detect crashes, app errors, and basic feature interaction events (e.g., dashboard views or backup completions).
- **User Opt-Out Control**: You can disable diagnostic reporting at any time under **Settings -> Privacy & Security -> Share Diagnostic Data**. Turning this setting OFF immediately stops future collection of diagnostic metrics and crash reports.
- **Zero Financial Data**: Diagnostic reports never contain transaction amounts, account balances, merchant names, transaction notes, account numbers, email addresses, or personal financial details.
- **Firebase Cloud Messaging (FCM)**: RupeeStream uses FCM to send critical app update notifications. FCM registers an anonymous device token with Firebase servers. Notification permissions can be controlled at any time in your Android system settings.

---

## ☁️ 6. Google Drive Backup & Restore (Optional)

RupeeStream includes an optional cloud backup feature for user data protection:

- **User Control**: Google Drive backups are 100% optional and user-initiated.
- **Private App Folder Access**: Backups are uploaded exclusively to your private Google Drive application folder (`appDataFolder`). RupeeStream cannot access, read, or modify any other files in your Google Drive.
- **AES-256-GCM Encryption**: Before leaving your device, your database backup file is encrypted on-device using **AES-256-GCM** encryption.
- **Key Security & Recovery**: Your backup master encryption key is wrapped using the hardware-backed **Android KeyStore** and backed up to **Google Blockstore** for key restoration across device reinstalls.
- **Deletion**: You can delete your cloud backup or disconnect Google Drive access at any time within the app under **Settings -> Backup & Restore**.

---

## 🔑 7. Device Permissions

RupeeStream requests specific Android permissions only when needed for app functionality:

- **Microphone (`RECORD_AUDIO`)**: Requested dynamically when using voice input in RupeeStreamAI.
- **Notifications (`POST_NOTIFICATIONS`)**: Requested on Android 13+ to deliver bill reminders, budget alerts, and backup notifications.
- **Biometric (`USE_BIOMETRIC`)**: Used strictly on-device via Android `BiometricPrompt` to unlock the app if App Lock is enabled.

---

## 👤 8. Children's Privacy

RupeeStream is not directed to children under the age of 13, and we do not knowingly collect personal information from children.

---

## 📑 9. Changes to This Privacy Policy

We may update this Privacy Policy periodically. Any updates will be published within the application and updated in our public repository.

---

## ✉️ 10. Contact Us

If you have questions or concerns regarding this Privacy Policy or your data privacy, please contact us:

- **Email**: sbiswas001.tech@gmail.com
- **GitHub Repository**: [https://github.com/Sbiswas001/RupeeStream](https://github.com/Sbiswas001/RupeeStream)
- **Privacy Policy URL**: [https://rupeestream.web.app/privacy-policy](https://rupeestream.web.app/privacy-policy)
