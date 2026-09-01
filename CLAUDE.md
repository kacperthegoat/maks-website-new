# Norwich Builders — project memory

## What this project is

A website rebuild for **Norwich Builders**, a building firm in Norwich, Norfolk.

This codebase is a duplicate of a **live client site: Standfast Fencing** (owner Nick Holywell-Walker, Brundall). Standfast was itself a rebrand of an earlier site, JB Outdoor Services. Two previous clients' traces exist in this codebase. Assume anything unverified belongs to one of them.

This is a **content rebuild on the existing layout**, not a rename. The old site had nine fencing service pages; this one has five building services. The service tree, gallery filters, homepage structure and most body copy have to be rebuilt, not edited.

---

## Client details — the only source of truth

| Field | Value |
|---|---|
| Business name | Norwich Builders |
| Owner | Maksymilian Chlebiej (goes by Maks) |
| Email | norwichbuilders@hotmail.com |
| Phone (display) | 07817 938507 |
| Phone (href) | `tel:+447817938507` |
| WhatsApp | `https://wa.me/447817938507` |
| Address | 14 Penrice Road, Norwich — **postcode TODO** |
| Opening hours | Mon–Fri, 8am–5pm |
| Service area | Norwich and surrounding areas, Norfolk |
| Domain | https://www.norwichbuilders.co.uk/ |
| Facebook | https://www.facebook.com/p/Norwich-Builders-100068577885824/ — confirmed |

### Business description — client's own wording, do not rewrite

> Norwich Builders is a trusted local business covering Norwich & surrounding areas. Norwich Builders is dedicated to providing quality building services. We specialise in all types of building works, from small jobs to large jobs. We are proud of what we do for our clients when we build and enhance their homes.

### Services — five, in this order

Kitchens · Bathrooms · Extensions · Renovations · Conversions

### Brand

- Primary `#2c3172` (navy) — dominant colour
- Accent `#e5a824` (gold) — **sparingly**: buttons, links, small highlights only. Never large fills or section backgrounds.
- Modern sans-serif, one family throughout
- Tone: warm, plain-spoken, not corporate

---

## Hard rules

**Never invent a value.** If a fact isn't in this file, leave a visible TODO and tell me. This applies especially to:

- Contact details, addresses, postcodes, geo coordinates
- Certifications, licences, memberships (CSCS, TrustMark, FMB, waste carrier licence, Gas Safe, NICEIC). None are confirmed. Trust badge slots stay empty.
- Years in business, number of employees, jobs completed, founding date
- Reviews, ratings, testimonials
- `aggregateRating`, `review`, `priceRange`, `foundingDate`, `numberOfEmployees` in schema — omit all of these

**Never source anything from another builder's website.** blc-builders.co.uk is a reference for *layout simplicity only*. Its contact details, copy and images are off limits.

**Never reuse the old client's private infrastructure.** The Google Apps Script webhook in `pages/process_form.html` is Nick's live lead endpoint feeding his Sheet. Delete it; do not repoint it.

**No motion.** The client's most specific complaint. No carousels, marquees, scroll-reveal, parallax, animated counters, autoplay video. Delete unused motion components rather than leaving them in the codebase.

**No stock photography of the wrong kind.** The client *has* asked us to supply stock images chosen to suit each service — that is in scope. Use royalty-free UK residential building work, warm and natural, no obviously American housing. List source and licence per image. Ten Unsplash photos are in `~/Downloads` as candidates.

---

## Old-client purge — final sweep must return zero

Case-insensitive search across all files including dotfiles, JSON and XML:

```
standfast · fencing · decking · Nick · Holywell · Walker · Brundall
NR13 · standfastfence · standfastfence@gmail.com
07976222991 · 07976 222991 · 447976222991
52.6203 · 1.4364 · jb outdoor · dgooch
```

Then confirm no page renders a broken image or missing favicon.

---

## Phase plan and status

**Phase 1 — header + footer** — complete
Contact details across five responsive copies; mega-menu collapsed three groups/nine links → flat five; Google Reviews deep link and Facebook URLs removed; trust badges removed (slots left empty deliberately); copyright updated; Ontek Systems credit kept.

**Phase 2 — head metadata** — complete
116 domain references updated; all 17 canonicals corrected including a pre-existing broken-path bug; "Norwich" in every title and description; `og:site_name` and `og:locale` added where missing. Sweep went wider than head and replaced the brand name in body copy too — this was approved.

**Phase 3 — JSON-LD** — complete
One `LocalBusiness` / `additionalType: GeneralContractor` on index.html (duplicate `GeneralContractor` block deleted); about/contact/gallery/services now reference it by `@id` only. Geo, `priceRange`, `sameAs`, founder `Person` and street address all removed. Hours Mon–Fri 08:00–17:00. FAQ microdata on contact.html cleared of Brundall/Nick/old phone; three answers left as visible TODOs. The nine fencing pages still carry their old Service/FAQ blocks — they are deleted wholesale in Phase 4, so cleaning them first would be wasted work. Delete: the duplicate block on index.html, the founder `Person` block, all Service and FAQPage blocks on the nine fencing pages. Opening hours Mon–Fri 08:00–17:00, **not** 24/7. Delete the geo block entirely — do not guess coordinates. Omit `sameAs` until Facebook is confirmed. Clear FAQ microdata naming Brundall, Nick or the old phone; keep question structure, mark fencing-specific answers TODO.

**Phase 3A — global styling sweep** — complete
Colour: `#40543C`→`#2c3172`, `#C98756`→`#e5a824`, `#21321D`→`#1f2352` across all Tailwind arbitrary values, inline styles and `style.css`. Tokens renamed to `--color-brand-navy` / `--brand-navy`, `--color-brand-gold` / `--brand-gold`, `--brand-navy-hover`; dead legacy aliases (`--midnight`, `--ocean*`, `--bronze*`, `--color-brand-green`) deleted. Large copper fills went to navy-deep `#1f2352`, not gold — see the report for the list.
Motion: header marquee → static wrapping bar; scroll-reveal removed from every page, `global.js` and `style.css`; hero slideshow → single static image; trust slideshow, homepage scrolling banner, animated counters, services carousel, about infinite-scroll strip, thank-you entry animations, FAQ slide-down and all `hover:scale`/`hover:-translate` all deleted. Zero `@keyframes` and zero `animation:` declarations remain anywhere.
Verified: all seven surviving pages render with content visible, no horizontal overflow.

**Phase 4 — service pages** — complete
Nine fencing pages deleted (with their Service/BreadcrumbList blocks). Five built on the same template: kitchens, bathrooms, extensions, renovations, conversions — each with a Service + BreadcrumbList block referencing the business by `@id`. Services index rebuilt to five cards; gallery filters and category sections rebuilt to five. Header nav already pointed at the five new slugs, so no dead links. Copy carries no superlatives, certifications, prices, timescales or material claims — credibility gaps left as TODOs listed in the Phase 4 report. `sitemap.xml`, `robots.txt` and `site.webmanifest` were still entirely on `standfastfence.com`; all three rewritten.
Contrast: white-on-gold pills (43) and the button labels changed to navy. Regression fixed along the way — Phase 3A deleted `--bronze`/`--bronze-dark` while `style.css` still used them, which had left every `.btn-bubble` unstyled.
Old-client purge across surviving pages: Nick's name, `07976 222991`, `standfastfence@gmail.com`, the Standfast Google-reviews deep link and the five-star block all gone. Body copy on index.html and about.html is still fencing-era — homepage rebuild and the About decision are separate.

**Phase 4A — homepage + About claims** — complete
Homepage cut from eight sections to three: hero (with section 2's intro folded in), services, bottom CTA. Deleted: about/trust container, before/after slider, process, "why" claim cards, FAQ (incl. its FAQPage microdata). New H1 "Builders in Norwich and Norfolk"; intro paragraph replaced and marked TODO-CONFIRM pending the client's choice of singular vs plural. Four fencing tiles replaced with five building services linking to the new pages. Footer Quick Links column deleted, footer grid 3→2 columns. All "sustainably sourced" and "licensed waste carrier" instances gone from index and about. About: "Owner-Led Projects" cards, "100% Sustainably Sourced" badge and the owner-operated paragraph deleted; commitment cards deduped 18→3 (the 3× repeat was left over from the deleted marquee). Contact: the insurance/credentials FAQ deleted outright.
Path audit: only ONE file path was corrupted by the Phase 2 brand sweep (`StandfastImages` → `Norwich BuildersImages`); no others. All four broken image paths now point at TODO placeholders on navy.
Nav: the two "FAQs" links pointed at the deleted homepage `#faq` and were repointed to `/pages/contact.html#faq`.

**Phase 5 — reviews**
Delete `pages/reviews.html` entirely and every link to it in nav and footer. The six named Google reviews are real people writing about a different business — delete, never reword. Delete the "Five-Star Rated on Google" claim at `index.html:213`. No placeholder testimonials.

**Phase 6 — forms**
Remove Nick's Apps Script webhook. Build a new enquiry form delivering to norwichbuilders@hotmail.com, and tell me exactly what I need to set up my end. Contact page needs: email, mobile, enquiry form, WhatsApp button.

**Phase 7 — assets**
Generate favicon set, app icons and OG image from the logo. Source stock for five services plus hero. Delete all 18 remaining fencing photos. Update `site.webmanifest`, `sitemap.xml`, `robots.txt`, the `style.css` header comment, `README.md`. **Delete `STANDFAST_REBUILD.md`** — it contains the old client's phone and email.

---

## Outstanding — blocking

1. **Postcode** — needed for the address and any geo data.
2. **Publish address or not** — 14 Penrice Road may be Maks's home. Ask before displaying it.
3. **About page** — the onboarding form requires it, but Maks asked to remove the "Our Story" button. Keep the page, or fold into the homepage?
4. **"Free quotes"** — kept in the header bar pending client confirmation.
5. **Trust badges / credentials** — ask Maks whether he holds any.

---

## Client's approved change list

From Maks's email, already agreed:

- Logo renders as `NorwichBuilders`, mixed case, single roof mark — done; logo placed at `assets/imgs/logo.png` (1672×941, transparent), no `text-transform: uppercase` anywhere near it
- Homepage collapses from six sections to two: hero + one body block (move section 2's text into section 1, delete 2–6)
- Remove: fully insured, 5-star Google rating, 100% owner-led, "Our Story" button, footer quick links, the moving blue services line
- Bathrooms copy: cut "tanked before tiled" and "tiled dead level"
- Add conversions to the homepage
- Services page intro — "Kitchens, bathrooms, extensions, renovations and conversions carried out across Norfolk."
- Homepage intro paragraph — **await my wording**; the client's own draft was grammatically broken and I am confirming the fix with him

---

## Working style

Stop after each phase for review. Report what changed, what you deliberately did not change, and what you need from me. Flagging a gap is always better than filling it.
