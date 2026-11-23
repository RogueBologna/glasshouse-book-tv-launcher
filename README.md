# Book TV — Fantasy Book Launcher

A single-page HTML launcher designed for compatible LG webOS / Glasshouse environments. It features a fantasy-book interface, animated page turns, gold selection highlight, page-turn sounds, clock, and local weather.

## Publish with GitHub Pages

1. Create a new GitHub repository (for example, `book-tv`).
2. Upload **all files in this folder** to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then save.
6. Wait for GitHub Pages to publish the site. Your launcher will be available at the URL GitHub provides.

The entry point is `index.html`. No build step or package manager is required.

## Weather and location

On startup, Book TV first asks the browser/TV for permission to use device location. If permission is denied or browser geolocation is unavailable, it attempts an approximate location based on the network IP address. Weather data is then loaded from Open-Meteo.

- Precise device location requires browser permission and a secure context (GitHub Pages uses HTTPS).
- IP-based location is approximate and may identify the internet provider's location rather than the TV's exact location.
- If both methods fail, the weather panel remains hidden.
- Weather location is not sent to a custom server by this project; the browser requests location-based weather/geocoding data from Open-Meteo and may request IP geolocation from ipapi.co.

## Compatibility notes

The launcher uses browser APIs and remote HTTPS services. Device geolocation and sound playback depend on the TV browser's support and permission settings. Page-turn sound may require a remote-control interaction before the browser allows audio.

## Configuration

The main settings object is near the beginning of the JavaScript in `index.html`. For example, `clock24h` controls the clock format and `fahrenheit` controls the weather temperature unit.
