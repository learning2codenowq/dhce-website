# DHCE Website — Claude Reference Document
> Use this file at the start of every new chat to ensure consistency across all pages.

---

## Project Overview
- **Site**: halalcertification.ie/enterprise
- **Stack**: WordPress + Astra + Spectra (Gutenberg)
- **Method**: Custom HTML blocks pasted directly into WordPress pages
- **Full-width breakout**: `width:100vw; left:50%; transform:translateX(-50%);` on every section
- **Astra page setting**: Full Width / Stretched, No Sidebar
- **GitHub repo** (internal reference only): https://github.com/learning2codenowq/dhce-website

---

## Brand Colors
```
Primary (teal):      #006271
Accent (green):      #82bb41
Accent hover:        #74a938
Background (white):  #fefeff
Light bg (sections): #f4f9f4 or #f5f8f8
Dark footer:         #012f37
```

---

## Typography Rules — CRITICAL
**DO NOT hardcode font-family or base font-size in any page code.**
Fonts and base sizes are controlled globally via Astra → Appearance → Customize.
Only hardcode font-weight, letter-spacing, text-transform, and color where needed for DHCE-specific styling.

---

## CSS Conventions
- All section IDs prefixed: `dhce-`
- All class names prefixed: `dhce-`
- Section padding: `90px 24px`
- Max content width: `1060px–1160px`
- Border radius: `10px` cards, `6px` buttons, `12px` large cards/banners
- Reset on every section: `*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }`

---

## Repeated UI Patterns

### Section Label (eyebrow)
```css
font-size: 11px;
font-weight: 700;
color: #82bb41;
letter-spacing: 0.14em;
text-transform: uppercase;
```

### Section Heading
```css
font-size: clamp(1.7rem, 3.5vw, 2.4rem);
font-weight: 800;
color: #006271;
letter-spacing: -0.02em;
line-height: 1.2;
```

### Primary Button
```css
background: #82bb41;
color: #fefeff;
font-size: 0.9rem;
font-weight: 700;
padding: 14px 30px;
border-radius: 6px;
/* hover */ background: #74a938;
```

### Secondary Button
```css
background: transparent;
color: #fefeff;
border: 2px solid rgba(254,254,255,0.3);
padding: 14px 30px;
border-radius: 6px;
/* hover */ border-color: rgba(254,254,255,0.65); background: rgba(255,255,255,0.07);
```

### Card Style
```css
background: #fefeff;
border-radius: 10px;
border: 1px solid rgba(0,98,113,0.1);
box-shadow: 0 2px 16px rgba(0,98,113,0.07);
/* hover */ transform: translateY(-4px); box-shadow: 0 12px 32px rgba(0,98,113,0.1);
```

### Icon Box
```css
width: 52px; height: 52px;
border-radius: 12px;
background: rgba(0,98,113,0.08);
/* icon stroke */ stroke: #006271; stroke-width: 1.75;
```

### Body text (on light bg)
```css
color: #666;
line-height: 1.7;
```

### Body text (on dark bg)
```css
color: rgba(254,254,255,0.68);
line-height: 1.75;
```

---

## Full-Width Section Template
```html
<style>
#dhce-SECTIONNAME *,
#dhce-SECTIONNAME *::before,
#dhce-SECTIONNAME *::after { box-sizing: border-box; margin: 0; padding: 0; }

#dhce-SECTIONNAME {
  position: relative;
  width: 100vw;
  left: 50%;
  transform: translateX(-50%);
  background: #fefeff;
  padding: 90px 24px;
  overflow: hidden;
}

.dhce-SECTIONNAME-inner {
  max-width: 1100px;
  margin: 0 auto;
}
</style>

<section id="dhce-SECTIONNAME">
  <div class="dhce-SECTIONNAME-inner">
    <!-- content -->
  </div>
</section>
```

---

## Pages Status
| Page | Status |
|------|--------|
| Homepage (index.html) | ✅ Complete — approved by Dr Umar |
| About DHCE | 🔄 In progress |
| Certification | ⬜ To build |
| Training | ⬜ To build |
| Contact / Apply | ⬜ To build |
| FAQs | ⬜ To build |

---

## Homepage Sections (for reference/consistency)
1. `#dhce-hero` — Dark teal, two-col, image slideshow, trust logos
2. `#dhce-process` — White bg, vertical step timeline
3. `#dhce-why` — Light green bg `#f4f9f4`, 3-col cards, bottom CTA banner
4. `#dhce-logos` — Dark teal, recognition logos row
5. `#dhce-footer` — Dark `#012f37`, 4-col grid

---

## Key Client Info
- **Client**: Department of Halal Certification Europe (DHCE)
- **Authority figure**: Dr Umar (approves designs)
- **Supervised by**: Islamic Centre of Ireland (formerly Al-Mustafa Islamic Centre)
- **Founded**: 2008
- **Markets**: Ireland, UK, Mainland Europe
- **Recognised by**: JAKIM, MUIS, EIAC, WHFC and IHAF
- **Target audience**: Food, cosmetics, and pharmaceutical businesses seeking halal certification

---

## WordPress Delivery Notes
- Each page = one Custom HTML block pasted into WordPress
- Footer and header are global — do NOT repeat in inner page code
- Test in WordPress/Astra, not in browser directly
- GitHub repo is for internal code reference only, not live hosting
- Font changes go through Appearance → Customize → Typography only