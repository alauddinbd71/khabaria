# Khabaria SAUDi

Premium bilingual (English / Arabic) home-style food landing page for Riyadh, built with React, Vite, Tailwind CSS, and TypeScript.

## What is included

- English / Arabic toggle with RTL support and smooth transitions
- Responsive premium landing page with menu filters
- Floating WhatsApp contact widget with bilingual lead form
- WhatsApp prefilled message handoff
- UTM, `gclid`, `fbclid`, and `ttclid` attribution capture
- `dataLayer` and `generate_lead` events for GA4, Google Ads, and Meta Pixel bridges
- SEO metadata, Open Graph/Twitter previews, and FoodEstablishment JSON-LD
- GitHub Pages deployment workflow

## Run locally

```bash
corepack enable
pnpm install
cp .env.example .env.local
pnpm dev
```

Open the local URL shown by Vite.

## Environment variables

| Variable | Purpose |
| --- | --- |
| `VITE_WA_NUMBER` | WhatsApp number in international format, without `+` or spaces |
| `VITE_BASE_PATH` | GitHub Pages base path, e.g. `/khabaria-saudi/` when deploying to a project repository |
| `VITE_GA4_MEASUREMENT_ID` | Reserved for your GA4 measurement setup |
| `VITE_META_PIXEL_ID` | Reserved for your Meta Pixel setup |
| `VITE_GOOGLE_ADS_ID` | Reserved for your Google Ads conversion setup |

**Important:** Replace the placeholder WhatsApp number before launch. Do not commit secrets.

## Build

```bash
pnpm check
pnpm build
pnpm preview
```

The production output is generated in `dist/public`.

## GitHub Pages

1. Create a GitHub repository and upload this project.
2. If using a project repository, set `VITE_BASE_PATH` to `/<repository-name>/` in the GitHub Actions workflow.
3. In GitHub, open **Settings → Pages** and select **GitHub Actions** as the source.
4. Push to `main`; `.github/workflows/deploy.yml` builds and deploys the site.
5. Set the real WhatsApp number in the workflow or repository environment variables.

For a custom domain, point DNS to GitHub Pages and update the canonical URL in `client/index.html`.

## Suggested campaign UTM format

```text
?utm_source=facebook&utm_medium=paid_social&utm_campaign=riyadh_home_platters&utm_content=video_a
?utm_source=google&utm_medium=paid_search&utm_campaign=riyadh_home_platters&utm_content=family_platter
?utm_source=youtube&utm_medium=video&utm_campaign=riyadh_home_platters&utm_content=creator_review
```

## Notes

- The site-side events are ready, but ad-platform IDs must be configured before you expect Meta, GA4, or Google Ads dashboards to receive platform-side events.
- The contact form does not store personal data on a server; it opens WhatsApp with a prefilled message.
