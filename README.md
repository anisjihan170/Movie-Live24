# MovieLive2473 — Dark Hybrid Android WebView App

A Kotlin/AndroidX shell for `https://movielive2473.blogspot.com` with fullscreen dark presentation, HTML5 video support, click interception, smartlink routing, a lightweight coin wallet, VIP payment modal, and fixed bottom navigation.

## Configure before release

Replace the placeholders in `app/src/main/res/values/strings.xml`:

- `smartlink_url`: your Adsterra Direct Smartlink
- `reward_url`: your approved Adsterra rewarded/video flow
- `telegram_url`: your real support chat
- `binance_pay_id` and `usdt_wallet_address`: your published payment details

Replace the QR placeholder in `MainActivity.kt` with a branded QR drawable, and connect TxID submission to a secure backend before granting VIP. Never grant VIP solely on client-side state; verify blockchain settlement server-side and protect admin review credentials.

## Build APK and AAB

```bash
./gradlew assembleDebug
./gradlew assembleRelease
./gradlew bundleRelease
```

Outputs appear under `app/build/outputs/apk/` and `app/build/outputs/bundle/`. Configure a signing key in `keystore.properties`/Gradle for production release builds; do not commit that file.

## Production notes

- Use a backend for rewarded-ad callbacks, coin balances, TxID verification, VIP entitlements, abuse prevention, and audit logs.
- Replace placeholder ad/payment URLs and support username before publishing.
- Review the website's content rights and Google Play policy eligibility. Streaming copyrighted content or aggressive interstitial routing may be rejected without appropriate rights and disclosures.
- The app disables cleartext traffic, file/content access, and multiple windows by default.
