# hyd-eats-photos

Venue photo store for [eats.mapmyhyd.com](https://eats.mapmyhyd.com).

Kept out of the Next.js app so Vercel deployments stay small. Served straight from
jsDelivr, which fronts this repo as a CDN:

```
https://cdn.jsdelivr.net/gh/shivtchandra/hyd-eats-photos@main/<place-id>.jpg
https://cdn.jsdelivr.net/gh/shivtchandra/hyd-eats-photos@main/gallery/<file>
```

Layout:

- `*.jpg` at the root: one Google Places thumbnail per venue, named by place id.
- `gallery/`: hand-shot photos for venues with an editorial write-up.

Updated by `scripts/sync-photos.mjs` in the app repo. Do not edit by hand.
