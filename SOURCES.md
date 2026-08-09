# Open Art Sources

This project currently uses keyless, browser-friendly sources first, so the app can run as a simple static site.

## Integrated

- National Gallery of Art: open access images are free to use, and the public domain data is released as CC0. The app includes curated NGA IIIF samples because the public collection website is Cloudflare-protected and not exposed as a simple browser API.
- Art Institute of Chicago: public API plus IIIF image service. The app filters for public domain works with images.
- Cleveland Museum of Art: Open Access API with CC0 records and image URLs. The app filters `cc0=1` and `has_image=1`.
- The Metropolitan Museum of Art: Collection API requires no key and returns Open Access public-domain image URLs.
- SMK, Statens Museum for Kunst (National Gallery of Denmark): keyless open API with per-work public-domain flags. The app filters `has_image:true` and `public_domain:true` and loads images through SMK's IIIF service, so every SMK work shown is CC0.
- Victoria and Albert Museum: keyless Collections API v2 with IIIF images. The app filters `images_exist=1`. Note: V&A images are free for non-commercial use under the V&A website terms, not CC0, so cards are labelled with a V&A copyright line instead.
- Are.na: public API only, no HTML scraping. The app discovers candidate channels from search terms, filters image-heavy channels, caches the normalized image feed locally for 12 hours, and treats image licenses as unknown unless a source explicitly says otherwise.
- SomaFM: live background radio streams. This is commercial-free, listener-supported radio, suitable for non-commercial prototyping. The app randomizes between Digitalis, SF 10-33, n5MD Radio, and Synphaera Radio, using official 128 kbps MP3 direct streams with alternate SomaFM servers as fallback.
- Independent radio streams: Kaaosradio Chiptune (Helsinki), Retreat Radio (Malmo), Experimental Madrid (radio.co), Ancient FM (mediaeval and renaissance), and New Sounds by WQXR (MP3 with AAC fallback). Only HTTPS streams in Safari-compatible codecs (MP3/AAC) qualify: the site is served over HTTPS so mixed-content HTTP audio is blocked, and Ogg streams do not play on iOS. If a station fails mid-listen, the app automatically hops to another station instead of going silent.

## Good Next Sources

- Rijksmuseum: open/FAIR data with IIIF images and OAI-PMH access, but the current no-key path needs an adapter that parses OAI/IIIF records.
- Smithsonian Open Access: large CC0 collection, but the live API requires an api.data.gov key.
- Europeana: very broad European cultural heritage aggregator, but API access requires a free key.
- Harvard Art Museums: rich collection API, but requires an API key.

## Primary References

- https://www.nga.gov/artworks/free-images-and-open-access
- https://api.artic.edu/docs
- https://openaccess-api.clevelandart.org/
- https://metmuseum.github.io/
- https://api.smk.dk/api/v1/docs
- https://developers.vam.ac.uk/guide/v2/welcome.html
- https://data.rijksmuseum.nl/about/
- https://www.si.edu/openaccess/devtools
- https://www.europeana.eu/en/apis
- https://harvardartmuseums.org/collections/api
- https://api.are.na/v2/search/channels
- https://api.are.na/v2/channels/visual-research
- https://somafm.com/digitalis/directstreamlinks.html
- https://somafm.com/sf1033/directstreamlinks.html
- https://somafm.com/n5md/directstreamlinks.html
- https://somafm.com/synphaera/directstreamlinks.html
- https://kaaosradio.fi/
- https://www.retreatradio.net/
- https://www.ancientfm.com/
- https://www.wqxr.org/streams/
