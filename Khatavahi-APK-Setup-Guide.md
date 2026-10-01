# ખાતાવહી (Khatavahi) — APK Setup Guide

Aa file ma badha steps chhe je apde saathe kariya, Khatavahi app ne
website thi real installable APK banavva mate. Future ma koi bhi
confusion thay to aa file jo lo.

---

## ⭐ SAUTHI AGATYNI VAAT (Future update mate)

**App nu design/features badalvu hoy to badhu pacha karvani jarur NATHI.**

Aa app ek "wrapper" chhe je live website (`tuleshgosai.github.io/khatavahi`)
batave chhe. Etle:

- Website nu `index.html` file update karo (GitHub par navi file upload karo,
  same name "index.html" rakho) → App potानी j pote update thai jashe,
  kem ke app hammesha live link j batave chhe.
- **Naa GitHub repo banavvani jarur nathi.**
- **Naa PWABuilder thi navu package banavvani jarur nathi.**
- **Naa APK Signer thi pacha sign karvani jarur nathi.**
- **Naa pacha install karvani jarur nathi** (already installed app j
  update content dekhadshe, jyare internet chalu hoy).

➡️ Sirf naya features/design ni vaat hoy tyare Claude ne kaho, e
`index.html` update kari devi, ane tame e file GitHub repo ma
upload kari do (Step 3 pramane) — BAS, ETLU J.

Naya APK/signing sirf tyare j joiye jyare:
- App nu naam badalvu hoy
- App nu icon badalvu hoy
- Package ID badalvu hoy
- Ke pachi app crash/error aave ane fresh setup joiye

---

## Overview — Su banavyu

1. Ek single-file web app (HTML) — ledger + loans tracker
2. GitHub Pages par host karyu (free, live link malyo)
3. PWABuilder thi Android package (APK) banavyo
4. APK Signer app thi phone par j sign karyu
5. Phone par install karyu

---

## Step 1 — GitHub account ane repository

1. **github.com** par account banavyu (sign up)
2. Top right **+** icon → **New repository**
3. Name: `khatavahi`, **Public** rakhyu
4. **Create repository** tap karyu

## Step 2 — Files upload karya

Repository ma aa 4 files upload karya ("Add file" → "Upload files"):

- `index.html` — mukhya app (Claude e banavyu)
- `manifest.json` — app nu naam/icon/color settings
- `icon-192.png` — nanu icon
- `icon-512.png` — motu icon

## Step 3 — Naya update mate (future)

Jyare pan `index.html` ma koi badlav hoy:

1. GitHub repo ma jao (`github.com/[username]/khatavahi`)
2. Jauni `index.html` file par tap karo
3. Pencil/edit icon tap karo, ke pachi "Add file → Upload files" thi
   navi file upload kari juni ne replace karo
4. **Commit changes** tap karo
5. 1-2 minute ma live site update thai jashe, ane app (jyare khule)
   automatically navu content batavse

## Step 4 — GitHub Pages ON karvu (ek j vaar karvani jarur)

1. Repo ma **Settings** → **Pages**
2. Branch: **main**, folder: **/(root)** → **Save**
3. Link malyo: `https://[username].github.io/khatavahi/`

## Step 5 — PWABuilder thi Android package (ek j vaar karvani jarur)

1. **pwabuilder.com** kholo, GitHub Pages link paste karo
2. **Start** tap karo, report card check karo (errors 0 hova joiye)
3. **Package For Stores** → **Android**
4. **"Other Android"** tab select karo (Google Play nahi, sidhu install
   mate aa saral chhe)
5. **Download Package** — zip file malshe jema unsigned APK hoy

## Step 6 — APK ne sign karvu (ek j vaar karvani jarur)

Android unsigned APK direct install nathi thato, etle sign karvu padyu:

1. Play Store thi **"APK Signer"** (RUBRIKPULSA SOFTWARE) app install karyu
2. **Keystores** → navi keystore banavi:
   - Keystore Name: `khatavahi`
   - Password: `khatavahi123`
   - Alias: `khatavahi`
   - Alias Password: `khatavahi123`
3. **Sign APK/AAB** → downloaded unsigned APK select karyu
4. Keystore select kari, password nakhi, **Sign Now**
5. Navi **signed APK** file malshe (same folder ma)

## Step 7 — Install karyu

1. Signed APK file par tap karyu
2. "Unknown source" allow karyu (jarur pade to)
3. **Install** tap karyu
4. Home screen par **Khatavahi** icon aavi gayu

---

## Jaruri details yaad rakhva mate

| Item | Value |
|---|---|
| GitHub repo | `khatavahi` |
| Live link | `https://tuleshgosai.github.io/khatavahi/` |
| Package ID | `io.github.tuleshgosai.twa` |
| Keystore file name | `khatavahi` |
| Keystore password | `khatavahi123` |
| Key alias | `khatavahi` |
| Alias password | `khatavahi123` |

⚠️ **Aa keystore password sachavi rakho.** Jo future ma kadi navi APK
sign karvi padi (naam/icon badalva mate), to same keystore use karvi
padse — nahi to Android juni app ne uninstall karva kahese pehla.

---

## Halni ek chhoti khami (optional fix)

App kholta upar ek thin address bar dekhay chhe (`tuleshgosai.github.io`),
kem ke domain verification (assetlinks.json) setup nathi thayu. App
kaam barabar kare chhe — offline, data save, icon — sirf ee ek line
dekhay chhe. Aa thik karva mate:

1. APK Signer ma keystore no SHA-256 fingerprint kadhavo
2. Navi repo banavvi (naam j `[username].github.io` hovu joiye)
3. Ema `.well-known/assetlinks.json` file mukvi (fingerprint sathe)

Aa optional step chhe — jyare taiyar hoy tyare Claude ne kaho, aage
vadharie.

---

## Data backup/restore

- App ni andar **⋮ menu → Export backup** — JSON file download thay,
  safe rakho
- **⋮ menu → Import backup** — koi bhi backup JSON pacha load karva
  mate, badhu current data replace thai jay (khatri kari ne j karo)

---

## App na niyam (Requirements) — aa pramane kaam karvu joiye

Aa niyam tutvay nahi e dhyan rakhvu. Navu feature umero tyare aa badha same rahevu joiye.

### 1. Ek j sachu hisab: Ledger
- **Cash in hand = Ledger no Balance** (Income − Expense). Alag ghatadvani ganatri nathi.
- Je paisa kharekhar haath ma aave ke jay, e badhu ledger ma line tarike lakhay.
- **Ledger tab:** Balance, In, Out, Loan. **Cash in hand card fakt Loans tab ma.**

### 2. In / Out / Loan
- **In** = kharekhar kamai (Salary vagere). **Out** = kharekhar kharcho (Hapta, Other vagere).
- **Loan** loan ni lines nu net chhe (Loan Taken + Loan Return − Loan Given − Loan Repaid).
- **Balance = In − Out ± Loan.** In/Out ma loan ni lines ganai nathi.

### 3. Loans tab
Be vibhag, alag alag:
- **લેવાના (To receive):** je ne tame paisa apya. Koi kyare aapshe e nakki nathi.
- **દેવાના (You owe):** je pase thi tame paisa lidha.

| Tame su karo | Ledger ma aapoaap shu aave |
|---|---|
| Udhar lidha | **Loan Taken** (+, Income) |
| Udhar apya | **Loan Given** (−, Expense) |
| Received / Received all (levana pacha aavya) | **Loan Return** (+, Income) |
| Pay / Settle (devana chukavya) | **Loan Repaid** (−, Expense) |

- Loan ni lines ledger ma **edit na thay**. "Loan Taken" / "Loan Given" ne delete na thay (loan delete karo to e sathe jati rahe).
- "Loan Return" / "Loan Repaid" line delete karo to e payment loan mathi pan hataai jay ane baki rakam pacho vadhe.
- **Loan delete karo to teni badhi ledger lines pan sathe jay.**
- **"Tracked only"** (juna loan, jema aajna paisa nathi aavya): ledger ma kai nathi lakhatu, cash par asar nathi.

### 4. Juna data
App khule tyare juna loans (jemni ledger line nathi) ni lines automatic bani jay chhe. Cash no aankdo badlato nathi. Update karya pehla **Export backup** karvu.

### 5. Test kem karvu
Real flow thi check karvo (headless Chrome / Playwright): Salary → kharcho → udhar lidha → udhar apya → Received → Settle. Darek step pachhi ledger In/Out/Loan ane cash tapasvu.

---

## Aagal na improvements (baki)

Aa badha navi branch ma j karvanu, `main` ma nahi (jethi chalti app ne asar na thay).

**Pehla (jarur):**
1. Ledger ni Balance card ma ek line: *Levana baki · Devana baki*.
2. Kul sthiti ek line ma: *Haath ma + Levana − Devana*.
3. Backup nu reminder (7 divas thi backup na hoy to) ane **Export CSV**.

**Pachhi (saru):**
4. Loan par tap karo to puro itihas (kyare apya, kyare kitla aavya).
5. Mahina pramane In/Out/Loan (Oct, Sep...).
6. Loan edit (naam / rakam bhul sudharva).
7. Delete par confirm / Undo.

**Saaf karva jevu:**
8. Bhasha ek rakhvi (Gujarati / English / Roman bhegu na hoy).
9. Vyakti-wise total (ek j vyakti ne ghani vaar apya hoy to).
10. "Tracked only" checkbox nu naam saral karvu.

**Surksha:** upar na setup ma keystore passwords lakhela chhe. Repo public hoy to e badha joi shake, etle e vaat kadhi nakhvi ke repo private karvu.
