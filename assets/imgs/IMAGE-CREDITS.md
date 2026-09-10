# Image credits

Every photo on the site is royalty-free stock, used under the **Unsplash Licence**
(https://unsplash.com/license) or the **Pexels Licence** (https://www.pexels.com/license/).
Both allow free commercial use with no attribution required; credits are recorded here anyway
so the source of each file can be traced.

None of these are photos of Norwich Builders' own work. Replace them as the client supplies
real project photography.

| Site file | Source file | Source |
|---|---|---|
| services/kitchens-2.webp | smart-renovations-07b4cw2eOzM-unsplash.jpg | Unsplash |
| services/kitchens-3.webp | immo-renovation-VtO6A-I3piU-unsplash.jpg | Unsplash |
| services/bathrooms-2.webp | pexels-peter-vang-2157328093-35493890.jpg | Pexels |
| services/bathrooms-3.webp | pexels-artbovich-6890406.jpg | Pexels |
| services/extensions-1.webp | james-feaver-glO8JbrAj5k-unsplash.jpg | Unsplash |
| services/extensions-2.webp | brett-jordan-PFr50OBMowU-unsplash.jpg | Unsplash |
| services/renovations-1.webp | smart-renovations-07b4cw2eOzM-unsplash.jpg | Unsplash |
| services/extensions-3.webp | elise-brown-IVDp_OeDlYk-unsplash.jpg | Unsplash |
| services/renovations-2.webp | elise-brown--TBeL9BIWF0-unsplash.jpg | Unsplash |
| services/renovations-3.webp | gennifer-miller-Mb_r0CIDFh8-unsplash.jpg | Unsplash |
| general/about-1.webp | brett-jordan-Zs9vage-0AM-unsplash.jpg | Unsplash |
| general/about-2.webp | pexels-brettjordan-28885519.jpg | Pexels |
| gallery/kitchens-metro.webp | franco-debartolo-hhDYh0_YQIA-unsplash.jpg | Unsplash |
| gallery/renovations-exterior.webp | zachary-keimig-Wzub0VR4OHU-unsplash.jpg | Unsplash |

All were centre-cropped to the layout's aspect ratio, saturation +1.1 to match the sitewide
pass, and saved as WebP at quality 82.

`services/renovations-1.webp` history: the francesca-knall strip-out (rubble, foreign-looking) was swapped 2026-09-11 for a client photo of a restored hallway, then swapped again 2026-09-11 at the client's request for stock only - now an island-weighted crop of the "smart renovations" kitchen-diner (Unsplash). The contact-page CTA that used it has been removed.

`services/conversions-1.webp` (the studwork/garage-opening photo) was removed from the
conversions **service page** the same day, again at the client's request. It remains only as
the small card thumbnail on the homepage, services index and gallery.


## Conversions

All four original conversion photos were removed on 2026-09-10: three showed loft
conversions, which are no longer a service the site offers, and one contained two
identifiable people.

| File | Source | Licence |
|---|---|---|
| services/conversions-1.webp | brett-jordan-yica25Tg73w-unsplash.jpg | Unsplash |

The replacement shows a garage opening being framed out in studwork and boarded over,
which matches the revised copy ("wall structure", no loft). Checked at full resolution
first: no people, no number plates, no house number. It does carry a small ADT alarm box
on the wall - a security brand, not a competing builder.

`general/photo-to-follow.webp` is a brand placeholder generated in-house, kept in the repo
for any future slot awaiting client photography.

## 2026-09-11 round 2

- Homepage and the "Everything We Build" grid on pages/services.html now show finished
  work only. Extensions cards point at `extensions-3.webp` (finished rear extension);
  conversions cards use `general/photo-to-follow.webp` because no finished-conversion
  stock photo exists in the pool (all three finished loft interiors were deleted when
  loft conversions were dropped, and the rest of the pool is kitchens, bathrooms,
  exteriors or construction sites). Client conversion photos are pending.
- The studwork/scaffolding shot `conversions-1.webp` (source brett-jordan-yica25Tg73w)
  now appears only on the conversions service page and the gallery - not in any
  homepage or services-index card.
- All absolute asset URLs (og:image, twitter:image, JSON-LD image + logo) were
  repointed from https://www.norwichbuilders.co.uk/assets/ to
  https://maks-website-new.vercel.app/assets/ so social/link previews resolve against
  the live deployment. Canonical and og:url still point at norwichbuilders.co.uk and
  must stay that way; revert the asset URLs too once that domain serves this build.
