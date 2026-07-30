---
title: "Vibe Coding My Wife's Website: What Happens When the Client is Someone You Love"
description: "I rebuilt ariannalanzillotti.com using AI in 6 days. The technical parts were hard. The human parts were harder. Here's the honest account."
pubDate: 2026-07-30
tags: ["ai", "vibe-coding", "engineering", "leadership"]
draft: false
---

Recently I rebuilt my own personal site using Claude Code. It went well enough that I wrote about it. Then I asked myself: "Would it work for a non-technical project, with a real client?"

The answer presented itself naturally. My wife, **Arianna Lanzillotti**, is an Italian singer-songwriter based in Barcelona. She had a website: a Google Sites page I'd built for her years earlier. It worked, roughly. But it was monolingual, inflexible, and had a contact form that dumped submissions into a Google Sheet nobody was checking.

She needed something better. I had a framework, a workflow, and a spare week.

Here's what actually happened.

## The Brief

The requirements were clear from the start:

Two audiences. Fans arriving from Instagram and TikTok bio-links, looking for music and updates. And, equally important, record labels and talent scouts who might evaluate her seriously. The site needed to work as a press kit: Sanremo mentions, press coverage, a proper biography with verified facts.

One non-negotiable: trilingual. Italian, Spanish, English. From the first line of code, not as an afterthought.

## What Made This Different From Building My Own Site

When I built my own site, I was client and developer simultaneously. Every decision was mine to make and mine to live with. Fast, frictionless, occasionally reckless.

Building for someone else, even someone you know intimately, changes the dynamic completely. The standard is higher because it's not about your taste, it's about theirs.

## The Technical Stack

- Astro for the static output
- Tailwind v4 with custom design tokens
- Astro's native i18n for the three languages
- Content Collections for the news/press section (with Markdown and optimised images), 
- Web3Forms for the contact form, Kit (formerly ConvertKit) for the newsletter, both integrated via direct `fetch()` calls with no backend. 
- Deployed on Cloudflare Pages via GitHub, domain on Squarespace DNS.

## The Moment That Humbled Me

The biography page.

I gave Claude the raw text from the old site and asked it to reformat it into a clean, structured biography. It did. It looked perfect.

Then I read it carefully.

It had silently cut an entire paragraph. Not flagged, not summarised, just gone. The tenor Josep Viader. A podium at the World Dance Championships. The names of musicals she'd performed in. **All absent**.

I caught it. But only because I read the original source against the output, line by line. If I'd approved it on first glance, which, honestly, I almost did, those facts would have been missing today.

This is the thing about AI-assisted content work that nobody says clearly enough: **the model summarises by omission, not by error**. It doesn't lie. It just quietly leaves things out. And the things it leaves out are often the specific, textured details that make a person real.

## The Cloudflare Mistake I Made Myself

When it came to deployment, I created a Cloudflare Worker instead of a Cloudflare Pages project.

I caught it myself, in real time, mid-sentence while Claude was still diagnosing: *"I think I created a service, not a page"*. Ten minutes lost.

This is the honest version of "AI-assisted development": the AI doesn't prevent you from clicking the wrong button in a dashboard. Human error remains entirely available to you.

## What Six Days Produced

A trilingual website (Italian, Spanish, English), live at [ariannalanzillotti.com](https://ariannalanzillotti.com), with:

- A home page with hero, featured release with Spotify embed, and social links
- A full discography with titles verified via Spotify and YouTube oEmbed APIs before display
- A biography with timeline, verified facts, and press mentions
- A news/press section powered by Content Collections (Markdown + optimised images)
- A contact page with two separate forms — one for general contact via Web3Forms, one for newsletter signup via Kit — both with AJAX submission, no page reload, and session-persistent "thank you" state
- Smooth client-side navigation via Astro's ClientRouter
- Full deployment on Cloudflare Pages with automatic redeploy on every push to `main`

### Estimated Effort
**Calendar time**: 6 days.  **Working hours:** 15–25.

## What This Taught Me About AI-Assisted Development

The AI was fast and consistent at the structural work: scaffolding, routing, component architecture, design system, deployment configuration. Things that have clear right answers and follow patterns.

It was less reliable anywhere human judgment was the input: evaluating whether a biography was complete, deciding which hero variant felt right for the audience, knowing when a UX behaviour (like the form redirect) was wrong even if technically functional.

That division of labour is, I think, the honest shape of vibe coding right now. **The AI handles implementation. You handle judgment.** And the quality of the output is determined almost entirely by the quality of your judgment, not by the sophistication of the AI.

Which means, counterintuitively, that experience matters more in an AI-assisted workflow, not less. You just spend that experience differently.

---

*Arianna's site is at [ariannalanzillotti.com](https://ariannalanzillotti.com).