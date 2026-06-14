# ChristianSisti.Com

Personal website and blog for Christian Sisti — Engineering Director.

## Owner profile

- **Name**: Christian Sisti
- **Role**: Engineering Director (previously at Ocado Technology — E-commerce Platform: Reliability, Performance, Developer Experience)
- **Background**: 15+ years in tech, specializing in scaling global engineering orgs and modernizing high-traffic platforms
- **Education**: Master's in CS with focus on Human-Computer Interaction, University of Pisa
- **Community**: Founding organizer of LeadDev Barcelona — curates spaces for engineering leaders
- **Tagline**: "High-Energy, Customer-Centered, Flow-Driven Engineering Director"
- **Tone of voice**: Direct, confident, leadership-oriented — with a light touch of humor (table soccer ;)

Use this profile to inform content decisions (blog post framing, bio updates, SEO copy).

## Goals

- **Full SEO control**: meta tags, Open Graph, canonical URLs, sitemap — all hand-rolled, no plugin magic
- **Blog**: write articles in Markdown, git-versioned, no CMS needed
- **Flexibility**: own the code completely, no Google Sites / page-builder constraints
- **Performance**: static output, near-zero JS

## Tech stack

- **Framework**: Astro (static output)
- **Styling**: Tailwind CSS v4 (config lives in `src/styles/global.css` via `@theme`, no `tailwind.config.js`)
- **Fonts**: Inter via Google Fonts (loaded in `src/layouts/Layout.astro`)
- **Sitemap**: `@astrojs/sitemap` — auto-generated, requires `site` set in `astro.config.mjs`
- **Package manager**: npm

## Design system

- **Tone**: Minimal & clean
- **Palette**: Navy (`--color-navy-*`) on warm white (`--color-warm-*`) — custom tokens defined in `src/styles/global.css`
- **Key colors**: `navy-950` headings · `navy-700` body · `navy-500` accents · `warm-50` background
- **Max content width**: `max-w-3xl` centered with `px-6` padding

## Project structure

```
src/
  components/
    SEO.astro          # Reusable SEO head (meta, OG, Twitter card)
  content/
    blog/              # Blog posts as .md files (Content Collections)
  content.config.ts    # Blog collection schema (title, description, pubDate, tags, draft)
  layouts/
    Layout.astro       # Base layout: nav, main slot, footer
  pages/
    index.astro        # Homepage
    about.astro        # About page
  styles/
    global.css         # Tailwind import + @theme tokens + base html styles
```

## Common commands

```bash
npm run dev      # Start dev server at http://localhost:4321
npm run build    # Build to dist/
npm run preview  # Preview the build locally
```

## Deployment

- **Target**: Cloudflare Pages (not yet configured)
- **Repo**: https://github.com/christiansisti/ChristianSisti.Com
- Plan: connect Cloudflare Pages to GitHub for auto-deploy on push to `main`

## Content

- Blog posts go in `src/content/blog/` as `.md` files
- Required frontmatter: `title`, `description`, `pubDate`
- Optional: `tags`, `draft` (drafts are excluded from listings), `updatedDate`
- Blog listing page not yet built — to be added when first post is ready

## Site URL

`https://christiansisti.com` — set in `astro.config.mjs` (required for sitemap and canonical URLs)
