# AnimaNoire

Website for AnimaNoire, a tattoo studio in Rimini, Italy: artists, gallery, merch and bookings, with content managed by the studio through Sanity.

**Live:** [anima-noire.vercel.app](https://anima-noire.vercel.app)

## Features

- Artist pages with individual portfolios, generated from the CMS at build time
- Gallery and merch sections with carousels (Embla) and motion effects
- Google reviews and a contact page for bookings
- Sanity Studio, so the studio can edit artists, works and copy without touching code

## Tech stack

| Area      | Tooling                                         |
| --------- | ----------------------------------------------- |
| Framework | Astro 5 with the Vercel adapter, React islands  |
| CMS       | Sanity Studio v3, GROQ, Portable Text           |
| Styling   | Tailwind CSS                                    |
| Motion    | Motion, Embla Carousel                          |

## Repository layout

An npm workspace with two apps:

```text
astro-app/   # The public website (Astro)
studio/      # Sanity Studio used by the studio to manage content
```

## Getting started

Requires Node.js 22 or later.

```bash
npm install
cp astro-app/.env.example astro-app/.env   # Sanity project ID and dataset
cp studio/.env.example studio/.env
npm run dev                                 # runs the website and the Studio together
```

| App     | URL                     |
| ------- | ----------------------- |
| Website | <http://localhost:4321> |
| Studio  | <http://localhost:3333> |

### Environment variables

| App       | Name                                                | Purpose                      |
| --------- | --------------------------------------------------- | ---------------------------- |
| astro-app | `PUBLIC_SANITY_STUDIO_PROJECT_ID`                   | Sanity project ID            |
| astro-app | `PUBLIC_SANITY_STUDIO_DATASET`                      | Sanity dataset               |
| studio    | `SANITY_STUDIO_PROJECT_ID`, `SANITY_STUDIO_DATASET` | Same project, for the Studio |
| studio    | `SANITY_STUDIO_STUDIO_HOST`                         | Hostname for `sanity deploy` |

## Deployment

The website deploys to Vercel with **Root Directory** set to `astro-app`. The Studio is deployed separately with `npm run deploy --workspace=studio`.

## Credits

Started from Sanity's [Astro clean template](https://github.com/sanity-io/sanity-template-astro-clean).

## License

Client project, shared as a portfolio sample. It is not open source: the code, brand and content belong to AnimaNoire and Stefano D'Ambrosio, and no license to reuse them is granted.
