# hyd-eats-photos

Venue photo store for [eats.mapmyhyd.com](https://eats.mapmyhyd.com).

Kept out of the Next.js app so Vercel deployments stay small. Shipping these as
Vercel static assets cost ~151MB of Deployment Storage on every deploy, which was
most of how that project blew the 10GB Hobby cap.

Served by GitHub Pages:

```
https://shivtchandra.github.io/hyd-eats-photos/<place-id>.jpg
https://shivtchandra.github.io/hyd-eats-photos/gallery/<file>
```

Pages and not jsDelivr: jsDelivr caps a package at 50MB and this repo is 158MB,
so it answered some files and returned `403 Package size exceeded` for others.
Pages allows 1GB per site, and republishes plus purges its CDN on every push, so
new photos go live in about a minute.

Layout:

- `*.jpg` at the root: one Google Places thumbnail per venue, named by place id.
- `gallery/`: hand-shot photos for venues with an editorial write-up.
- `.nojekyll`: stops Pages from skipping files that begin with an underscore.

This repo must stay public. Pages will not serve a private repo on the free plan,
and that is exactly what broke photos before it existed.

Updated by `scripts/sync-photos.mjs` in the app repo, which also rewrites the
`data/photo-ids.json` manifest the app reads. Do not edit by hand.
