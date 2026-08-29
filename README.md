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

## 4. Share your lists with your household (optional)

By default your pantry and shopping list live only on your phone. If you
want to share them live with a partner or family member — so both of you see
the same lists update in real time — set up free sync:

### One-time setup (do this once, on either phone)

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
   and sign in with any Google account.
2. Click **Add project**, give it any name (e.g. "our-groceries"), and
   finish the wizard (you can turn off Google Analytics — you don't need it).
3. In your new project, go to **Build → Realtime Database** → **Create
   Database**. Pick any location, and choose **Start in test mode** when
   asked about rules, then **Enable**.
   - Test mode means anyone with your project's config and your chosen
     household code could read or write your lists. That's fine for a
     private household list, but don't post the config publicly. If you
     want it locked down further later, Firebase's docs cover tightening
     the database rules.
4. Back on the project **Overview** page, click the **`</>`** (web) icon to
   register a web app. Give it any nickname and click **Register app** —
   you don't need Firebase Hosting.
5. You'll see a code block that starts with `const firebaseConfig = {`.
   Copy that whole block.

### In the app

1. Open **Grocery Crate**, tap **Sync** (top right).
2. Paste the `firebaseConfig` block into the box, type a household code —
   any short word only your household will use (e.g. `smithkitchen`) — and
   tap **Connect**.
3. Once connected, tap **Copy sync code** and send that (via text, email,
   whatever) to your partner.
4. On their phone: install the app the same way (steps 1–3 above), open
   **Sync**, paste the code you sent, and tap **Connect**. No need to
   re-enter the config or household code — the sync code carries both.

From then on, both phones stay in sync automatically. Either of you can tap
**Disconnect this phone** in the Sync panel to go back to a private,
device-only list at any time.

## About your data

Without sync set up, your pantry and shopping list are saved right on your
phone (in the browser's local storage), not on a server — private to that
device, won't sync anywhere, and clearing your browser's site data for this
app will erase them.

With sync set up, your lists live in your Firebase Realtime Database
instead (Google's free tier — no cost for a household-sized list), and a
local copy is still cached on each phone so the app keeps working offline
and catches up once you're back online.

## Files in this package

- `index.html` — the app itself
- `manifest.json` — tells the phone how to install it (name, icon, colors)
- `service-worker.js` — caches the app so it works offline
- `icons/` — app icons at the sizes phones expect
