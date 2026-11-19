# Echoes of the Endless Vale

**A pocket-sized, top-down pixel adventure about finding your way through a world that feels a little like home.**

[Play Echoes online](https://ttfnrob.github.io/Echoes-of-the-Endless-Vale/)

Echoes is an original, handheld-style adventure for the browser. Explore a procedurally growing fantasy world, meet the people who live there, learn songs for your ocarina, and free the old Echoes who keep time moving. You can begin in a different imagined world each time, or let the shape of a real place inspire the Vale.

It is a self-contained web game, not a Game Boy emulator or ROM. The screen, pixel art, music, and controls are made for this game.

## The story

The clocks have stopped. Varrow and the Meridian Company promise a world where nothing ever gets old, and are sealing away the Echoes to make it happen. Wren sets out with a sword, their mother's ocarina, and Pip, a small and very determined moth, to wake the shrines and set time moving again.

Each chapter points you towards another Echo. Find its shrine, discover which song will wake the stone, then explore the rooms beyond: look for a key, face the guardian, and free the Echo. A new song and stronger hearts open the way to the next chapter. The tale moves through acts, with Varrow's plans changing as the Vale grows.

## Make a world

Choose **New world** to start in one of two ways:

- **Classic** builds a fresh, seeded fantasy landscape. Travel outward and new terrain, paths, villages, shrines, signs, caches, and encounters appear as you explore.
- **Your place** starts with a postcode, town, or address. Nearby rivers, roads, woods, water, settlements, and landmarks shape the pixel landscape. Familiar settlement names are kept intact; some natural features and minor names get a light storybook twist. The map borrows the shape of an area, not every street or building, and the world keeps growing beyond it.

One overworld screen covers roughly 1.25 km east-to-west and 1 km north-to-south. That puts nearby neighbourhoods a screen or two away and nearby towns within a journey of several to a dozen screens. The Journal map is a regional overview, showing explored ground alongside named settlements in the surrounding area.

Worlds, places, characters, and encounters are generated from the world seed as you travel. The Journal shows the explored map and points towards the current Echo.

## How to play

On a keyboard:

- **Move:** Arrow keys or **W A S D**
- **A, sword, or interact:** **Z**, **J**, or **Space**. Swing at enemies, speak to nearby people, open chests, and read signs.
- **B, ocarina:** **X** or **K** opens your song list. Use Up/Down to choose a song and an A button to play it. **B** closes the list.
- **Journal and map:** **Enter** or **Escape**
- **Change colour palette:** **Shift** or **P**

On a phone or tablet, use the on-screen direction pad and A/B buttons. The Journal also has controls for sound, colour palette, full screen, and starting a new world.

A few things to try:

1. Follow Pip's pointer and the Journal's directions towards the current shrine.
2. Ask people for clues. Elders know about the Echo; other residents may share rumours or trade.
3. Stand by the shrine's song stone and play the song it needs.
4. Search dungeon rooms for the small key, then find and challenge the guardian.
5. Explore for chests, shards, and heart pieces. Four heart pieces increase your maximum hearts; merchants may trade a piece for shards.

The **Hearth Song** brings you home. The other songs awaken shrines and help the story move forward.

## Your place, maps, and privacy

In the published web game, place lookup uses public services:

1. A UK postcode is located with [postcodes.io](https://postcodes.io/) and its nearby area name is resolved with [OpenStreetMap Nominatim](https://nominatim.openstreetmap.org/). Other place names and addresses are searched with Nominatim.
2. The resolved location is used to request nearby map features from public [Overpass API](https://overpass-api.de/) servers.
3. Nearby named districts and settlements are placed around the starting area and kept recognizable. The local terrain uses map features near the start; settlement names are also requested farther out so nearby towns can appear on the regional map. Some roads, waterways, landmarks, and other minor names are lightly adapted for the storybook setting.

The location text you enter is sent to the relevant lookup service. For postcodes, the resolved coordinates are also used for a Nominatim reverse lookup to find a nearby neighbourhood name; the coordinates are sent to Overpass for the map features. The game has no account or game server: your save, place label, and simplified map sketch stay in this browser's local storage. Saves do not sync between browsers or devices. Starting a new world replaces the current save on that device.

Map data is © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) and available under the [ODbL](https://opendatacommons.org/licenses/odbl/). Place lookup needs an internet connection and public map services may be slow or temporarily unavailable. Classic worlds do not need a map lookup.


## Saves, sound, and offline play

- Progress and preferences are saved automatically in this browser on this device. When you return, choose **Continue** on the title screen. There is no account or cloud save, and the save does not sync to other devices.
- The save uses browser storage, not cookies or a separate save file, so there is no save-consent prompt. Private browsing or clearing the browser's site data may erase it.
- The game is a Progressive Web App. After its first load, the app shell is cached so you can play offline; **Your place** still needs a connection.
- Music and sound effects are synthesised in the browser. Sound and palette can be changed from the Journal.
- Use the full-screen control for a more console-like view. On mobile, you can also add the game to your home screen from the browser's install or share menu.

## Development

The game is plain HTML, CSS, and JavaScript. There is no package manager, build step, or external JavaScript library to install.

Serve the project directory over HTTP while developing. For example, with Python installed:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000/>. Using a local web server lets the service worker and installable-app features work; opening `index.html` directly as a `file://` URL does not.

The main game and rendering code live in `index.html`. `manifest.webmanifest` describes the installable app, `sw.js` caches the app shell for offline use, and the PNG files provide its home-screen icons.

## Credits and licence

The project code is released under the [MIT License](LICENSE). OpenStreetMap data remains under the ODbL and its attribution requirements; the public geocoding and map services have their own usage policies. The game makes small, occasional requests for a place lookup, not continuous map polling.
