# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML marketing funnel website for a coaching/course business. It consists of multiple landing pages designed for lead generation and appointment booking.

## Architecture

**Main Funnel Flow:**
- `index.html` - VSL (Video Sales Letter) landing page with CTA to application
- `application.html` - Typeform embedded application with video testimonials
- `booking.html` - Calendly scheduling page for qualified leads
- `confirmation.html` - Thank you page with FAQ videos and next steps

**Webinar Funnel (separate flow in `/Webinar Funnel/`):**
- `registration.html` - Webinar registration form
- `confirmation.html` - Webinar confirmation with calendar links

## Design System

- **Color Palette:** Black background (#000000), beige text (#F5F5DC), blue accent (#0171E3)
- **Typography:** Apple system fonts (SF Pro Display fallback chain)
- **CTA Style:** Blue (#0171E3) rounded buttons with 980px border-radius (pill shape)
- **Layout:** Max-width containers (800-1200px), responsive with mobile breakpoints at 768px and 480px

## Key Integrations

- **Typeform:** Embedded forms using `data-tf-live` attribute
- **Calendly:** Inline calendar widget for booking calls
- **YouTube:** Video testimonials with custom modal player
- **Wistia:** Placeholder comments indicate Wistia player integration for main VSL videos

## UTM Tracking

All pages include a shared UTM parameter tracking script that:
1. Captures UTM params from URL and stores in sessionStorage
2. Appends UTM params to all internal `.html` links
3. Passes UTMs to embedded Typeform/Calendly widgets

## Deployment

Hosted on Vercel with clean URLs enabled (`vercel.json` config removes `.html` extensions).

## Common Tasks

**Local Development:**
```bash
# Serve files locally (any static server works)
python3 -m http.server 8000
```

**Adding Testimonials:**
- Screenshot testimonials: Add images to `images/testimonials/` and reference in grid
- Video testimonials: Use YouTube video IDs in `data-video` attributes on `.video-card` elements

**Replacing Placeholder Content:**
Search for `[` brackets to find placeholder text that needs customization (brand name, headlines, phone numbers, etc.)
