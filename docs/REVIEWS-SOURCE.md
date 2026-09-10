# Customer reviews — source text

The full, untrimmed Google reviews behind the excerpts on `pages/testimonials.html`.
Kept so any quotation on the site can be checked against what the customer actually wrote.

Rules applied when excerpting:

- No word is changed, reordered or added.
- `…` marks every place text has been cut.
- Two typographic normalisations only, no wording touched:
  1. Anika's inner quotation `"nothing is impossible"` is set with single quotes on the page,
     because the excerpt itself is wrapped in double quotes.
  2. Peter wrote `cost saving ideas.Max is a fantastic person`; a space is added after the full
     stop so the sentence break renders.
- No star graphics on the page: only Anika's review states a star count (via the owner's reply),
  so showing five stars against Chris's or Peter's would be inventing a rating they did not give.
- No `aggregateRating` or `review` structured data anywhere: Google's guidelines disallow markup
  for reviews collected on a third-party platform.

---

## Anika Elfara — Local Guide, 22 reviews, 10 photos — 3 years ago

> We are so happy to have found Norwich Builders (Max) for our home improvement projects!
> Max converted our pantry into a great looking toilet, installed a lovely new family bathroom(with
> new ceiling spotlights instead of our old tired lamp) added a cold water tap to the outside of the
> house(finally our home car wash and plant watering in front of the house has become easy), removed
> the last remaining lead pipe from our home, built boxes, added recesses to crumbling /difficult
> walls ...all in all for Max "nothing is impossible". So many other builders had told us on the past
> how this and that was absolutely not possible, so Max's can-do attitude was truly music to our ears
> as it surely will be to any future clients of his!
> On top of all of this Max is a pleasure to have around,  keeps good communication about the ongoing
> job and always clarifies any uncertain details, he is punctual, extremely tidy and managed to keep a
> what I had been told by other builders in the past would be an "incredibly dusty job" almost
> dust-free.
> So if you need a builder, choose Max!
> We will certainly do so should our house need more work in the future:)
>
> Positive: Responsiveness, Quality, Professionalism, Value

Owner reply: "I'm so glad to hear that you are happy with my service. It was pleasure to put new look
to parts of your house. Thank you so much for 5 star review."

## Chris Yallop — 3 reviews — 2 years ago

> Norwich builders did a garage conversion for me. They covered everything from building regs through
> to decorating.
>
> The end result was lovely and during the process Max often looked for ways to improve the final
> appearance, off of his own back.
>
> Price wise, the quote was slightly cheaper than other quotes I'd had. I have little to no experience
> in anything building related and was worried about ending up with a cowboy builder, but my reason for
> picking Norwich Builders was because I got a good gut impression after talking to Max.
>
> Max was super friendly and kept me up to date at every stage. His work was also as tidy as could be
> expected.

Owner reply: "Many thanks. Hope kids like new playroom."

## Peter Durrant — 1 review — 3 years ago

> Norwich builders are a first class company and we're prepared to go the extra mile with advice and
> cost saving ideas.Max is a fantastic person who really cares about his work.
> I would not hesitate to recommend this company.
>
> Positive: Responsiveness, Quality, Professionalism, Value

---

## Outstanding

**"Read the full review on Google" links are not on the page yet.** They need one canonical Google
Business Profile URL. The codebase currently holds two unmatched identifiers, neither verified:

- `maps.google.com/?cid=14340383533896799532` — the QR image and the "Write a Review" buttons on
  index, about, services and testimonials
- `place_id:ChIJGVQlQKNjjKsRLJXHcNhGA8c` — `sameAs` in the JSON-LD on index

When the correct URL is confirmed it must be updated in **all** of those places, and the QR image
regenerated, because the URL is encoded into the QR pattern itself.
