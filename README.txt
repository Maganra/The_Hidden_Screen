The Hidden Screen — PWA bundle
==============================

App files (deploy these SIX):  index.html, manifest.webmanifest,
sw.js, icon-192.png, icon-512.png, icon-512-maskable.png

PRIVATE-campaign-canon.json — your campaign secrets, party roster,
and seal states. NEVER upload this one. Campaign canon no longer
ships inside index.html (players could read it via View Source);
it lives only in your browser's storage.

To deploy (any static host works):
  1. Upload the six app files to the SAME folder on an HTTPS host.
     Free options: GitHub Pages, Netlify Drop (drag the folder in),
     Cloudflare Pages.
  2. Visit the URL once. The service worker caches everything,
     including the fonts — after that it works fully offline.
  3. On YOUR device: Combat Tracker > Import > pick
     PRIVATE-campaign-canon.json. This loads your canon, party,
     and seals into that browser (repeat once per DM device).
     Don't import it on player devices.
  4. On Android/Chrome you'll get an "Install app" prompt (or
     menu > Add to Home Screen). On iOS: Share > Add to Home Screen.

CAMPAIGNS: the masthead has a campaign switcher (dropdown + new /
rename / delete). Each campaign keeps its own tracker, party, canon,
journal, clues, notes, sessions, seals, and encounter library.
Custom (homebrew) creatures are a shared library available to every
campaign. Switching reloads the app into the chosen campaign —
instant once the service worker has cached it. On first run after
this update, your existing data is migrated automatically into a
campaign named "My Campaign" (rename it with ✎).

MOVING A CAMPAIGN BETWEEN DEVICES: Export on the old device
(saves the active campaign; filename includes its name), get the
file to the new device (drive, email, USB), then Import there.
The app detects the campaign in the file and offers to add it as
a NEW campaign automatically — or you can load it into the current
campaign instead (that's the restore-a-backup path). Custom
creatures in the file are merged into the shared homebrew library,
never overwriting creatures other campaigns use.

State persists per browser. The app requests persistent storage,
but use Export regularly for backups.

To ship an update later: edit index.html, then bump the VERSION
string at the top of sw.js (current: v7) so clients refresh
their cache.
