# CLAUDE.md — locus-consulting.com

Website for **Locus Design + Innovation**, a design-led business strategy consultancy based in Chania, Crete and the UK. Founder: Dr. Manos Chatzakis. Greek market is primary.

Read this file fully before any task. If a request conflicts with a rule here, stop and ask.

---

## 1. Working rules (non-negotiable)

- **Never commit to `main`.** Create a named branch per task (`seo-fixes-1`, `restore-articles`, etc.). Do not merge or push until Manos approves.
- **Report before changing** when a task is an audit or investigation. Findings first, edits only after approval.
- **All changes go through this local repo.** Never suggest uploading or replacing files via the GitHub web interface. (Lesson: commit `ef2c902`, 31 Mar 2026, a web "Add files via upload" silently wiped the body of all 6 articles. They stayed blank in production for 7 months.)
- **Show diffs.** After every task: a per-file diff summary, plus a list of any new or changed user-facing text.
- **Greek text needs approval.** Any new or rewritten Greek copy (meta descriptions, alt text, headings, body) must be listed for Manos to review before commit. Never machine-translate without flagging it.
- **Preview before approval.** Open changed pages locally and check at **desktop (1440px) and mobile (390px)**.
- **Don't touch what wasn't asked.** No opportunistic refactors, renames, or "improvements" outside the task scope. Report them as suggestions instead.

## 2. Design skill routing

- **Use the `frontend-design` skill for all UI, layout, styling, or visual work.** It's built in and auto-triggers; do not also load a manual copy of its SKILL.md.
- **One design generator per task.** Do not run `ui-ux-pro-max`, `bencium-impact-designer`, or other design skills alongside it unless explicitly told to. Colliding generators average into generic output.
- `ui-ux-pro-max` is for product/SaaS/conversion sites. It works against Locus's warm, restrained brand, so don't use it here.
- If Impeccable is installed: its slop-detector may be used as a **review pass before shipping**, not as a generator.
- The brief decides the result more than the tool does. When asked for bold refinement, real assets plus explicit permission to break convention is what produces distinctive work. Keep brand colours, content, i18n and mobile-first as hard constraints.

## 3. Stack & services

| Item | Value |
|---|---|
| Domain | locus-consulting.com (Namecheap) |
| Hosting | Vercel, auto-deploys from GitHub `manosdesign4/locus-website` |
| Stack | Static HTML/CSS/JS. No framework, no build step. CSS and JS are inline per page. |
| Analytics | GA4 `G-LGSMXK2FRE` (gtag immediately after `<head>` on every page) |
| Contact form | Formspree `https://formspree.io/f/mjgallky` (AJAX submit, homepages only) |
| Search | Google Search Console verified; `sitemap.xml` + `robots.txt` in root |
| Quiz | `quiz.locus-consulting.com` (GR) and `/en.html` (EN). Separate Vercel project. Always link via the subdomain, never a `*.vercel.app` URL. |
| Map | Google Maps embed, homepages only, `filter: grayscale(0.3)` |

## 4. Site structure (28 pages, EN + GR pairs)

GR files use the `_gr` / `-gr` suffix. Every page has a language pair.

- **Core:** `index` / `index_gr`, `about`, `approach`, `work`, `our-thinking` (+ `_gr`)
- **Services (6):** `service-transform`, `service-newbiz`, `service-cx`, `service-creative`, `service-products`, `service-visibility` (+ `_gr`)
- **Articles (3):** `article-clarity-gap`, `article-front-loading`, `article-org-chart` (+ `-gr`)

**Shared components must stay identical across pages.** The nav (desktop menu, services dropdown, language switcher, hamburger, mobile menu) and the footer are duplicated in every file. When copying a component into a page, copy its **HTML + CSS + JS together**, because articles have their own stylesheet. Reference implementation: `service-transform.html` / `service-transform_gr.html`.

When adding a page: add it to `sitemap.xml` (with hreflang alternates), link it from the nav or relevant index, and create its language pair.

## 5. Brand

### Colour

Primary:
- Sky Blue `#26AADB`: dominant. Logo, headings, links, CTAs, active states.
- Dark Charcoal `#333333`: CTA bands, closing/contact elements, strong type. **Not** for content section backgrounds.
- Light Grey `#EAEAEA`: backgrounds only, never text.

Secondary: **one per composition, never mixed.** Each is tied to a service territory.

| Territory | File | Accent | Light | Dark |
|---|---|---|---|---|
| Business Transformation | `service-transform` | `#CEB189` Warm Sand | `#F5EDE2` | `#A8895E` |
| New Business Models | `service-newbiz` | `#26AADB` | `#E3F4FB` | `#1E92BD` |
| Services & Experiences | `service-cx` | `#58A998` Teal Green | `#E8F4F1` | `#3D8A7A` |
| Creative Environments | `service-creative` | `#F5A55E` Amber Orange | `#FDF2E8` | `#D4843A` |
| New Products | `service-products` | `#4D61A8` Indigo Blue | `#EAEDF5` | `#3A4A82` |
| Strategic Marketing | `service-visibility` | `#ED6B6B` Coral Red | `#FDEAEA` | `#C94F4F` |

Also allowed: Pale Mint `#F0F4F3` (background only), Icon Blue-Grey `#535E6B` (H3s, captions).

**Banned. Never introduce:** `#BF6963`, `#5F6F52`, `#D8C6A7`, `#A4573D`, `#5A7C9F`. Add no colour outside the palette without explicit approval.

### Typography

- **Main site:** DM Serif Display (display/headings) + DM Sans (body, UI).
- **EN articles:** Cormorant Garamond + DM Sans. **GR articles:** Crimson Pro + DM Sans.
- Max two typefaces per page. Body left-aligned (centre only for hero/display). Line height ≥1.5 body, ≥1.2 headings.
- ALL CAPS only for short labels and section identifiers.
- Always test Greek rendering. Greek text uses Greek quotation marks « ».

### Imagery & layout

- **No stock photography.** Use real workshop photos, session artefacts, Chania/Crete landscape (sparingly), and diagrams from real work.
- Illustrations are hand-drawn and line-based, with 1–2 colours max. Slight irregularity is intentional.
- **Walking figure:** always with its long shadow, grounded at the bottom of compositions, in Dark Charcoal or Icon Blue-Grey (never Sky Blue or a secondary colour). Decorative instances use `alt="" aria-hidden="true"`.
- Avoid clichés: lightbulbs, gears, handshakes, neon, emoji-style art.
- Generous white space, one dominant element per section, short paragraphs.
- Logo: lowercase wordmark plus the "design + innovation" descriptor, always together. Never alter, rotate or shadow it. Min 80px wide on screen.

## 6. Voice (when writing or editing copy)

A thinking partner, not a service provider. Calm, precise, grounded, warm. Direct, never hyperbolic, never salesy, never jargon-heavy.

- Lead with the problem/question, not the solution.
- Match clients' real language first ("δεν μεγαλώνουμε", "δεν ξέρω πού να αρχίσω"), then introduce Locus concepts.
- Messaging arc: **Σαφήνεια → Κατεύθυνση → Επιλογή** (Clarity → Direction → Choice).
- Service H1s keep the Locus framing (e.g. "Όταν η επιχείρηση λειτουργεί — αλλά δεν μεγαλώνει."). Searchable category terms go in titles, eyebrows, and body (see §7).

## 7. SEO & AI-search rules (every page)

Goal: visibility in Google and AI search (ChatGPT, Gemini/AI Overviews, Claude, Perplexity) for Greek queries in Chania, e.g. συμβουλευτική επιχειρήσεων, στρατηγικός σχεδιασμός, σύμβουλος στρατηγικής, νέα επιχείρηση, στρατηγική μάρκετινγκ + Χανιά/Κρήτη.

Every page must have:
- [ ] Unique `<title>` and meta description **fully in the page's language** (no mixed EN/GR)
- [ ] Exactly **one `<h1>`**, then a logical H2/H3 hierarchy
- [ ] `rel="canonical"` to itself
- [ ] hreflang trio: `en`, `el`, and `x-default` (→ EN URL of the pair)
- [ ] Open Graph + Twitter tags in the page's language; `og:locale` = `el_GR` (GR) or `en_GB` (EN), with the other as `og:locale:alternate`; `og:url` = this page
- [ ] Image alt text in the page's language; empty alt only for decorative images
- [ ] Working language switcher pointing to the pair (not to itself)
- [ ] JSON-LD structured data (see below)

Content signals:
- Greek service pages should naturally include the category term (συμβουλευτική / στρατηγικός σχεδιασμός) and a location signal (Χανιά, Κρήτη). Write naturally; never keyword-stuff.
- Articles: author byline (Δρ. Μάνος Χατζάκης / Dr. Manos Chatzakis), machine-readable date (`<time datetime>`), H2 subheadings, and links to the relevant service page.
- Service pages should link to related articles.

Entity consistency: "Locus" collides with other companies (Locus Robotics, Locus Research NZ, LOCUS Prishtina). Always use the **full name "Locus Design + Innovation"** together with the location. NAP must be identical everywhere:
- **Name:** Locus Design + Innovation
- **Address:** Μελετίου Πηγά 17, Χανιά, Κρήτη (EN: Meletiou Piga 17, Chania, Crete)
- **Phone/WhatsApp:** +30 6944 800 352
- **Email:** currently `locusforinnovation@gmail.com`. A switch to a domain address is planned; **confirm with Manos before changing.** Email must be plain crawlable text, not entity-obfuscated.

Structured data (JSON-LD, in `<head>`):
- Homepages: `ProfessionalService` (+ `Organization`) with NAP, geo, areaServed, `founder` → `Person`, and `sameAs` (Instagram, Facebook, LinkedIn company + personal, Google Business Profile)
- Service pages: `Service` with `provider` → the organisation
- Articles: `Article` with `author` → `Person`, `datePublished`, `dateModified`
- About: `Person` (Dr. Manos Chatzakis, PhD Northumbria University)
- Use one consistent `@id` per entity across all pages. **Get Manos's approval on entity details before first implementation.**

Sitemap: each `<lastmod>` = the date of that file's last git commit. Update it whenever pages change.

After deploying significant content changes: remind Manos to request reindexing in Search Console (URL Inspection → Request Indexing).

Social links: footers should be consistent site-wide (Instagram, Facebook, LinkedIn).

## 8. Open backlog (from Oct 2026 audit)

Check status before starting related work:
- Article bodies restored from `2635978` on branch `restore-articles`. Nav CSS/JS still being fixed.
- `work_gr.html`: broken hreflang, English OG tags, mixed meta, language switcher pointing to self
- `approach_gr.html`: nav link points to EN page; English OG description; English funnel alt
- `about_gr.html`: mixed-language meta description
- H1 missing on about, approach, our-thinking, work (EN + GR)
- No `x-default` hreflang on any page
- No JSON-LD on any page
- `hero.JPG` has empty alt on both homepages; `index_gr` svc-products alt is in English
- No Google Business Profile link; no quiz link found on the site
- Address/email appear only on homepages
- `article-clarity-gap.html` is missing OG/Twitter tags
- Sitemap lastmod is uniform (2026-03-30)
