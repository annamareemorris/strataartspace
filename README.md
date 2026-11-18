# Strata Artspace website

The website for **Strata Artspace**, a contemporary art gallery collective at 1 Melmore Tce, Cromwell Heritage Precinct, Cromwell 9310, Central Otago.

Live site: https://www.strataartspace.co.nz

## How it's hosted

- The whole site is a single page: `index.html`. There's no build step.
- It's served by **GitHub Pages** from the `main` branch. The `CNAME` file points it at `www.strataartspace.co.nz`.
- Changes go live about a minute after they're pushed to `main`.

## Folder layout

| Path | What it is |
|------|------------|
| `index.html` | The page: layout, styles, artwork list and artist list |
| `images/` | Full-size artwork images (max 1600px) for the lightbox, artist photos (max 500px), logo and icons |
| `images/thumbs/` | 800px versions of the artwork images, used on the gallery cards |
| `CNAME` | Custom domain for GitHub Pages |

## Adding or editing an artwork

1. Add the full-size image to `images/` and an 800px version with the **same file name** to `images/thumbs/`. Keep full-size images under 1600px on the long side.
2. In `index.html`, add an entry to the `galleryItems` list:

   ```js
   {
     id: 14,
     title: "Artwork title",
     artist: "Artist Name",
     category: "Painters",          // must match a filter button: Jewellery, Painters, Pastel & Paint, Sculptor, Ceramicist, Collage, Photographer
     medium: "Oil on canvas",
     desc: "Short description supplied by the artist.",
     image: "images/artwork-file.jpg"
   }
   ```

## Adding or editing an artist

Add or edit an entry in the `artistsList` list in `index.html`:

```js
{ name: "Artist Name", specialty: "Ceramicist", bio: "First paragraph.\n\nSecond paragraph.", image: "images/artist-name.jpg" }
```

- Separate paragraphs in a bio with `\n\n`.
- Artist photos are shown in a small circle. A square photo around 500px with the face centred works best.
- If the photo file is missing, the card shows a placeholder icon.

## Image rules

- Never rotate images. Some photos rely on their orientation tag to display the right way up, so keep that tag if you resize them.
- Strip location (GPS) data before adding photos.

## Other parts of the page

- **Map:** a Google Maps embed in the Visit section, pinned on the gallery building.
- **Social feeds:** the Facebook Page Plugin and an Instagram profile embed, above the map.
- **Business details for Google:** a structured-data block in the `<head>` with the address, hours, phone and social links. Update it if the hours or contact details change.
- **Search engines:** `robots.txt` and `sitemap.xml` tell search engines what to index. Update the `<lastmod>` date in `sitemap.xml` after big content changes. The artist list in the structured data must be updated when artists join or leave.
- **Link previews:** `images/og-image.jpg` is the picture shown when the site is shared.

## Contact

- Gallery: strataartspace@gmail.com · 027 600 7106
- Facebook: https://www.facebook.com/p/Strata-Artspace-61595813769390/
- Instagram: https://www.instagram.com/strata_art_space/
- Website built and maintained by Anna-Maree Morris.
