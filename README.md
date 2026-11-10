# Air Control Engineers: Website Package

A static, multi-page website for **Air Control Engineers**, Kumbakonam (est. 2010, authorised Daikin dealer).
All content comes from the company profile PDF. Journals and FAQs were written for the site and cite their sources.

## What's inside

| Path | Purpose |
|---|---|
| `index.html` | Home: hero, stats, services, why-us, products, milestones, sectors, process, founder, clients, journal, FAQs |
| `about.html` | Story, founder's letter, mission/promise/values, journey timeline, memberships |
| `services.html` | 6 services in detail, AMC plans (no prices), warning signs, support process |
| `products.html` | 7 Daikin systems with filter tabs + interactive **AC tonnage calculator** |
| `projects.html` | Milestones, searchable/sortable **Top-15 client table**, sectors, service-area map, regions |
| `journal.html` + 6 `journal-*.html` | Articles: tonnage, star ratings/ISEER, VRV vs ductable vs cassette, maintenance tips, AMC types, marriage-hall cooling |
| `faq.html` | 21 FAQs in 5 categories, live search, FAQPage schema |
| `contact.html` | Phones, WhatsApp, email, QR, booking form (opens WhatsApp), Google Map |
| `privacy.html`, `404.html` | Legal note and error page |
| `sitemap.xml`, `robots.txt`, `site.webmanifest`, `favicon.ico` | SEO and app icons |
| `assets/css/styles.css` | Design system (tokens, components, responsive rules) |
| `assets/js/main.js` | Interactions (no libraries): menu, reveal, counters, tabs, table, FAQ search, calculator, WhatsApp forms |
| `assets/img/` | Logo, founder photo, product photos and QR (from the PDF), plus stock photos (Unsplash licence) |
| `_build/` | Python generator that writes every page. **Edit content here, not in the HTML.** |

## Editing content

1. Change text in `_build/content_data.py` (services, products, clients, FAQs), `_build/content_pages.py` (page layouts) or `_build/content_journal.py` (articles).
2. Phone numbers, email and address live in one place: `BIZ` in `_build/build.py`.
3. Rebuild:
   ```bash
   python website/_build/build.py
   ```

## Preview locally

```bash
python -m http.server 8642 --directory website
```
Then open http://localhost:8642

## Deploy

Upload the contents of `website/` (the `_build` folder is optional) to any static host: Netlify, Vercel, GitHub Pages, Cloudflare Pages, or cPanel `public_html`.
The canonical domain is set to `https://www.aircontrolengineerskum.com` in `_build/build.py` (`SITE`). Change it there if the domain differs, then rebuild.

After going live:
- Submit `sitemap.xml` in Google Search Console.
- Create or claim the **Google Business Profile** with the same name, address and phone (NAP) as the site.
- Optional: connect the booking form to Formspree or Netlify Forms if you also want email copies. It currently opens a pre-filled WhatsApp message to +91 97885 05743, which works on any static host.

## Brand system

| Token | Value | Use |
|---|---|---|
| Navy | `#241964` | Primary brand, headings, dark sections |
| Deep navy | `#140e42` / `#0d0930` | Hero, footer |
| Signal red | `#E30613` | Accents, CTAs, the "airflow" line |
| Daikin blue | `#0097E0` | Daikin dealer mentions only |
| Display font | Saira Condensed 500–700 | Headlines (same as the company profile) |
| Text font | Inter 400–600 | Body copy |

Signature motif: the flowing **airflow lines with one red stream**, taken from the company profile cover.

## Before launch: confirm with the client

- Stock photos (sectors, journal covers, hero technician) are representative. Swap in real project photos (Pavalam Mahal, showrooms, the team) as soon as they are available. Keep the same filenames to avoid code changes.
- AMC plan features are described generally, with no prices. Confirm the wording against the actual contract terms.
- No customer testimonials were included because none were in the profile. Add real, permission-granted quotes if available.
- Product feature bullets are general Daikin category features. Confirm current models and capacities.
