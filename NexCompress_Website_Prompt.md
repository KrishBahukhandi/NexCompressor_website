# NexCompress — Complete Website Prompt for Play Store

> **How to use this:** Copy everything inside a `---` section and paste it as your prompt to any AI (ChatGPT, Claude, Gemini, Cursor, v0.dev, etc.) to generate the full website. The prompt is self-contained.

---

## 📋 PROJECT ANALYSIS SUMMARY
*(Read this to understand what was extracted from the codebase — not part of the prompt)*

| Detail | Value |
|---|---|
| App Name | **NexCompress** |
| Package ID | `com.nexcompress.app` |
| Version | `1.1.0` (versionCode 2) |
| Min Android | API 26 (Android 8.0 Oreo) |
| Developer | Krish Bahukhandi |
| License | Proprietary © 2026 |
| Primary Color | `#5B5BD6` (NexIndigo) |
| Secondary Color | `#8B5CF6` (NexViolet) |
| Accent Colors | `#22D3EE` (Cyan), `#22C55E` (Green), `#F59E0B` (Amber), `#EF4444` (Red) |
| Dark Background | `#0F1115` |
| Dark Surface | `#171A21` |
| Dark Surface Variant | `#222732` |
| Light Background | `#F6F7FB` |
| Core Tech | Kotlin 2.0, Jetpack Compose, Material 3, PDFBox-Android, Room, AdMob |
| Network Use | AdMob only (all file processing is 100% on-device / offline) |
| Storage | No runtime storage permissions (Scoped Storage compliant) |
| Play Store Requirement | Needs: Landing page, Privacy Policy page, Support/Contact page |

### All Features (extracted from source)
**On-Device Tools (fully offline):**
1. Compress PDF — 3 quality profiles: Recommended / Balanced / High-Fidelity. Never produces a file larger than the source.
2. Convert Images — JPG/PNG/HEIC/BMP/WebP → JPG/PNG/WebP. Batch up to 5 images. Per-file rename, drag-to-reorder.
3. PDF → Images — Export every PDF page as JPG/PNG/WebP.
4. Images → PDF — Combine photos into a multi-page PDF with reorderable pages.
5. Text → PDF — Convert a `.txt` file into a clean paginated A4 PDF.
6. Sign PDF — Draw finger signature, drag & resize onto any page. Signed page flattened; others stay lossless.
7. Edit PDF Pages — Reorder (drag), rotate, delete pages, then export.
8. Merge PDFs — Concatenate multiple PDFs into one (reorderable).
9. Split PDF — Extract chosen pages or burst every page into its own file.
10. Protect PDF — AES password lock/unlock. Password never leaves device.
11. Image Studio — Rotate, flip, crop (draggable frame), resize; re-encode to JPG/PNG/WebP.

**Online Tools (optional, require API key):**
12. Word ↔ PDF
13. PowerPoint → PDF
14. Excel → PDF
15. PDF → PowerPoint
16. PDF → Excel
*(Demo mode available without API key)*

**App-wide features:**
- Performance Ledger — cumulative storage reclaimed + file history (Room database)
- Rename / Share / Preview / Download any output
- Files saved to `Downloads/NexCompress`
- AdMob banner + interstitial ads

---

## 🚀 THE FULL WEBSITE PROMPT
*(Copy everything from here to the end and paste it as your AI prompt)*

---

Build me a **complete, production-ready, multi-page website** for my Android app called **NexCompress**. This website is required for publishing on the **Google Play Store**. It must include exactly **3 pages**: a **Landing Page**, a **Privacy Policy Page**, and a **Support Page**. All 3 pages must be built in a **single HTML file** using vanilla HTML, CSS, and JavaScript — no frameworks, no build steps, no external dependencies except Google Fonts and a single CDN icon library.

---

### 🎯 PURPOSE & CONTEXT

NexCompress is a **privacy-first, offline file utility and converter** for Android. It compresses PDFs, converts images between formats, edits/signs/merges/splits/protects PDFs, and converts Office documents — almost entirely **on-device**, with **no user account required** and **no user files ever uploaded to any server**. The only network activity is Google AdMob for ads.

Play Store listing requirements I need to satisfy:
1. **Privacy Policy URL** — Must be publicly accessible and describe all data handling
2. **Website/Support URL** — Must have contact info and app support
3. **App landing page** — Professional showcase to link in the Play Store listing

---

### 🎨 DESIGN SYSTEM (MUST FOLLOW EXACTLY)

**Typography:** Use Google Fonts — `Inter` for body/UI, `Plus Jakarta Sans` for headings. Import both.

**Color Palette (match the actual app):**
```
--nex-indigo:        #5B5BD6   /* Primary brand — main CTAs, headings */
--nex-indigo-dark:   #4242A8   /* Hover states, deep accents */
--nex-violet:        #8B5CF6   /* Secondary — image tools */
--nex-cyan:          #22D3EE   /* Tertiary — highlights, badges */
--nex-green:         #22C55E   /* Success, savings, privacy badges */
--nex-amber:         #F59E0B   /* Warnings, online-feature badges */
--nex-red:           #EF4444   /* Error states */

/* Dark theme surfaces */
--bg-dark:           #0F1115
--surface-dark:      #171A21
--surface-variant:   #222732
--text-primary:      #E6E8EE
--text-muted:        #9AA1AF
--border-dark:       #333A47

/* Light theme surfaces */
--bg-light:          #F6F7FB
--surface-light:     #FFFFFF
--surface-variant-light: #ECEEF5
--text-on-light:     #1A1C22
--text-muted-light:  #5C6270
```

**Default theme:** Dark mode. Add a toggle button (moon/sun icon) to switch to light mode.

**Design style:**
- Glassmorphism cards: `background: rgba(23, 26, 33, 0.8); backdrop-filter: blur(20px); border: 1px solid rgba(255,255,255,0.06);`
- Gradient hero background using `#0F1115` with radial gradients of `#5B5BD6` and `#8B5CF6` at 10–15% opacity
- Smooth transitions on all hover states (`transition: all 0.25s ease`)
- Subtle scale transform on hover for cards (`transform: translateY(-4px)`)
- Rounded corners: `border-radius: 20px` for cards, `border-radius: 12px` for smaller elements
- Use `box-shadow: 0 4px 24px rgba(91, 91, 214, 0.15)` for primary cards
- Gradient buttons: `background: linear-gradient(135deg, #5B5BD6, #8B5CF6)`

**Icon library:** Use **Lucide Icons** via CDN: `<script src="https://unpkg.com/lucide@latest"></script>` and call `lucide.createIcons()`. Use inline SVG `<i data-lucide="icon-name">` syntax for all icons.

---

### 📄 PAGE 1: LANDING PAGE

#### Navigation Bar
- Fixed, full-width, glassmorphic: `backdrop-filter: blur(16px)`
- Left: App icon (a ⚡ lightning bolt emoji or SVG) + "**NexCompress**" in bold 20px
- Right: Nav links — "Features", "Privacy", "Support" (anchor links), plus a **"Get it on Google Play"** button (styled with the Play Store badge look — rounded, dark/green, with the Play triangle icon)
- Right also: **Dark/Light mode toggle** button (moon icon)
- On mobile: collapse to hamburger menu with animated slide-down

#### Hero Section
- Full viewport height (`min-height: 100vh`)
- Centered content, two columns on desktop (text left, phone mockup right), stacked on mobile
- **Headline:** "Your Files. Your Device. Your Privacy." — large, bold, gradient text (`background: linear-gradient(135deg, #5B5BD6, #22D3EE); -webkit-background-clip: text`)
- **Subheadline:** "NexCompress is a powerful, offline-first PDF and image utility for Android. Compress, convert, sign, edit, merge, split and protect your files — entirely on your device. No account. No uploads. No cloud."
- **Two CTA buttons:**
  - Primary: "Download on Google Play" — gradient button (`#5B5BD6` → `#8B5CF6`), Play Store icon
  - Secondary: "View Privacy Policy" — ghost/outline button
- **Trust badges row** below CTAs (small pill badges, icon + label):
  - 🔒 "100% On-Device" (green)
  - 📵 "No Account Required" (indigo)
  - ☁️ "No File Uploads" (cyan)
  - 📦 "Android 8.0+" (violet)
  - ⚡ "Kotlin 2.0 + Jetpack Compose" (amber)
- **Right column:** A stylized phone frame (use CSS only — a tall rounded rectangle `border-radius: 40px`, dark border, inner shadow) containing a card-grid mockup of the app's feature tiles. Do NOT use an actual image — build this with HTML/CSS to mimic the app UI:
  - Show 4 feature tiles in a 2×2 grid inside the phone: "Compress PDF" (indigo icon), "Convert Images" (violet icon), "Sign PDF" (green icon), "Edit PDF" (indigo icon)
  - Each tile: small rounded card with a colored icon at top, title, subtitle arrow
  - Below the tiles: a "Performance Ledger" card showing "Total Storage Reclaimed: 142.6 MB" and "Total Files: 87 Files" in green

#### Features Section — "Everything You Need. Nothing You Don't."
Build a **3-tab layout** (or use a horizontal scroll on mobile):
- **Tab 1: PDF Tools**
- **Tab 2: Image Tools**
- **Tab 3: Online Conversions**

On tab click, show the corresponding feature cards with a smooth fade-in.

**PDF Tools cards** (indigo accent `#5B5BD6`):
1. **Compress PDF** — Icon: `file-minus`. "Reduce PDF file size with 3 quality profiles: Recommended, Balanced, or High-Fidelity. Guaranteed never to produce a file larger than the original."
2. **Sign PDF** — Icon: `pen-line`. "Draw your signature with your finger, then drag & resize it onto any page. The signed page is flattened; all other pages remain perfectly lossless."
3. **Edit PDF Pages** — Icon: `layers`. "Drag to reorder, rotate, or delete individual pages from any PDF, then export the result."
4. **Merge PDFs** — Icon: `git-merge`. "Combine multiple PDFs into a single document with drag-to-reorder page previews before merging."
5. **Split PDF** — Icon: `scissors`. "Extract a specific set of pages, or burst every page into its own separate PDF file."
6. **Protect PDF** — Icon: `lock`. "Lock any PDF with AES-standard password encryption, or unlock a protected PDF. Your password never leaves your device."
7. **PDF → Images** — Icon: `image`. "Export every page of any PDF as high-quality JPG, PNG, or WebP images."
8. **Text → PDF** — Icon: `file-text`. "Convert any .txt file into a clean, paginated, print-ready A4 PDF document."
9. **Images → PDF** — Icon: `file-plus`. "Combine multiple photos into a single multi-page PDF with reorderable pages."

**Image Tools cards** (violet accent `#8B5CF6`):
1. **Convert Images** — Icon: `refresh-cw`. "Batch convert up to 5 images (JPG, PNG, HEIC, BMP, WebP) to JPG, PNG, or WebP in one go. Per-file rename and drag-to-reorder."
2. **Image Studio** — Icon: `crop`. "Rotate, flip, crop (with a draggable crop frame), and resize any image. Re-encode to JPG, PNG, or WebP at your chosen quality."

**Online Conversions cards** (amber accent `#F59E0B`):
Show these with an "Online" badge in amber:
1. Word → PDF, PDF → Word, PowerPoint → PDF, Excel → PDF, PDF → PowerPoint, PDF → Excel
Note text below: "Online conversions require an internet connection and an optional API key. Without a key, they run in built-in demo mode."

#### "How It Works" Section — 3-Step Flow
Horizontal stepper on desktop, vertical on mobile. Use large numbered circles with gradient background.

**Step 1 — Pick a Tool:** "Open NexCompress, tap any tool from the home screen tiles or the full-feature side drawer."
**Step 2 — Select Your File(s):** "The system file picker opens. Choose your PDF, images, or text file directly from your device storage."  
**Step 3 — Process & Save:** "Your file is processed 100% on-device in seconds. Save to Downloads/NexCompress, share, rename, or re-download from the history ledger."

#### Privacy Highlight Section — "Privacy Is Not an Afterthought"
Full-width section with dark background and indigo left-border accent.

- **Bold headline:** "Your files never leave your phone."
- Paragraph: "NexCompress processes every PDF compression, image conversion, signature, merge, split, protect, and edit operation entirely on your device using native Android APIs and the open-source PDFBox-Android engine. No file, page, or byte of your documents is ever uploaded to any server. The only network connection the app makes is to Google's AdMob SDK to display ads."
- 3 info cards side-by-side:
  1. **On-Device Engine** (green `#22C55E`) — "PDFBox-Android handles all lossless PDF operations. Native Android BitmapFactory handles all image processing. Zero cloud dependencies."
  2. **No Storage Permissions** (indigo) — "NexCompress uses Android's Scoped Storage (Storage Access Framework). You pick files through the system picker — the app never gets broad access to your storage."
  3. **No Account. No Sign-In.** (cyan) — "There is no user account, no registration, no email, and no login. The app works fully anonymously from the moment you install it."

#### Statistics / Social Proof Section
Show animated counters (count up on scroll into view using Intersection Observer + JS):
- **14+** Tools
- **0** File Uploads
- **0** Permissions Required
- **100%** On-Device Processing

#### Footer
- Left: "⚡ NexCompress" logo + "© 2026 Krish Bahukhandi. All rights reserved."
- Center links: Privacy Policy | Support | GitHub (link to `https://github.com/KrishBahukhandi/NexCompressor`)
- Right: "Requires Android 8.0 (API 26) or higher"
- Very bottom: "Made with ❤️ in India" small text

---

### 📄 PAGE 2: PRIVACY POLICY PAGE (`#privacy`)

This is a **required legal page** for Google Play Store. Style it cleanly — centered max-width container (800px), good line-height (1.7), section headings in indigo.

**Top of page:**
- Heading: "Privacy Policy"
- Subtext: "NexCompress — Offline File Utility & Converter"
- "Last updated: June 2026" (or current month/year)
- "Effective date: June 2026"
- A green banner/callout box: "🔒 Short version: NexCompress does not collect, store, or transmit any of your personal data or files. Everything runs on your device."

**Section 1 — Who We Are**
"NexCompress is developed and published by Krish Bahukhandi ("Developer", "we", "us"). The app package identifier is `com.nexcompress.app`."

**Section 2 — What Data We Collect**
"NexCompress collects **no personal data** from users.

Specifically, we do **not** collect:
- Names, email addresses, phone numbers, or any contact information
- Location data (coarse or precise)
- Identifiers (device ID, advertising ID, IMEI, etc.) beyond what AdMob requires (see Section 5)
- File content, filenames, or metadata from documents you process
- Usage analytics or crash reports (no analytics SDK is integrated)
- Any data that could be linked to a real-world identity"

**Section 3 — How Files Are Processed**
"All file processing — PDF compression, image conversion, PDF signing, page editing, merging, splitting, password protection, and Image Studio operations — is performed **entirely on-device** using:
- Native Android APIs (`android.graphics`, `android.media`)
- PDFBox-Android (open-source, offline PDF engine by Tom Roush, Apache-2.0)
- Kotlin Coroutines on `Dispatchers.IO`

Your files are **never uploaded**, **never transmitted**, and **never stored** on any external server. Output files are written to the `Downloads/NexCompress` directory on your device using Android Scoped Storage. The app holds only temporary URI permissions granted by the Android system via the Storage Access Framework — it does **not** have broad storage access."

**Section 4 — Local Storage (Room Database)**
"NexCompress stores a local compression history ledger in a Room (SQLite) database on your device. This ledger records:
- The name and type of processed files
- The file size before and after processing
- The URI of the output file (local on your device)
- The timestamp of the operation

This data exists solely on your device and is never transmitted anywhere. You can delete any history entry at any time from within the app."

**Section 5 — Advertising (Google AdMob)**
"NexCompress displays ads through the **Google AdMob SDK**. This is the **only** component of the app that makes network connections. AdMob may collect:
- Approximate location (country/region) based on IP address
- Advertising ID (`AD_ID`), used for ad personalization
- Device information (OS version, screen size, etc.)

The `INTERNET`, `ACCESS_NETWORK_STATE`, and `AD_ID` permissions in the app manifest exist solely for AdMob. NexCompress does not independently use these permissions.

For more information, see [Google's Privacy Policy](https://policies.google.com/privacy) and [How Google uses information from partner apps](https://policies.google.com/technologies/partner-sites)."

**Section 6 — Online Conversions (Optional)**
"The app includes optional online Office conversion tools (Word ↔ PDF, PowerPoint → PDF, Excel → PDF, etc.). These tools:
- Require an internet connection and an optional third-party API key
- Are **disabled by default** (run in demo/simulation mode without a key)
- When enabled, upload **only the document you explicitly select** to the configured conversion service for processing

If you use online conversions, refer to the privacy policy of the configured conversion service (e.g., ConvertAPI at convertapi.com)."

**Section 7 — Permissions**
Table format:

| Permission | Reason |
|---|---|
| `INTERNET` | Required by Google AdMob SDK to fetch and display ads |
| `ACCESS_NETWORK_STATE` | Required by Google AdMob SDK to check connectivity before requesting ads |
| `AD_ID` | Required by AdMob on Android 13+ to use the Advertising ID for ad personalization |

"NexCompress does **not** request `READ_EXTERNAL_STORAGE` or `WRITE_EXTERNAL_STORAGE`. File access is handled through Android's Scoped Storage / Storage Access Framework, which grants only temporary, user-selected file access."

**Section 8 — Children's Privacy**
"NexCompress does not knowingly collect any information from children under 13. The app contains advertising; parents should supervise usage in line with applicable laws (COPPA, etc.)."

**Section 9 — Changes to This Policy**
"We may update this Privacy Policy from time to time. When we do, we will update the 'Last updated' date at the top of this page. Continued use of the app after any changes constitutes acceptance of the updated policy."

**Section 10 — Contact**
"If you have any questions about this Privacy Policy, please contact us at: [provide your email — see Support page]"

---

### 📄 PAGE 3: SUPPORT PAGE (`#support`)

**Top heading:** "Support & Contact"
**Subheading:** "We're here to help. NexCompress is built by a solo developer — expect a fast, personal reply."

**FAQ Section** — Accordion/collapsible style (click to expand), with smooth animation:

1. **"Does NexCompress upload my files to the internet?"** → "No. Never. All PDF and image processing runs entirely on your Android device using native APIs and the open-source PDFBox-Android engine. No file content, filename, or metadata is ever transmitted anywhere. The only network the app uses is for Google AdMob ads."

2. **"Why does the app have INTERNET permission if it's offline?"** → "The `INTERNET` permission exists solely for the Google AdMob advertising SDK. Without it, AdMob cannot fetch and display ads. The app itself does not independently use any network connection for file processing."

3. **"Where are my output files saved?"** → "All processed files are automatically saved to the `Downloads/NexCompress` folder on your device. You can also rename, re-download to a custom location, share, or preview any output directly from the History Log on the home screen."

4. **"How do I compress a PDF?"** → "On the home screen, tap the 'Compress PDF' tile (or select it from the side drawer). The system file picker will open — choose your PDF. Then pick your quality profile (Recommended, Balanced, or High-Fidelity) on the next screen and tap Compress. The app guarantees it will never produce a file larger than your original."

5. **"Can I batch-convert multiple images?"** → "Yes! The image converter supports batch conversion of up to 5 images at once. You can drag to reorder them and rename each output file before converting. Supported formats: JPG, PNG, HEIC, BMP, WebP as input; JPG, PNG, WebP as output."

6. **"What does 'Demo mode' mean for online conversions?"** → "Online Office conversions (Word↔PDF, PowerPoint→PDF, etc.) require a third-party API key to perform real conversions. Without a key, the app runs a simulated demo that shows how the flow works but produces a placeholder output. These tools are completely optional — all core PDF and image features work 100% offline."

7. **"How do I sign a PDF?"** → "Select 'Sign PDF' from the home screen or side drawer. Pick your PDF, then draw your signature on the signature pad. Once drawn, you can drag and resize the signature on any page. Tap export when done — the signed page is flattened, and all other pages remain lossless."

8. **"What Android version does NexCompress require?"** → "Android 8.0 (API level 26, 'Oreo') or higher. The app targets Android 15 (API 35) and is compiled with the latest SDK."

9. **"How do I protect/password-lock a PDF?"** → "Select 'Protect PDF' from the side drawer, pick your PDF, enter your desired password, and tap Lock. To unlock a protected PDF, select the same option and enter the existing password. Your password is processed entirely on-device and is never transmitted anywhere."

10. **"I found a bug — how do I report it?"** → "Please open an issue on our GitHub repository: [github.com/KrishBahukhandi/NexCompressor](https://github.com/KrishBahukhandi/NexCompressor/issues). Include your Android version, device model, and steps to reproduce the issue."

**Contact Form Section:**
Below the FAQ, add a simple styled contact form:
- Full Name (text input)
- Email Address (email input)
- Subject (select dropdown): "Bug Report", "Feature Request", "Privacy Question", "General Inquiry"
- Message (textarea, min 5 rows)
- Submit button (gradient, full width on mobile)
- Note below: "This form is for informational purposes. Replace with a real form backend (e.g., Formspree, EmailJS) before going live."

**Direct Contact:**
- GitHub Issues: `https://github.com/KrishBahukhandi/NexCompressor/issues`
- Email: `[Add your email address here]`
- Response time expectation: "Typically within 48 hours"

---

### ⚙️ TECHNICAL REQUIREMENTS

**File structure:** Single `index.html` file. All CSS in a `<style>` block in `<head>`. All JS in a `<script>` block before `</body>`. No external CSS files, no separate JS files.

**Navigation between pages:** Use URL hash routing (`window.location.hash`). Show/hide page sections based on the hash. Default to `#home`. Update the hash when nav links are clicked. Handle browser back/forward button with `hashchange` event.

**Smooth scroll:** Enable `scroll-behavior: smooth` globally.

**Responsive:** Must work on mobile (375px+), tablet (768px+), and desktop (1280px+). Use CSS Grid and Flexbox. No media query breakpoints above 3 — keep it simple.

**Animations:**
- Hero section: fade-in + slight upward slide on load (CSS `@keyframes`)
- Feature cards: stagger in with `animation-delay` (0, 0.1s, 0.2s, etc.) when tab is clicked
- Statistics counters: count up from 0 when scrolled into view using `IntersectionObserver`
- Accordion FAQ: smooth `max-height` transition from 0 to auto using JS
- Dark/light mode: smooth `transition: background 0.3s, color 0.3s` on `:root`

**SEO meta tags** in `<head>`:
```html
<title>NexCompress — Privacy-First Offline PDF & Image Utility for Android</title>
<meta name="description" content="NexCompress is a powerful offline PDF and image utility for Android. Compress PDFs, convert images, sign, edit, merge, split and protect PDFs — all on your device. No uploads. No account. Free.">
<meta name="keywords" content="PDF compressor Android, image converter Android, offline PDF editor, sign PDF Android, NexCompress">
<meta property="og:title" content="NexCompress — Offline PDF & Image Utility">
<meta property="og:description" content="A powerful, privacy-first Android app for PDF and image processing. Everything runs on your device.">
<meta name="theme-color" content="#5B5BD6">
<link rel="canonical" href="https://yourdomain.com">
```

**Accessibility:**
- All interactive elements must have `aria-label` or visible label
- Color contrast must meet WCAG AA
- Focus styles must be visible
- All decorative icons must have `aria-hidden="true"`

**Performance:**
- Google Fonts loaded with `font-display: swap`
- No blocking scripts
- Images: none (use CSS-only illustrations and icon fonts)
- Lucide icons script deferred: `<script defer src="https://unpkg.com/lucide@latest"></script>`

---

### 📝 COPY & TONE GUIDELINES

- **Tone:** Confident, developer-friendly, privacy-conscious. Not marketing fluff.
- **Voice:** "Your files never leave your phone" — direct, simple statements
- **Avoid:** phrases like "revolutionary", "game-changing", "best-in-class"
- **Use:** Precise technical details — "AES encryption", "PDFBox-Android", "Scoped Storage", "API 26+"
- **Target audience:** Privacy-conscious Android users, developers, small business owners who handle documents

---

### ✅ FINAL CHECKLIST (make sure all of these exist)

- [ ] Navigation with working hash-based routing between 3 pages
- [ ] Dark/Light mode toggle that persists on `localStorage`
- [ ] Play Store download button (placeholder link `#`)
- [ ] Mobile hamburger menu
- [ ] Hero with phone mockup built in CSS
- [ ] 3-tab feature grid with all 11 on-device tools + 2 image tools + 6 online conversions
- [ ] How It Works 3-step section
- [ ] Privacy Highlight section with 3 cards
- [ ] Animated counters (14+, 0, 0, 100%)
- [ ] Footer with GitHub link
- [ ] Full Privacy Policy page (all 10 sections)
- [ ] Support page with FAQ accordion (10 items) + contact form
- [ ] All Lucide icons rendering correctly
- [ ] `lucide.createIcons()` called after DOM loads
- [ ] No console errors
- [ ] Fully responsive on mobile, tablet, desktop

---
*End of prompt. Paste everything between the `---` markers into your AI of choice.*
