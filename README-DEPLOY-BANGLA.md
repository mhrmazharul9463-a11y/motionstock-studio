# MotionStock Studio — Deploy Guide (Bangla)

## Eta ki?

**MotionStock Studio** — HTML animation theke MP4 video bananor tool, microstock-er jonno.
Ekta file-i sob: `index.html` (CSS + JS vitorei ache, alada build lagbe na)।
Chrome (desktop) e sobcheye valo chole।

**Brand:** MotionStock Studio
**WhatsApp / bKash:** 01741192705 (bKash number-o ei tai dhora hoyeche — bodlate chaile Site Settings-e bodlan)
**Theme:** Deep teal + gold (ager orange/lal theme theke alada)
**Plans:** ৳199 / 30 din, ৳499 / 90 din, ৳999 / 180 din, ৳1499 / 365 din
**Free:** Unlimited export — sob size (720p / 1080p / 1440p / 4K), login charao, kono limit nei

## File gulo

| File | Kaj |
|---|---|
| `index.html` | **Publish korar file** — etai GitHub Pages-e upload korben |
| `_source/index.html` | Clean source (backup, private) — **eta publish korben na, kauke diben na** |
| `README-DEPLOY-BANGLA.md` | Ei guide |

## Step 1 — GitHub Pages-e deploy (free, 10 minute)

1. github.com-e login kore **New repository** banan. Nam din jemon: `motionstock-studio`। Public rakhun।
2. **Add file > Upload files**-e giye sudhu `index.html` upload korun (README ba `_source` upload korben na)।
3. **Commit changes** chapuni।
4. Repo-r **Settings > Pages**-e jan।
5. **Branch:** `main`, folder: `/ (root)` select kore **Save** korun।
6. 1-2 minute por upore ekta link dekhabe, jemon:
   `https://apnar-username.github.io/motionstock-studio/`
   Etai apnar site-er address।

> Site-er nam / link pore bodlate chaile repo-r nam bodle dilei link bodle jabe।

## Step 2 — Prothom login + Admin

1. Site khule **লগইন / সাইন আপ** chapuni, nijer email + password diye **সাইন আপ** korun।
2. **Prothom account-tai Admin hoy** (demo mode-e)।
3. Admin hole upore **অ্যাডমিন** menu dekhabe। Admin-er kokhono Pro kinte hobe na — Admin manei Pro, unlimited।
4. **Free Unlimited mode:** Export-e kono Pro / login / limit nei — je keu, login na koreo, jekono size-e jotobar khushi export korte parbe।

## Step 3 — Brand / WhatsApp / bKash / Plan bodlano (Site Settings)

Admin panel-e giye **সাইট সেটিংস**-e bodlan, tarpor **সেটিংস সেভ করুন** chapuni:

- সাইটের নাম (ব্র্যান্ড), WhatsApp নম্বর, বিকাশ নম্বর
- 1080p ফ্রি লিমিট (default 20)
- উপরের চলমান লেখা (ticker), ঘোষণা / নোটিশ
- "প্রমট বানানোর নিয়ম" লেখা, AI প্রম্পট টেমপ্লেট

Plan-er dam / din ekhon code-er `DEFAULTS.plans`-e ache — bodlate chaile Admin panel-e ekhono plan editor nei, tai `index.html`-er `plans:` ongsho bodle abar upload korte hobe, ba amake bolle ami kore dibo।

## Pro / bKash kivabe cholbe?

1. Buyer site-e account khule Pro plan beche **Send Money** korbe apnar bKash number-e (01741192705)।
2. Buyer form-e tar bKash number + **TrxID** diye Submit korbe — status **Pending** hobe।
3. Apni Admin panel-e giye TrxID miliye **Approve** chapben — buyer-er account sathe sathe Pro hoye jabe (plan-er din onujayi)।
4. Vul hole **Reject** chapben।

## Firebase bosano (optional, kintu asol site-er jonno dorkar)

Demo mode-e shob kichu sudhu **oi browser-er localStorage-e** thake — mane onno browser / onno user-er account, payment apni dekhte paben na। Asol site chalate Firebase bosan:

1. console.firebase.google.com-e giye **Add project** korun (free plan-ei hobe)।
2. **Build > Authentication > Sign-in method**-e **Email/Password** ON korun।
3. **Build > Firestore Database**-e database banan (test mode diye shuru korte paren, pore rules tight korun)।
4. **Project settings > Your apps > Web app (</>)**-e giye config copy korun।
5. `index.html`-er upore `CONFIG.FIREBASE`-e `apiKey`, `authDomain`, `projectId`, `appId` bosan (jagay `PASTE_YOUR_...` lekha ache)।
6. `CONFIG.ADMIN_EMAILS`-e apnar admin email bosan, jemon `["you@example.com"]`।
7. Abar GitHub-e upload korun।

> ⚠️ Firebase config-e `apiKey` thakleo seta secret na — Firebase web key public-i thake। Asol surakkha Firestore Rules + Admin email diye hoy। Kono password / secret kokhono code-e likhben na।

## Video export kivabe kaj kore?

- HTML paste korle seta iframe-e chalano hoy, virtual clock diye animation-er somoy thik rakha hoy।
- Tarpor frame by frame chobi tule browser-er WebCodecs VideoEncoder diye H.264 video banano hoy, ar mp4-muxer diye MP4 file hoy।
- Export-er somoy Chrome tab khula rakhte hoy, screen on rakhte hoy।
- Prothom export-er somoy mp4-muxer library internet theke load hoy — tai internet lagbe।
- Firefox / Safari-te VideoEncoder na thakle export hobe na — tai Chrome use korte bolun।

## Code protection — sotyi kotha

`index.html` (publish file) minify + obfuscate kora — variable-er nam, string gulo ultapalta kore deoa hoyeche, jate keu khulei bujhte na pare। Clean source sudhu `_source/index.html`-e ache, seta kauke diben na।

Kintu ekta sotyi kotha mone rakhben: **kono static website-i 100% copy-proof hoy na।** Browser-e ja dekhay, seta kono na kono vabe neya jay। Ja kora jay:

- ✅ Code obfuscate kora hoyeche — shohoje pora jay na
- ✅ Settings / user / payment code-e nei — Firebase bosale segulo server-e thake, HTML copy korleo keu apnar user ba payment pabe na
- ✅ Brand, number, plan apnar nijer — copy korleo tader site-e apnar info thakbe na (jodi tara bodle ney)
- ❌ Right-click block kora hoyni — ota asol user-der birokto kore, ar copy thamay na

## Somossa hole

| Somossa | Somadhan |
|---|---|
| "এই ব্রাউজারে ভিডিও এনকোডার নেই" | Chrome desktop use korun, Chrome update korun |
| "The target must be provided and an instance of Target" | Purono version-er bug chilo — notun `index.html` (fix kora) upload korun, ager-ta soriye din |
| "File-ta double-click kore khulle export hobe na" / `[object Event]` | **File double-click kore khulben na** — Chrome file:// page-ke iframe-er vitore dhukte dey na। GitHub Pages-e upload kore https link theke khulun, tarpor Export chapun |
| Export majhkhane theme jay | Tab khula rakhun, onno tab-e jaben na, screen off korben na |
| mp4-muxer load hoyni | Internet check korun, ad-blocker thakle site-ta allow korun |
| Login korar poro Admin dekhay na | Prothom account-tai Admin — onno browser-e notun account khulle seta admin hobe na |
| Site khulle "ডেমো মোড" dekhay | Firebase bosano hoyni — demo mode cholche, eta normal |
| Plan-er dam bodlate chai | Admin panel-e plan editor nei — `index.html`-er `plans:` bodle abar upload korun |
