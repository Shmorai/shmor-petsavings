# PetSavings (petsavings.shmor.ai)

A Shmor marketplace (shared rules in `../../CLAUDE.md`): its own brand, design and SEO. Pet supplies, food, insurance and accessories compared for dogs, cats and small pets, with savings guides and help finding trusted local pet services. Repo: `Shmorai/shmor-petsavings` (private until launch). Status: **building**.

## Where things are
| What | Where |
|---|---|
| Card on shmor.ai, search keywords, **referral links**, offers, SEO defaults | `shmor-site.json` |
| Pages (1 JSON file = 1 Google landing page) | `content/` (`home.json` = homepage) |
| Design: header, logo, footer | `templates/layout.html` |
| Design: styles | `assets/site.css` (kit defaults; add this site's theme block at the bottom) |
| Generated output (don't edit by hand) | `index.html`, `*/index.html`, `sitemap.xml`, `robots.txt`, `404.html`, `search/` |

## Pages (17)
Home · pet-food · pet-insurance · dog-supplies · cat-supplies · small-pet-supplies · flea-tick-and-worming · save-on-pet-supplies · local-pet-services (hub, "recommended local suppliers") · dog-grooming · dog-walkers-and-pet-sitters · kennels-and-catteries · blog + 4 posts (fireworks-and-pets, winter-and-holiday-pet-hazards, how-to-read-pet-food-labels, new-puppy-checklist).
Top menu (navOrder): Pet food, Insurance, Dogs, Cats, Small pets, Local services, Save money, Blog. Menu collapses to the burger below 960px.
Home: trust strip + "Shop and compare by pet" photo tiles sit right after the hero (blocks with `"position": "top"`); latest posts and the search band are moved to the bottom with CSS `order`.

## Design
"Park walk": warm cream pages #FFF9F1, deep navy #12263F / #1B3557 hero and bands with rounded bottom corners (36px), sky-blue #38BDF8 buttons with navy text (hover #0EA5E9 + white text, soft #E3F5FD), biscuit-orange #F6B26B paw-print details (eyebrows, list bullets, highlight icons, CTA band watermark), links #0369A1 on light backgrounds. Fredoka 600 headings + Inter body. Logo = navy rounded square with sky-blue toes and a biscuit pad + "Pet**Savings**" (Savings in sky blue). Favicon = the same mark. Every hero is a photo with a navy overlay. Tables go in `<div class="table-wrap">`; tip boxes use `<p class="callout">`. Mobile checked at 375px (no horizontal scroll).
**Photos:** free-licence Unsplash images (not Unsplash+), credited, in each page's "image".

## Content rules for this site
No invented prices, discounts, product ratings, insurer rankings or reviews. Not veterinary advice: health pages point owners to a vet (disclaimer is in the footer). Facts used: AAFCO "complete and balanced" + 95/25/3/flavor naming rules; UK/EU "complete" vs "complementary" feed; permethrin is toxic to cats; UK vets must give a written prescription on request (may charge); England: dogs and cats (over 20 weeks) must be microchipped, puppies by 8 weeks; England licenses kennels, catteries, home boarding and dog day care with 1–5 star ratings (dog grooming and walking aren't licensed); UK dog collar + ID tag law; FCA + Financial Ombudsman (UK), state regulators + NAIC Pet Insurance Model Act (US). Sources: AAFCO, FEDIAF, UK Pet Food, FDA, FCA, FOS, NAIC, RCVS, AAHA, iCatCare, RSPCA, PDSA, Blue Cross, ASPCA, ESCCAP, American Heartworm Society, RWAF, NAPPS, PSI, IBPSA, NDGAA, GOV.UK.
**Local suppliers:** there is no directory of named businesses yet. The local pages explain what to check and invite businesses to apply via shmor.ai/partners/. Only add a named business once the user supplies it (and its link).

## Commands (run here)
```bash
node tools/build.js           # rebuild after ANY change to content/, templates/ or shmor-site.json
node tools/serve.js <port>    # local preview (see the "petsavings" preview config)
```
After changing `shmor-site.json`, also run `node tools/sync-network.js` in `../../shmor-ai`.

## Referral links
None yet. Candidates: online pet stores, pet insurers, pet pharmacies, food subscription brands and pet-sitting platforms with affiliate programmes (Awin/CJ/Impact). Paste exact links from the user only. Every page already has a `partnersTitle`, so adding slugs to `"partners"` is enough.
Add to `shmor-site.json` → `"links"`, list slugs in a page's `"partners"` (or add `"offers"`), rebuild, sync the master, then commit both repos.
