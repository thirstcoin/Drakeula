# Drakeula — AFTER TWELVE website

Static site. Upload this whole folder to any static host (Render static site, Netlify, Vercel, GitHub Pages).

```
index.html            ← the site (all CSS/JS inside)
assets/img/           ← AVIF / WebP / JPEG versions of every image
assets/icons/         ← favicon + Apple touch icon
audio/                ← the 10 web MP3s for AFTER TWELVE (192 kbps). The album plays directly on the site.
```

## Before you deploy
1. **Domain:** already configured for `https://drakeula.com/` in `index.html` for canonical, Open Graph, X/Twitter card, and structured-data URLs.
2. **Analytics:** paste one provider snippet (GA4, Plausible, Umami or GTM) where the `<head>` comment says. These events are already sent:
   `album_play, track_play, track_pause, track_complete, next_track, previous_track, hero_album_click, telegram_click, tiktok_click, x_click, ca_copy, trade_click, chart_click, calendar_add`

## Everything else lives in `CONFIG` (top of the `<script>` near the bottom of index.html)
- `links` — X, TikTok, Telegram. Empty = hidden. No placeholder links ever show.
- `audio.enabled` — `true` (all 10 tracks play). Nothing downloads until someone presses play; the next track prefetches at 70%.
- `calendar` — add a `date: 'YYYY-MM-DD'` to an event only when it's confirmed.
- `latest` — up to 3 content cards (hidden while empty).
- `token` — at launch: set `launched: true`, paste the contract address into `ca` (the ONLY place it lives),
  then fill in only the real values for mint authority / freeze authority / liquidity, the trade link and the DexScreener pair (supply is already set to 1,000,000,000).
  Empty fields stay hidden. The header button, hero button, Solscan/DexScreener links and the chart all switch over automatically.

The Halloween countdown runs to Oct 31, 12:00 AM Toronto time and switches to "The night has arrived." on its own.
