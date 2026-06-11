The Hidden Screen — PWA bundle
==============================

Files: index.html, manifest.webmanifest, sw.js, icon-192.png,
icon-512.png, icon-512-maskable.png

To deploy (any static host works):
  1. Upload all six files to the SAME folder on an HTTPS host.
     Free options: GitHub Pages, Netlify Drop (drag the folder in),
     Cloudflare Pages.
  2. Visit the URL once. The service worker caches everything,
     including the fonts — after that it works fully offline.
  3. On Android/Chrome you'll get an "Install app" prompt (or
     menu > Add to Home Screen). On iOS: Share > Add to Home Screen.

Combat tracker state persists across launches via localStorage.

To ship an update later: edit index.html, then bump the VERSION
string at the top of sw.js (e.g. v1 -> v2) so clients refresh
their cache.
