# MACCARDANO Android App

**Tangem companion app for [maccardano.online](https://maccardano.online)**

Signs multi-sig transaction requests from the MACCARDANO website using your Tangem card, and shows you which wallet address to use when creating or joining a multi-sig wallet.

---

## Download

**[⬇ Download APK](https://github.com/maccardano/maccardano-android/releases/latest)**

> iOS version coming soon.

---

## What It Does

### 1. Sign Transaction Requests

When you sign a proposal on maccardano.online, the website shows a QR code containing a signing request in JSON format.

**Flow:**
1. Open the app → tap **Sign Request**
2. Scan the QR code from the MACCARDANO website
3. Tap your Tangem card to the back of your phone (NFC)
4. The app signs the request and shows a response JSON
5. Paste the response JSON back into the website

The signed response is also in JSON format — copy and paste it directly into the signing field on the website.

---

### 2. List Card Wallets

Not sure which address to use for MACCARDANO? The app shows all wallet addresses stored on your Tangem card.

**Flow:**
1. Open the app → tap **List Card Wallets**
2. Tap your Tangem card to the back of your phone
3. The app lists all wallet addresses on the card
4. Find the **Cardano** address — this is the one to use on maccardano.online

Use this address when:
- Adding yourself as a signer when creating a new multi-sig wallet
- Loading an existing wallet by entering your signer address

---

## Requirements

- Android 8.0 or higher
- NFC enabled on your device
- A Tangem card with a Cardano wallet

**To enable NFC:**
Settings → Connected devices → NFC → On

---

## How to Install

Since the app is not yet on Google Play, install it directly:

1. Download the APK from the [Releases](../../releases/latest) page
2. On your Android phone, go to **Settings → Install unknown apps**
3. Allow installation from your browser or file manager
4. Open the downloaded APK and tap **Install**

> Google Play and App Store versions coming soon.

---

## How to Use with MACCARDANO Website

### Signing a Proposal

On **maccardano.online → Manage Wallet → Sign Proposal**:

1. The website displays a QR code with the signing request
2. Open the MACCARDANO app → tap **Sign Request**
3. Point your camera at the QR code to scan it
4. Tap your Tangem card to the back of your phone when prompted
5. The app shows a JSON response — copy the entire text
6. Paste it into the **"Paste Tangem JSON response"** field on the website
7. Done — your signature is recorded

### Finding Your Wallet Address

On **maccardano.online → Create Wallet** (adding signers):

1. Open the MACCARDANO app → tap **List Card Wallets**
2. Tap your Tangem card to the back of your phone
3. Find the row labeled **Cardano**
4. Copy that address
5. Paste it into the **"Signer address"** field on the website

---

## JSON Format

The app works with standard JSON for both input and output.

**Signing request (input — from QR code):**
```json
{
  "tx_cbor": "84a400...",
  "proposal_id": "084953c9",
  "wallet_address": "addr1xx...",
  "signer_kh": "b95826c7...",
  "amount_ada": 10.0,
  "recipient": "addr1q9...",
  "type": "send"
}
```

**Signed response (output — paste into website):**
```json
{
  "public_key": "7d30196462fe...",
  "signature": "97d4a8f3bc...",
  "proposal_id": "084953c9"
}
```

---

## Privacy & Security

- The app **never connects to the internet**
- No data is sent to any server
- Your Tangem card private key never leaves the card
- Signing happens entirely on the card's secure chip via NFC
- The app only reads the public key and signature from the card

---

## Troubleshooting

**Card not detected**
- Make sure NFC is enabled in Android settings
- Hold the card flat against the back of your phone for 1-2 seconds
- Remove any thick phone case that may block NFC

**QR code not scanning**
- Make sure the QR code is fully visible on screen
- Increase screen brightness
- Hold the phone steady 20-30cm from the screen

**Wrong address shown**
- If your Tangem card has multiple wallets, make sure you pick the one labeled **Cardano**
- The address starts with `addr1`

---

## Links

- Website: [maccardano.online](https://maccardano.online)
- CLI recovery tool: [maccardano_cli](https://github.com/maccardano/maccardano_cli)

---

*MACCARDANO © 2025 — Built on Cardano*
