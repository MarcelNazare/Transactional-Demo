# Copperbelt Car Hire — Transactional Demo

> **Concept demo — not a client project.** This site was built to show a
> car hire firm what a booking-focused website looks like when it's done
> properly. It is not a live business. Every vehicle, rate, and booking
> is fictional.

---

## What this is

A single-page, mobile-first demo website for a fictional car hire firm
in the Copperbelt. Its job is to demonstrate one thing: **how a car hire
website turns a visitor into a booking enquiry.**

It is the second demo in a three-part portfolio, built for the
transactional niche in the set — businesses whose customers arrive with
a specific intent ("I need a car for three days, what does it cost, is it
available?") and who will abandon a site that makes them work for the
answer.

| | |
|---|---|
| **Fictional client** | Copperbelt Car Hire |
| **Niche** | Car hire / vehicle rental |
| **Primary outcome sold** | Completed booking enquiries |
| **Design system** | Vercel DESIGN.md (from `VoltAgent/awesome-design-md`) |
| **Stack** | Single HTML file, embedded CSS, Geist/Inter fallback, no build step |
| **Hosting** | Free tier (Vercel / Netlify) |
| **Status** | Concept demo — placeholder content throughout |

---

## Why this demo exists

A car hire customer does not want to read. They want to answer four
questions in under thirty seconds:

1. **Do you have the kind of car I need?**
2. **What does it cost per day?**
3. **Is it available on my dates?**
4. **How do I book it?**

Most car hire websites in Lusaka fail at questions 2 and 3. Rates are
hidden behind "contact us for a quote." Availability is a phone call.
The demo answers all four on the page, then hands the visitor a
pre-filled enquiry form.

The sales line for this demo is:

> *"I built a concept for a car hire firm. The fleet and rates are on the
> page, the availability check works, and the enquiry form comes
> pre-filled. Want me to build the real one with your fleet?"*

It replaces "do you have a portfolio?" with a live, clickable answer to
the exact objection a car hire owner will have: *"will this actually
get me bookings?"*

---

## Key features

### 1. Fleet showcase with transparent rates
- A **3-up grid** (desktop) / **1-up** (mobile) of vehicle cards.
- Each card shows: vehicle name, **daily rate as the visual anchor**,
  passenger capacity, transmission type, and a status pill.
- Rates are visible on the card. No "call for price." This is the single
  most important conversion decision on the page — ambiguity here is
  where bookings are lost.
- Cards use **hairline borders, no shadows**, tight padding. The layout
  reads like a spec sheet, not a brochure.

### 2. Booking enquiry flow
- A single form with: **pickup location, drop-off location, pickup date,
  return date, vehicle type**.
- The form is structured, labelled, and short. Every field earns its place.
- Submit button uses the primary accent color and the exact label
  the visitor expects: **"Send booking enquiry."**
- In this demo, the form is a **placeholder** — it validates on the
  client side and logs to the console. Wiring it to a real endpoint is
  the next build step (see *Roadmap*).

### 3. Simulated availability check
- A **status pill** next to each vehicle: **"Available"** in the accent
  color, **"Booked"** in muted gray.
- A simple **date-picker** in the hero and above the fleet that filters
  the grid — select a date range and the grid re-renders with the
  matching availability state.
- This is simulated with static data. Its purpose is to *show* the
  operational logic, not to run a real calendar. The demo proves you
  understand how car hire businesses actually work — availability is the
  product.

---

## Design decisions

The page is built on the **Vercel DESIGN.md** system. Why Vercel and not
Stripe (used for the consultancy demo):

| Requirement | Why Vercel fits |
|---|---|
| Fleet grid must read like a spec sheet | Vercel's precision and information density suit scannable data |
| Booking form must feel structured | Vercel's input and button components are transactional, not editorial |
| Availability status must be unambiguous | Black-and-white precision with a single accent color for state |
| Rates must be the visual anchor | Vercel's hierarchy puts numbers and labels first, decoration last |
| The page is a tool, not a manifesto | Vercel is built for tools; Stripe is built for long-form trust-building |

**Constraints carried over from the design system:**

- **Typography**: Geist (Inter fallback), tight letter-spacing, weight
  400–500 on body, weight 500 on the daily rate. No weight-300 elegance —
  this page is functional, not editorial.
- **Color**: Black, white, and neutral grays. **One accent color**,
  used only for: the primary CTA, the "Available" status pill, and
  focus states on form inputs.
- **Borders and structure**: Hairline borders (`1px`), **no shadows**
  on cards. The fleet grid is a structured table of cells, not floating
  rounded tiles.
- **Radius**: 6px maximum. Sharp, not soft.
- **No icons** except a single `→` in the primary CTA and a small
  calendar glyph inside the date-picker inputs.

**What was deliberately avoided:**

- Gradient backgrounds and atmospheric blobs
- Stock photos of cars on scenic roads
- "From K—" pricing with an asterisk that hides the real number
- Star ratings and "trusted by 10,000 customers" badges
- A "Contact Us" page instead of a booking form
- Decorative icons on every vehicle card

---

## File structure

```
/
├── index.html        # The entire demo — single file, embedded CSS + JS
└── README.md         # This file
```

No build step. No dependencies beyond the Geist or Inter font. Open
`index.html` in a browser, or deploy the folder to any static host.

The simulated availability logic and the form validation live in a
single `<script>` tag at the bottom of `index.html`.

---

## How to use this demo in a sales conversation

1. **Identify a car hire prospect** with a weak site — rates hidden,
   no availability, no online enquiry.
2. **Send the link** with a one-liner referencing something specific:
   *"I noticed your rates aren't on your site — here's a concept that
   puts them front and centre."*
3. **Say the line:** *"The fleet and rates are live, the availability
   check works, and the enquiry form comes pre-filled. Want me to build
   this with your fleet?"*
4. **If they reply,** book a call and use the demo as the visual brief.

The demo is **not** sent cold to every business. It is sent to car hire
firms, and only after you've looked at their current site and found a
specific gap the demo closes.

---

## Roadmap (next build steps)

- [ ] **Wire the booking enquiry form** to a real endpoint
  (Formspree, Google Sheets via Apps Script, or a simple serverless
  function). Include an auto-reply email to the customer.
- [ ] **Make availability real.** Replace the static data with a simple
  JSON calendar per vehicle, stored in a Google Sheet or a small
  database. The UI doesn't change; the data source does.
- [ ] **Add a vehicle detail page** for each car — full spec, multiple
  photos, terms and conditions. The fleet grid links to it.
- [ ] **Add a "Book now" fallback** via WhatsApp for visitors who
  won't fill a form. In the Lusaka market, this is often the
  highest-converting path.
- [ ] **Add a simple admin view** so the client can mark a vehicle as
  "Booked" without touching code.
- [ ] **Build a second variant** for a different vehicle niche
  (e.g., minibus hire, equipment hire) to A/B the pitch.

---

## Reusing this demo for other transactional niches

The structure is deliberately generic enough to retarget:

| Element | Change for a new niche |
|---|---|
| Brand name | Swap `Copperbelt Car Hire` |
| Hero H1 | Rewrite around that niche's booking outcome |
| Fleet grid | Replace vehicles with the new inventory (rooms, equipment, venues) |
| Rates | Change to the pricing unit that niche uses (per night, per day, per event) |
| Availability check | Change the date logic to match the niche's booking model |
| Booking form fields | Swap pickup/drop-off for the fields that niche needs |

Keep the design system. Change the content. The demo is the **shell**;
the niche is the **fill**.

---

## Honesty note

This is a **concept demo**, not a real business. Every vehicle, rate,
location, phone number, and email address on the page is fictional. The
availability data is simulated. The booking form does not send anywhere.

The footer carries the line *"Concept demo — not a client project"* so
that anyone landing on it understands what they're looking at.

If you reuse this demo for a real client, remove that line, replace every
placeholder, and wire the form and availability data to real sources
before publishing.
