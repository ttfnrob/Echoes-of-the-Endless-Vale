# Echoes of the Endless Vale

An endless top-down pocket adventure that runs in your phone's browser and installs like an app.
Pick **New world → Your place** and type a postcode or town: the game reads the real rivers, roads,
woods, villages and landmarks around it from OpenStreetMap and grows the Vale around them.

## Put it online with GitHub Pages (about 5 minutes)

1. On GitHub, create a new **public** repository, for example `echoes`.
2. On the repository page, choose **Add file → Upload files**, drag in every file from this folder
   (`index.html`, `manifest.webmanifest`, `sw.js`, the three icons and this README), then **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, set **Source** to *Deploy from a branch*,
   pick **main** and **/ (root)**, then **Save**.
4. After a minute or two the game is live at `https://YOUR-USERNAME.github.io/echoes/`.

## Install it on your phone

- **Android (Chrome):** open the link, tap **⋮ → Install app** (or *Add to Home screen*). It opens full screen with its own icon.
- **iPhone (Safari):** open the link, tap **Share → Add to Home Screen**.

Once it has loaded once, the game itself works offline. Building a world from your place needs a connection.

## Good to know

- Saves live in the browser on each device. The copy in the Claude app keeps its own separate save.
- To update the game later, upload the new `index.html` over the old one. Bump `V` in `sw.js` if an old version sticks.
- Map lookups use free public services (postcodes.io, Nominatim and Overpass). They're fine for personal play;
  please don't hammer them. Map data © OpenStreetMap contributors, available under the ODbL.
