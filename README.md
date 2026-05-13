# Rapidpatch Pothole Index

Live public tracker of Auckland potholes flagged & repaired by Rapidpatch.

**Live URL:** https://sp210-collab.github.io/rapidpatch-pothole-index/  
**Embedded on:** https://www.rapidpatch.co.nz/index (planned)

## Stack
- Plain HTML/CSS/JS — no build step
- [Leaflet](https://leafletjs.com/) 1.9.4 for the map
- [Leaflet.heat](https://github.com/Leaflet/Leaflet.heat) for the heatmap
- [OpenStreetMap](https://www.openstreetmap.org/) tiles (no API key needed)
- Demo data hardcoded in `index.html` — to be replaced with Wix CMS `FlagDeployments` feed

## Adding a flag
Edit the `FLAGS` array in `index.html`. Each entry:
```js
{ tag: 24, suburb: "Mt Eden", lat: -36.8772, lng: 174.7625, flagged: "2026-05-14", repaired: null }
```
Set `repaired: null` while pending; set the date string once repaired.

## Wiring to Wix CMS (future)
Replace the hardcoded `FLAGS` constant with a `fetch()` call to a Wix Velo HTTP function (e.g. `https://www.rapidpatch.co.nz/_functions/flag_data`) that returns the `FlagDeployments` collection as JSON.
