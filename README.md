# FIZZ — Strike Cold 🥤

A dark, premium single-page soda brand website built with **pure HTML + Tailwind CSS (CDN)**. No build step, no npm, no framework — just drop the file in a browser and it works.

---

## Preview

```
Section 01 — Hero         Floating can, animated bubbles, flavor selector, pack picker
Section 02 — Products     Three flavor cards with per-flavor accent colors + stats
Section 03 — Features     What's Inside — ingredient deep-dives, real numbers
Section 04 — Reviews      Verified testimonials + press strip
Section 05 — CTA + Footer Email waitlist, pricing tiers, full footer nav
```

---

## Getting Started

### Option 1 — Just open it

```bash
open fizz-soda.html
# or double-click the file in Finder / Explorer
```

That's it. No server required.

### Option 2 — Serve locally (recommended for smooth anchor scrolling)

```bash
# Python (built-in)
python3 -m http.server 8080
# then visit http://localhost:8080/fizz-soda.html

# Node (if you have npx)
npx serve .
```

---

## Project Structure

```
fizz-soda/
├── fizz-soda.html      # Entire site — all 5 sections in one file
├── README.md           # You are here
└── .gitignore          # Ignores OS junk and editor files
```

Everything lives in `fizz-soda.html`. There are no separate CSS or JS files.

---

## Tech Stack

| Layer      | Tool                                    | Notes                          |
|------------|-----------------------------------------|--------------------------------|
| Markup     | HTML5                                   | Semantic sectioning elements   |
| Styling    | [Tailwind CSS v3 CDN](https://tailwindcss.com) | Loaded via `<script>` tag |
| Typography | [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue) + [Inter](https://fonts.google.com/specimen/Inter) | Google Fonts |
| Icons      | Inline SVG (can illustration)           | No icon library dependency     |
| JS         | Vanilla — ~60 lines                     | Bubbles, pill selector, scroll reveal |

---

## Design Tokens

Defined in the `tailwind.config` block inside `fizz-soda.html`. Edit these to retheme the whole site:

```js
colors: {
  brand: {
    bg:      '#080C14',   // page background
    surface: '#0d1520',   // card / section surface
    card:    '#0a1018',   // product cards
    border:  '#0f1824',   // default border
    border2: '#1a2a3a',   // hover border
    cyan:    '#00C2FF',   // primary accent
    amber:   '#FF8C00',   // secondary accent / best-seller
    muted:   '#3a4a5a',   // body text
    dim:     '#1e2a3a',   // labels / captions
    light:   '#E8F4FF',   // headings / display
  }
}
```

---

## Sections

### Section 1 — Hero
- Full-viewport dark hero with floating can SVG
- Animated rising bubble background (vanilla JS)
- Flavor pill selector (Electric Citrus / Amber Ginger / Dark Berry)
- Pack size picker (12 / 24 / 48)
- Smooth scroll hint

### Section 2 — The Lineup
- 3 product cards, each with its own accent color
- Amber Ginger card elevated as Best Seller
- Per-flavor macro stats (caffeine / calories / artificial ingredients)

### Section 3 — What's Inside
- 2×2 feature grid: Cane Sugar, Natural Caffeine, Zero Artificial, Carbonated to Order
- Real numbers on each feature (GI index, caffeine duration, CO₂ volume, etc.)

### Section 4 — Cold Takes
- 3 verified customer reviews
- Aggregate rating (4.9 / 12k+) displayed in header
- Press strip: Vogue India, Economic Times, YS Stories, TechCrunch

### Section 5 — CTA + Footer
- Email waitlist with 10% first-order offer
- 3 pricing tiers (12 / 24 / 48 pack) with Best Value badge
- Full footer: Shop, Info, Follow columns + legal bar

---

## Customisation

### Swap flavors

Find the flavor pill block in Section 1 and the product cards in Section 2. Each flavor has:

- A `data-flavor` attribute on the pill
- An accent color class (`text-brand-cyan`, `text-brand-amber`, `text-purple-400`)
- A matching top bar color on the product card

### Change copy

All copy is inline in the HTML. Search for any text string and replace it directly.

### Add a real can image

Replace the inline `<svg>` in the hero with an `<img>` tag:

```html
<img
  src="your-can.png"
  alt="FIZZ Electric Citrus can"
  class="w-40 h-auto animate-float-can relative z-10"
/>
```

### Connect the email form

The waitlist input in Section 5 posts nowhere by default. Wire it up to your preferred service (Mailchimp, ConvertKit, Resend, etc.) by wrapping it in a `<form>` with the service's action URL, or adding a JS `fetch` on the button click.

---

## Browser Support

Tested in:

- Chrome 120+
- Firefox 121+
- Safari 17+
- Edge 120+

Tailwind CDN + CSS custom properties require a modern browser. IE is not supported.

---

## License

MIT — do whatever you want with it.

---

## Credits

Designed and built with [Claude](https://claude.ai) by Anthropic.  
Fonts by Google Fonts. No stock assets used.