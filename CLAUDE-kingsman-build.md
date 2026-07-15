# CLAUDE.md — Kingsman Security Sdn Bhd Website Build Brief

## What this is
A complete static website for **Kingsman Security Sdn Bhd**, a Malaysian licensed manned-guarding and security-solutions provider. All facts below trace to five client-supplied marketing PDFs (company profile, mission/vision/values, two services sheets). **No Fillout intake form has been completed for this client yet** — target customer, CTA channel, and budget-floor sections are marked accordingly and should be filled once one is run.

## Hard constraints
1. Static HTML/CSS/JS only. No framework, no build step. Deploys via git push to Cloudflare Pages.
2. One shared stylesheet, one small shared script. Semantic HTML, mobile-first.
3. **No client-showcase page. No named client logos, named premises, or identifiable guarded sites anywhere on the site.** This is a deliberate industry-specific decision (see notes to owner below), not sourced from the client materials — confirm with the owner but do not build a "Showcase" page by default.
4. Per page: unique title, meta description, canonical URL, OG tags, favicon (from the lion-crest logo).
5. Tone: factual, professional, restrained. This company describes armed guards and firearms-licensed personnel as a real operational capability (PDRM-licensed) — state this plainly and factually, sourced to the license type mentioned in the source material. **No dramatization, no action-movie language, no invented tactical detail.** This is a business credential, not a marketing hook to sensationalize.
6. Any claim not traceable to the source PDFs gets a `[TO BE CONFIRMED]` marker. Do not invent target-customer language, pricing, or testimonials.

## Brand tokens (extracted from client PDFs via pixel sampling — verified, not guessed)
```css
--gold:  #B38C41;  /* sampled from the logo/design gold-foil gradient across all 5 PDFs */
--black: #141414;  /* dominant dark panel color (near-black, not pure #000, matches the "premium" gold-on-charcoal look already in their materials) */
--paper: #FFFFFF;
```
**Contrast (verified):** gold-on-white = 3.11:1 (fails AA for text; only usable as large-scale/decorative elements on white). Gold-on-black = 6.74:1 (passes AA comfortably). **Rule: gold text only ever appears on the black/charcoal background, never on white.** Body text on white sections = black/charcoal; on dark sections = white, with gold reserved for headings, icons, dividers, and the crest.
**Motif:** the lion-crest-with-crown logo, and the three-word tagline **"VIGILANT • HONOUR • SECURE"** repeated as a signature site-wide element (footer, section dividers) — this already functions as their brand motif across all five source documents, keep it consistent.
**Type:** Display: a bold serif or serif-adjacent face (their wordmark "KINGSMAN" reads as a confident serif/slab in the source material) — recommend Playfair Display or Cormorant for headings to match the "premium/established" feel; Body: a clean sans (Inter or similar) for legibility.

## Verified company facts (cite exactly, do not embellish)
- **Legal name:** Kingsman Security Sdn Bhd
- **SSM Registration No.:** 1539788-A
- **Established:** 2024
- **Founder:** Dato' Narander Singh A/L Chand Singh
- **KDN License No.:** 02250737 (Ministry of Home Affairs — this is the statutory license required to operate a security firm in Malaysia; display exactly as given)
- **Association membership:** Persatuan Industri Kawalan Keselamatan Malaysia (PIKM) — Malaysian Security Industry Association
- **Tagline:** "VIGILANT • HONOUR • SECURE"
- **Mission:** "To provide world-class security solutions that safeguard people, assets, and environments through unwavering vigilance, professional excellence, and innovative security practices. We are committed to delivering reliable, responsive, and customized protection services that exceed our clients' expectations and provide complete peace of mind."
- **Vision:** "To be Malaysia's most trusted and respected security solutions provider, recognised for our operational excellence, integrity, and commitment to protecting what matters most. We aspire to set the industry benchmark by empowering our people, embracing innovation, and building lasting partnerships founded on trust and performance."
- **Core values (primary three, each with its own line):**
  - VIGILANT — "Always Alert. Always Prepared." / "We remain alert so you can have peace of mind."
  - HONOUR — "Integrity in Every Action." / "We serve with integrity and professionalism."
  - SECURE — "Protection You Can Trust." / "Your safety is our responsibility."
- **Secondary values (from the About Us sheet):** Discipline ("we act with precision, follow procedures, and uphold the highest"), Discretion ("we operate with integrity, respect confidentiality, and protect your trust"), Dedication ("committed to your safety, delivering reliable protection 24/7")
- **Training/vetting facts:** all managers, patrolling officers and guards undergo KDN security vetting before employment, and attend the Certified Security Guard (CSG) training programme customised by KDN/PDRM/PIKM, with regular assessment, training and orientation afterward.
- **Workforce note:** guards drawn from local & Nepali personnel (stated directly in source material — present factually and respectfully, no stereotyping language).
- **Contact (flagged, needs verification):**
  - Phone: `[TO BE CONFIRMED — +60 3-1234 5678 as given looks like a placeholder pattern, verify real number]`
  - Fax: `[TO BE CONFIRMED — same concern]`
  - Email: info@kingsmansecurity.com.my *(plausible, but confirm)*
  - Website: www.kingsmansecurity.com.my
  - Address: No. 12-1, Jalan 1/123A, Taman Desa Melawati, 53100 Kuala Lumpur, Malaysia *(confirm this is the real registered/public address, not a template)*

## Available image assets (extracted, optimized WebP, in ./assets/)
All extracted from the client's own PDF marketing sheets — deduplicated (removed 2 repeated CCTV-room shots and 1 repeated access-control shot across sheets) and converted to WebP. **Resolution caveat: these top out at 454–625px wide (source PDFs are flattened print layouts, not a photo library) — fine for card/section images, too low-res to stretch across a full-width hero.** See "Hero image decision" below.

| File | Size | Suggested use |
|---|---|---|
| `logo-lion-crest-source.webp` | 400×360 | Source for header logo lockup |
| `logo-crest-only-square.webp` | 290×260 | Tighter crop — favicon / square social avatar source |
| `hero-guard-radio-skyline.webp` | 454×260 | Candidate hero (see resolution caveat) — guard, radio, KL skyline |
| `hero-executive-protection-team-suv.webp` | 625×340 | Candidate hero (largest native asset) — protection team + branded SUV |
| `bodyguard-close-protection.webp` | 454×200 | Executive Protection / Bodyguard service card |
| `cash-in-transit-armed-escort.webp` | 454×200 | Cash-in-Transit & Cargo Escort service card |
| `access-control-keycard.webp` | 454×200 | Access Control Management service card |
| `cctv-monitoring-room.webp` | 454×190 | CCTV Monitoring & Surveillance service card |
| `guard-dog-service.webp` | 454×200 | Guard Dog Service card |
| `guard-patrolling-condo.webp` | 454×200 | Residential/Commercial Security card |
| `guards-at-building-entrance.webp` | 454×200 | Manned Guarding service card |
| `patrol-vehicle-night.webp` | 454×200 | Patrol Services / Emergency Response card |
| `event-security-red-carpet.webp` | 454×200 | Event & Special Assignment card |
| `guard-portrait-closeup-thumb.webp` | 160×160 | Small supporting image only (About/team section) — smallest asset, do not enlarge |

### Hero image decision — needs owner input, don't default silently
Neither hero candidate is high-resolution enough to be a confident full-bleed hero at modern site widths. Recommended approach: **build the hero as a strong typographic/color treatment** (large "KINGSMAN SECURITY" wordmark + tagline on the black/gold palette, per the existing brand system) rather than a stretched photo, OR use `hero-executive-protection-team-suv.webp` (the largest available, 625×340) at a contained/boxed size rather than full-bleed. Ask the client if real, current photography exists outside these PDFs before finalizing.

### Possible AI-generated/stock imagery — flag to client before launch
Several images (skyline guard, protection team, cash-in-transit crew) have the visual character of AI-generated or stock-composite renders rather than photos of Kingsman's actual guards/vehicles. Confirm with the client whether these are meant as final brand imagery or placeholders — a security company's prospective client may reasonably expect to see real guards and vehicles, not renders.


The source material gives a **6-icon primary strip** (used repeatedly across all 5 documents) plus a **10-item expanded list**. Structure the site as: 6 primary service pillars (matching the repeated icon strip — this is clearly their intended top-level navigation), with the remaining items folded in as sub-services or an "additional capabilities" section.

**Primary 6 (site nav / homepage pillars):**
1. Manned Guarding
2. Executive Protection (source also calls this "Bodyguard" — pick one term, recommend "Executive Protection & Close Protection" to cover both)
3. CCTV Monitoring & Surveillance
4. Access Control Management
5. Patrol Services
6. Special Security Assignments (covers event/crowd security per source: "crowd management, access control, VIP protection, and emergency preparedness")

**Additional capabilities (secondary grid or sub-pages):**
- Cash-in-Transit & Cargo Escort — "armed escorts for secure cash transfers to the bank and cargo escort services... by road from point to point"
- Guard Dog Service — German Shepherd, Rottweiler, Doberman
- Central Monitoring System (CMS) — 24/7 sensor/alarm monitoring for fire, break-in, etc., with immediate owner + authority alerting *(note: source says "cents alarm system," almost certainly a typo for "sensor" — confirm with client before publishing)*
- Emergency Response Team — rapid response/patrol units, incident response, coordination with authorities
- Residential, Commercial & Companies Security — positioning line for condos/homes/businesses, not a distinct operational service

**⚠️ Needs client resolution before publishing:** Service "01" is titled "Unarmed Guard Services" but its description states guards carry PDRM-licensed firearms (pistol & pump gun). Do not publish until the client clarifies whether this is: (a) two separate guard tiers being conflated in their source doc, or (b) a labeling error. Draft copy should describe unarmed and armed guard options as clearly separate offerings once clarified.

## Site structure
1. **index.html** — Hero (lion crest, tagline, dark background per the palette rule), the 6 primary service pillars, mission snippet, KDN license + PIKM membership as trust badges, CTA.
2. **about.html** — Mission, Vision, Core Values (Vigilant/Honour/Secure + Discipline/Discretion/Dedication), founder name, established 2024, SSM + KDN credentials displayed prominently (this is what replaces a client-showcase page for trust-building in this industry).
3. **services.html** — All service pillars + additional capabilities, structured per the reconciliation above.
4. **training-standards.html** (recommended addition, not from source but supported by it) — the CSG training/vetting facts make a strong standalone trust page: KDN vetting, PDRM-licensed armed guards, PIKM-aligned training. This does more credibility work than a client list would, and doesn't reveal any client identity.
5. **contact.html** — Address, phone/email (once verified), enquiry form. No map unless the address above is confirmed real.

## FAQ / depth content (draft once intake form fills the gaps)
Suggested starting questions based on what a security-services buyer typically asks, to be answered once real info exists: "Are your guards licensed and vetted?" (yes — answer from KDN/CSG facts above), "Do you provide armed guards?" (clarify per the unarmed/armed resolution above), "What areas do you serve?" `[TO BE CONFIRMED]`, "What's your minimum contract term?" `[TO BE CONFIRMED]`.

## What's missing — recommend running the intake form before finalizing
No Fillout submission exists for this client. These fields from your standard intake form are still open and materially affect the site:
- Target customer description (condos? corporate offices? banks/CIT clients? events?) — changes hero copy and tone significantly
- Preferred CTA channel (WhatsApp number vs phone call vs quote-request form)
- Budget floor / minimum engagement, if publishable
- Qualification line (who to politely turn away, if anyone)
- Real, verified contact details (see flagged items above)
- Any real testimonials with permission (security clients often can't be named — consider anonymized attribution: "Facilities Manager, Commercial Tower, Klang Valley")

## QA before handover
1. Validate HTML all pages; every asset path resolves.
2. No named client, no identifiable guarded premises, no client logos anywhere.
3. Gold-on-white contrast check: confirm no gold body text on white backgrounds.
4. Armed-guard/firearm language reviewed: factual, sourced to the PDRM-license fact, not dramatized.
5. Contact details section clearly marked pending verification until owner confirms.
6. The Service 01 armed/unarmed contradiction is either resolved or the page is held back from publishing until it is.

## Deliverables
Complete site files + optimized assets + PRELAUNCH-CHECKLIST.md listing every `[TO BE CONFIRMED]` item above, plus a note to run the standard client intake form for the missing strategic fields.
