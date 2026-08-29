# Grocery Crate

A pantry + shopping list app: keep a master list of everything you usually
buy, build a trip's shopping list from it, check items off as you shop, and
drag to reorder to match your store's layout. Works offline once installed.

## 1. Put it on GitHub

1. Go to [github.com/new](https://github.com/new) and create a new repository
   (public), e.g. `grocery-crate`.
2. Upload every file in this folder to the repository, **keeping the folder
   structure** (the `icons/` folder needs to stay a folder). The easiest way:
   on the repo page, click **Add file → Upload files**, then drag this whole
   folder's contents in.
3. Commit the files to the `main` branch.

## 2. Turn on GitHub Pages

1. In your repository, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Set **Branch** to `main` and folder to `/ (root)`, then **Save**.
4. Wait a minute or two. GitHub will show you a URL like:
   `https://yourusername.github.io/grocery-crate/`

## 3. Install it on your phone

Open that URL on your phone in a browser, then:

- **iPhone (Safari):** tap the Share icon → **Add to Home Screen**.
- **Android (Chrome):** tap the **⋮** menu → **Install app** (Chrome may also
  offer this automatically as a banner).

It'll launch full-screen from your home screen icon, just like a regular app,
and keeps working without a connection after the first load.

## About your data

Your pantry and shopping list are saved right on your phone (in the browser's
local storage), not on a server. That means:

- It's private to that device and that browser.
- It won't sync between your phone and, say, a laptop.
- Clearing your browser's site data/cache for this app will erase your lists.

## Files in this package

- `index.html` — the app itself
- `manifest.json` — tells the phone how to install it (name, icon, colors)
- `service-worker.js` — caches the app so it works offline
- `icons/` — app icons at the sizes phones expect
