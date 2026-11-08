# Lisbon — Interactive Map

190 Lisbon destinations on one map: search, area filters, three day routes,
photo lightbox, "near me" GPS sort, and a Google My Maps KML for the same data.

Mobile-first: full-screen map with a draggable bottom sheet (peek / half / full),
48px touch targets, 16px input text so iOS doesn't zoom on focus, safe-area
insets, and card taps that pan the map and open the place popup. Visual language
borrowed from Airbnb's system via VoltAgent/awesome-design-md — white canvas,
#222 ink, one accent (#ff385c), hairline dividers, a single shadow tier.

**Live:** https://hamzafelix.github.io/Lisbon-Map-3Days/

## What's inside

- `index.html` — the whole app, single file, no build step, no API keys.
- `lisbon-destinations.kml` — import into Google My Maps (7 folders, one per zone,
  190 placemarks with photo, opening hours, website and directions link).

## The data

- 190 places, picked from pt.wikipedia articles about Lisbon with coordinates
  pulled from Wikidata — article depth used as a rough notability filter.
- 182 have photos (543 images), all from Wikimedia Commons, hotlinked from
  `thumb.wikimedia.org`; flags, crests, logos, location maps and images reused
  across four or more unrelated places are filtered out.
- 84 have an official website; 32 have real OSM opening hours (via Nominatim
  `extratags`).
- Coordinates are Wikipedia/Wikidata points, not shopfront-accurate survey marks.
  Places with a coarse coordinate are flagged `approx` in the popup.

No ratings: Google Places, Foursquare and Yelp all need an API key, and inventing
stars is not on the menu.

## Not included

Halal restaurants and the supermarket layer that the Porto map has. Every public
Overpass mirror was either blocked from this host or serving an empty Lisbon
extract, so those layers are empty rather than guessed.

## Zones and routes

Alfama & Castelo · Baixa & Chiado · Bairro Alto & Estrela · Belém & Ajuda ·
Alcântara & Riverside · Avenidas & North · Parque das Nações.

Day 1 Baixa, Chiado & Alfama — Day 2 Belém & the River — Day 3 Bairro Alto & Beyond.
Routes are greedy nearest-neighbour walks through each day's zones, not optimised
tours.

## Running it

Open `index.html`. From `file://` it uses Esri's public tiles, because OpenStreetMap
blocks tile requests that arrive without a Referer header; once hosted over http(s)
the OSM layer appears in the layer switcher automatically.

Personal, non-commercial use. Basemap © Esri, HERE, Garmin, OpenStreetMap
contributors. Place data from OpenStreetMap (ODbL), Wikipedia (CC BY-SA) and
Wikidata (CC0). Photo credits: see `ATTRIBUTION.md`.
