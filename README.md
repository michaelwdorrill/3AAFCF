# Trailer Landing Page

A minimal, all-black GitHub Pages site that plays a trailer video and redirects
to an event page when it finishes.

## How it works

- The screen is black until the viewer taps/clicks anywhere.
- That first interaction is required by browsers before audio can play, so it
  doubles as a "Turn Up Your Volume" prompt.
- On interaction, the video plays unmuted, full-bleed, centered on a black
  background.
- When the video ends, the page automatically redirects to the event URL
  defined in `index.html` (`REDIRECT_URL`).
- Text uses a Skyrim-style display font (Cinzel from Google Fonts by default).

## Adding the video

This repo does not include the actual video file. To add it:

1. Put your video file at `assets/Trailer.mp4` (exact path/name matters — or
   update the `<source src="...">` in `index.html` to match your filename).
2. Commit and push the file.

Keep in mind GitHub has a 100MB per-file limit for normal pushes (use Git LFS
for larger files), and GitHub Pages sites are recommended to stay under ~1GB
total. If the trailer is large, consider compressing it or hosting the video
file elsewhere (e.g. a CDN) and pointing the `<source>` tag at that URL
instead.

## Changing the redirect URL

Edit `REDIRECT_URL` near the bottom of `index.html`:

```js
var REDIRECT_URL = "https://partiful.com/e/cFadVDtIjiAh00iKc36j";
```

Replace it with the real event link when ready.

## Using the real Skyrim font (optional)

By default the page uses **Cinzel**, a free Google Font with a similar
Roman/carved-stone look. If you have rights to use the actual Skyrim UI font
(commonly distributed as `Sovngarde.ttf` from fan font packs), drop it at
`assets/Sovngarde.ttf` and the page will automatically prefer it over Cinzel.

## Enabling GitHub Pages

1. In the repo, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to **GitHub Actions**.
3. Push to `main` — the included workflow (`.github/workflows/pages.yml`)
   will build and deploy automatically.
4. Your site will be available at the URL shown on the Pages settings page.
