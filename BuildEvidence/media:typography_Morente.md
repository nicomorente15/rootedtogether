# Testing Checklist

Responsive images
- [x] Checked `picture` + `srcset` behavior at widths: 320px, 375px, 768px, 1024px, 1440px

Zoom & readability
- [x] Verified layout and typographic scale at 200% zoom in Chrome and Firefox.

Slow network
- [x] Emulated 3G/Slow in DevTools; confirmed images load progressively and fall back to JPEG when WebP unsupported.

Image dimensions & file size
- Images/Hero-1200.jpg
- Images/Hero-800.jpg
- Images/Hero-400.jpg
- Images/Logo.svg

Alt text & semantics
- [x] All informative images have descriptive `alt` text.
- [x] Decorative images use `alt=""`.

Captions / transcripts
- No audio or video present; N/A.

Layout shift & CLS
- [x] Verified images have intrinsic `width`/`height` or `aspect-ratio` to avoid layout shift.
- [x] Measured CLS with Lighthouse / DevTools (note score).

Font loading
- [x] Using system font stack — no webfonts; `font-display` not required. If adding webfonts, use `font-display: swap` and preload when appropriate.

Accessibility checks
- [x] Keyboard navigation of header and mobile menu.
- [x] Focus styles present and visible (checked).
- [x] Images within `picture` have `alt` attributes.

Notes / Results
- Responsive widths: Tested at 320px, 375px, 768px, 1024px, 1440px — correct `srcset` images selected and no visual artifacts observed.
- 200% zoom: Layout and typographic scale verified in Chrome and Firefox; no overflow or unreadable text.
- Slow network: 3G emulation tested; images load progressively and fall back to JPEG as expected.
- CLS measurement: Lighthouse/DevTools run and report saved (report.html). Numeric CLS: 0.02 (good).

# AI Disclosure

Parts of the text on this site were drafted with assistance from an AI tool and reviewed and edited by Nicole Angelo Morente for accuracy and clarity. I verified the image sizes and technical details.

