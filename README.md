# Weatherpins landing page

Static RU/EN presentation site for Weatherpins. The site is independent of the Django application and contains no build step or runtime dependency. Russian is served from `/`; English is served from `/en/`.

## Files

- `index.html` — Russian landing page.
- `en/index.html` — English landing page.
- `assets/css/styles.css` — shared responsive styles.
- `assets/images/` — local brand assets and the illustrative map.

## Local preview

Open `index.html` or `en/index.html` directly in a browser using `file://`. All resources and language links use relative paths and work without a server, including in a subdirectory. No Django server or build tool is required.

## Publishing

The intended hosting is Netlify Free with this repository as the static site source and the repository root as the publish directory. Configure the custom domain and DNS separately after approval. This repository contains no deployment credentials or production configuration.

## Brand assets

The logo, favicon, and blue map pin are copied unchanged from `photos/static/photos/brand/` in the local Weatherpins Django repository (`sganzha81/weatherpins`); the same assets are present in `staticfiles/photos/brand/`. The brand kit manifest documents `#1E88E5` as its theme color. The website is self-contained and has no runtime dependency on the Django repository.

## Map and image credits

- `assets/images/map-illustration.svg`: land outlines from [Natural Earth 1:110m Land](https://www.naturalearthdata.com/downloads/110m-physical-vectors/), version 5.1.2, obtained as [GeoJSON](https://github.com/nvkelso/natural-earth-vector/blob/v5.1.2/geojson/ne_110m_land.geojson). Natural Earth data is [public domain](https://www.naturalearthdata.com/about/terms-of-use/); attribution is not required. Credit: Natural Earth. The source SHA256 is embedded in the SVG. The outlines were projected to SVG coordinates with `x = 20 + (longitude + 180) * 920 / 360`, `y = 300 + (85 - latitude) * 920 / 360`, rounded to 0.1 SVG units. This is a static equirectangular map; no map tiles, OpenStreetMap data, APIs, or runtime mapping libraries are used.
- `assets/images/demo-yosemite.jpg`: [Yosemite Valley, View from Glacier Point, Yosemite National Park](https://commons.wikimedia.org/wiki/File:Yosemite_Valley,_View_from_Glacier_Point,_Yosemite_National_Park.jpg), by Mckunec, [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Local 330px Wikimedia thumbnail, displayed with a crop.
- `assets/images/demo-milford.jpg`: [Milford Sound on a stormy day](https://commons.wikimedia.org/wiki/File:Milford_Sound_on_a_stormy_day._-_Flickr_-_upsidedown_astronomer.jpg), by Paul Stewart (upsidedown astronomer), [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Local 330px Wikimedia thumbnail, displayed with a crop.
- `assets/images/demo-samara.jpg`: view of the Samara brewery, supplied locally by the project owner as `IMG_6954.JPG` and authorized for this landing page. Cropped and resized to 600 × 360 pixels, re-encoded as an optimized JPEG without source metadata. The original file is unchanged; no open license is asserted for this photograph.
- `assets/images/feature-*.svg`: original line icons for this site. No external icon library is used.

The map shows five real geographic locations: Yosemite (37.728, -119.572), Milford Sound (-44.671, 167.926), Lisbon (38.722, -9.139), Buenos Aires (-34.604, -58.382), and Samara (53.2, 50.1). The Yosemite and Milford Sound photos are licensed demonstration material, not user uploads. The Samara photograph was supplied by the project owner for this illustration. The Yosemite and Milford Sound dates and weather are fictional examples. The Samara capture time (6 June 2026, 13:26), drizzle condition, and 20.2 °C temperature were provided by the project owner; they are not fetched from Weatherpins.

Three expanded cards illustrate **separate interface states** on desktop. The actual application uses one popup at a time. On mobile (up to 600px), all five points use the same closed blue pin appearance on a compact map, followed immediately by three cards in the order Yosemite, Samara, Milford Sound. The cards reuse the same HTML and images, with photos beside the date, place, and weather. Mobile has no connector lines. The map's original desktop padding is cropped with CSS without changing geographic coordinates or adding a second image. Desktop keeps two cards above the map and the Samara card below its own marker, slightly right of center. There is no map interaction.

## Interface reference

The static card styling follows the local Django source: `photos/templates/photos/photo_list.html`, `photos/templates/photos/public_map.html`, and `photos/static/photos/css/main.css`. The templates contain the map selection and popup JavaScript. The illustration preserves the official blue pin with a bottom-center geographic anchor, white rounded card, date above the photo, location below it, and a pale weather row with condition and temperature. The real photo-opening behavior was also inspected in `photos/static/photos/js/image_lightbox.js`. No application logic, drag controls, or photo actions are copied into the landing page.
