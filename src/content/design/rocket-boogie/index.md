---
title: "Rocket Boogie Co."
description: "Website for a whimsical art and lifestyle goods brand, with tailored e-commerce and brand-forward design."
date: "2023-01-01"
category: "UX · UI Design"
role: "Designer & Developer"
skills: ["UX Design", "UI Design", "Web Development", "E-commerce", "Next.js", "Stripe"]
image: "/rbc-1.png"
images: ["/rbc-1.png", "/rbc-2.png"]
url: "https://rocketboogie.com"
---

Rocket Boogie Co. is a San Francisco-based art and lifestyle goods brand with a hand-painted, playful aesthetic. The site needed to match the brand's personality: irreverent, colorful, and handcrafted, while functioning as a reliable e-commerce storefront.

## Approach

Rather than adapting a third-party e-commerce platform, I built a fully custom storefront using Next.js 14 and a modern, composable stack. Every layer, from auth to payments to image delivery, was chosen to give the brand maximum flexibility without recurring platform fees.

## Stack

- **Next.js 14 (App Router):** SSR, API routes, and UI in one codebase
- **Supabase:** Postgres database, auth, and file storage
- **Stripe:** Payments and webhooks, no monthly subscription fee
- **Resend:** Transactional email for order confirmations and receipts
- **Vercel:** Deployment with native Next.js hosting

## Features

- Custom storefront design reflecting the brand's illustrative voice
- Product collection browsing with editorial-style layouts
- Supabase Auth for customer accounts and session management
- Stripe checkout with webhook-driven order fulfillment
- Mobile-first responsive design
