# Refactoring Evidence, Architecture Notes, and AI Disclosure


## Refactoring Evidence
- **Reduced duplication:** Shared classes such as `.shell`, `.site-header`, `.button`, `.event-card`, and `.site-footer` are used across the pages.

- **Lowered specificity:** Most rules use simple class selectors. One shared mobile media query handles the responsive layout.

- **Clarified naming:** Component classes describe their purpose, such as `.page-hero`, `.contact-form`, and `.event-row`. Utilities use the `u-` prefix.

- **Replaced repeated values:** Colors, spacing, shadows, radii, transitions, and focus styles are stored as `--garden-*` variables in `:root`.

### Before and After

**Before:** Repeated colors, spacing, layout rules, and page-specific selectors could become inconsistent.

**After:** Reusable components and design tokens keep the six pages consistent and easier to update.


## Architecture Notes

- **Order:** Tokens, reset, shared header, page layouts, components, utilities, states, responsive rules, then print rules.

- **Tokens:** Colors are named by role, such as `--garden-forest` and `--garden-muted`, instead of by appearance. Spacing uses a small rem-based scale.

- **Naming:** Classes describe components and states. Utilities begin with `u-`, while state classes begin with `is-` when appropriate.

- **Browser checks:** The site includes a `760px` mobile breakpoint, responsive images, visible keyboard focus, disabled-control styling, and print rules. Test each page at desktop and mobile widths, with keyboard navigation, and in print preview.


## AI Assistance Disclosure

I used AI to help with CSS organization, design token names, reusable classes, and refactoring ideas. I reviewed the suggestions and adapted them to fit my project. I made the final design decisions and checked each page in the browser on both desktop and mobile screen sizes.