# Fitness Evolution — Official Website

Conversion-focused static website for **Fitness Evolution, Pakistan**.

## Verified public business information

- Business: Fitness Evolution
- Category: Gym / Fitness Center
- Country: Pakistan
- WhatsApp: +923006966010
- Independent official website: not provided

No address, email, membership price, opening hours, coach profile, certification, testimonial, transformation claim, or facility claim is published without verification.

## Architecture

This repository intentionally uses semantic HTML5, organized CSS and vanilla JavaScript. It is fast, dependency-free and GitHub Pages friendly.

- `index.html` — semantic section hierarchy and SEO/structured data
- `styles.css` — global design tokens, responsive layout, animation and reduced-motion rules
- `content.js` — central editable business/content configuration
- `app.js` — rendering, navigation, FAQ, lightbox and WhatsApp behavior
- `wordpress-template-map.md` — WordPress/Gutenberg migration mapping
- `robots.txt` / `sitemap.xml` — crawl configuration
- `.github/workflows/pages.yml` — GitHub Pages deployment workflow

All asset references are relative except deliberately remote illustrative images and WhatsApp links, so the site works at the GitHub Pages project base path.

## Content replacement guide

### Business data
Edit `content.js`. Keep readable keys because they can map cleanly to future WordPress custom fields.

### Facilities
The `facilities` array is deliberately empty. **Only add verified facilities.** Suggested object shape:

```js
{ title: "Verified facility name", description: "Verified factual description", verified: true }
```

Until verified facilities are supplied, the public site shows a clear confirmation placeholder.

### Images
Current Unsplash images are visual placeholders and are explicitly labeled as illustrative. Replace each `gallery[].src` URL in `content.js` with optimized authentic business images when available. Replace the hero background URL in `styles.css` too. Recommended: WebP/AVIF, 1600–2000px max hero width, 800–1200px gallery width.

### Address, map, timings, pricing, social links
Do not add these until verified by Fitness Evolution. When verified, add them to `content.js`, then render them in the appropriate section. Update JSON-LD in `index.html` at the same time.

### WhatsApp
The canonical number is centralized as `923006966010` (displayed as +92 300 6966010). Default message:

> Assalam-o-Alaikum, mujhe Fitness Evolution ki membership aur timings ki details chahiye.

## Local preview

No build step is required. Run any static server from the repository root, for example:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

## GitHub Pages deployment

The included workflow deploys the repository root as a static Pages artifact on pushes to `main`. In repository settings, set **Pages → Source → GitHub Actions** if it is not already selected. The expected project URL is:

`https://probuilderoffical.github.io/fitnessevolution/`

Do not treat that URL as live until the Pages deployment succeeds.

## WordPress conversion

See `wordpress-template-map.md`. The current section hierarchy is intentionally Gutenberg-friendly and avoids inline styles/tightly coupled scripts.

Recommended conversion path:
1. Create a lightweight custom theme or child theme.
2. Move CSS variables/base styles into theme stylesheet.
3. Register/enqueue `styles.css` and `app.js`.
4. Map `content.js` keys to ACF/custom fields or core block attributes.
5. Convert each major section into a template part/block pattern.
6. Use WordPress media attachments for authentic images with responsive sizes.
7. Populate verified contact/location/social fields only.
8. Generate SEO/OG/canonical/sitemap via a chosen SEO setup and avoid duplicate metadata.
9. QA WhatsApp URLs, keyboard navigation, responsive layouts and reduced motion after migration.

## QA checklist

- Responsive breakpoints for desktop/tablet/mobile
- Keyboard-accessible navigation, FAQ and lightbox controls
- Visible focus behavior through native controls
- Reduced-motion preference respected
- Lazy-loaded gallery images except the lead image
- No fabricated prices, timings, facilities, testimonials, coaches or transformation stats
- Exact public WhatsApp number used
- Contact form generates a WhatsApp inquiry instead of collecting/storing personal data
- Dynamic footer year
- Relative internal asset paths for GitHub Pages compatibility
- SEO title/description, Open Graph, HealthClub + LocalBusiness JSON-LD
- robots.txt and sitemap.xml included
- No application secrets required

## Final content QA note

Before announcing the website as the business's final official public presence, replace illustrative stock images with authentic photos and verify the address, opening hours, membership information, facilities and social accounts.
