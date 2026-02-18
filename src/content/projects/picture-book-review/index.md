---
title: "Picture Book Review"
description: "A publishing and review platform for picture books, built with Astro and Sanity CMS"
date: "2024-03-01"
demoURL: "https://picturebookreview.com"
---

## Picture Book Review

![Picture Book Review](/pbr.png)

Picture Book Review is a publishing platform dedicated to celebrating picture books — featuring editorial reviews, author spotlights, and curated reading lists. I built the site with Astro for static site generation and Sanity as the content management backend, giving editors a smooth publishing workflow while keeping the frontend fast and performant.

## Architecture

The site is built as a statically generated Astro site that pulls content from a Sanity CMS backend at build time, with on-demand revalidation for new content. This gives the best of both worlds: fast, CDN-delivered pages for readers, and a flexible structured content layer for editors.

![Picture Book Review Layout](/pbr-1.png)

Sanity's content model handles the richly structured data that picture book content requires — GROQ queries power featured books, review listings, author bios, and tag-based filtering.

## Key Features

- **Editorial reviews** — rich text content with custom portable text components for callouts, book metadata, and inline images
- **Author and illustrator profiles** — reference-based content connecting books to their creators
- **Curated reading lists** — editor-assembled collections with drag-and-drop ordering in Sanity Studio
- **Tag-based filtering** — browse by age range, theme, and award recognition
- **SEO-optimized static pages** — Astro's SSG with Sanity-driven metadata

## Tech Stack

- **Astro** — static site generation with component-based architecture
- **Sanity CMS** — structured content backend with custom Studio configuration
- **GROQ** — Sanity's query language for fetching and filtering content
- **TypeScript** — end-to-end type safety with Sanity's generated types
- **Tailwind CSS** — utility-first styling
- **Vercel** — deployment and edge caching
