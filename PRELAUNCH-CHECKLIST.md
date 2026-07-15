# Kingsman Security Sdn Bhd — Prelaunch Checklist

This site was built from five client-supplied marketing PDFs, per `CLAUDE-kingsman-build.md`. Everything below must be confirmed with the client/owner before public launch.

## 1. Contact details — unverified, currently withheld or marked pending
- **Phone & fax:** not published. Source material's numbers (`+60 3-1234 5678`-style) look like placeholder patterns, not real numbers. Add real numbers to `contact.html` and the footer of all five pages once confirmed.
- **Email** (`info@kingsmansecurity.com.my`): published as "plausible" per source — confirm it is live and monitored.
- **Address** (No. 12-1, Jalan 1/123A, Taman Desa Melawati, 53100 Kuala Lumpur): published as-is but unconfirmed as the real, current registered/public address. **No map is embedded anywhere on the site** until this is confirmed — add one to `contact.html` once verified.
- Location: `contact.html`, plus footer on every page.

## 2. Service 01 contradiction — Unarmed vs Armed Guard Services
Source material titles a service "Unarmed Guard Services" but its own description states guards carry PDRM-licensed firearms (pistol & pump gun). **Resolution taken for this build:** `services.html#manned-guarding` presents Unarmed and Armed Guard Services as two clearly separate offerings, with a visible `[TO BE CONFIRMED]` notice explaining why, rather than holding the entire page back. The same pending status is echoed in the `contact.html` FAQ. **Before launch:** confirm with the client whether this is (a) two genuinely separate tiers (matches what we published) or (b) a labeling error requiring different copy, and remove the notice once resolved.

## 3. Central Monitoring System (CMS) wording
Source material says "cents alarm system" — almost certainly a typo for "sensor alarm system." Published on `services.html` as "sensor and alarm monitoring" with an inline `[TO BE CONFIRMED]` note flagging the source typo. Confirm exact intended wording with the client.

## 4. Hero image — typographic treatment chosen, not a photo
Neither `hero-guard-radio-skyline.webp` (454×260) nor `hero-executive-protection-team-suv.webp` (625×340) is high-resolution enough for a confident full-bleed hero at modern site widths. **Decision taken:** the homepage and interior-page heroes use a typographic/color treatment (crest + wordmark + tagline on the black/gold palette) instead of a stretched photo. Ask the client if real, current photography exists before considering a photo hero.

## 5. Possible AI-generated / stock imagery
Several source images (skyline guard, protection team, cash-in-transit crew) have the visual character of AI-generated or stock-composite renders rather than photos of Kingsman's actual guards/vehicles. All are still in use as service-card imagery (best available option from source material). **Confirm with the client** whether these are acceptable as final brand imagery or should be replaced with real photography — a prospective client may reasonably expect real guards/vehicles, not renders.

## 6. Domain / canonical URLs
All pages use `https://www.kingsmansecurity.com.my/` as the canonical/OG base URL, matching the source material's stated website. Confirm this is the actual production domain before launch (update all five `<link rel="canonical">` and `og:url`/`og:image` tags if not).

## 7. Contact form backend
`contact.html` contains a static HTML enquiry form with `action="#"` — **it does not currently submit anywhere.** Wire it to a form backend (Formspree, Fillout, a Cloudflare Pages Function, etc.) before launch.

## 8. OG / social image
All pages currently reference `assets/icon-512.png` (the crest logo, upscaled from a 210px source crop) as the social share image. This is a placeholder, not a proper 1200×630 OG image. Commission or design a real social-share image before launch if social sharing is a priority.

## 9. `guard-portrait-closeup-thumb.webp` is not actually a portrait — left unused
On inspection this 160×160 asset is a small hexagon-cropped design fragment (partial text + a cropped patrol-vehicle photo), not a guard headshot as its filename suggests. It was dropped from `about.html` rather than force-fit into a circular portrait frame, which misrepresented it. Ask the client if a real guard/team portrait exists to fill this spot; otherwise leave it out.

## 10. Open FAQ items
On `contact.html`, two FAQ answers are marked `[TO BE CONFIRMED]` pending the intake form:
- "What areas do you serve?"
- "What's your minimum contract term?"

## 11. Run the standard client intake form
No Fillout submission exists for this client yet. The following fields are still open and materially affect the site's messaging — run the standard intake form and update copy accordingly:
- Target customer description (condos? corporate offices? banks/CIT clients? events?) — affects hero and section copy tone
- Preferred CTA channel (WhatsApp vs phone call vs quote-request form)
- Budget floor / minimum engagement, if publishable
- Qualification line (who to politely turn away, if anyone)
- Real, verified contact details (see item 1)
- Any real testimonials with permission (consider anonymized attribution, e.g. "Facilities Manager, Commercial Tower, Klang Valley," since security clients often can't be named)

## QA already completed in this build
- [x] All 5 pages have unique title, meta description, canonical URL, OG tags, and favicon links.
- [x] No client-showcase page; no named clients, named premises, or identifiable guarded sites anywhere on the site.
- [x] Gold-on-white contrast rule followed: gold is never used as body/heading text color on white or light (`section--alt`) backgrounds — only as a decorative border/eyebrow-on-dark accent. Gold text appears only on the black/charcoal background (hero, dark sections, footer, motif strip).
- [x] Armed-guard/firearm language reviewed on `services.html` and `training-standards.html`: stated factually, sourced to the PDRM firearms-licensing fact, no dramatization or invented tactical detail.
- [x] All image paths point into `./assets/` and were spot-checked to resolve.
- [x] Every unverifiable claim (contact details, CMS wording, service areas, contract terms) carries a `[TO BE CONFIRMED]` marker rather than being invented.
