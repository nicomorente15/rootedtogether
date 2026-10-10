# Fallback path, Document Checks, and AI Disclosure

## What I extended
- I added a stronger responsive layout foundation in css/styles.css by using logical sizing and flexible constraints.
- I kept the reusable event card container-query setup and added a fallback for browsers that don’t support container queries.
- I updated the grid system to use intrinsic sizing patterns like auto-fit and minmax(), which makes the layout adapt a lot better across screen sizes.
- I added a support for prefers-reduced-motion so the page is a little nicer for people who want less animation.
- I used content-driven breakpoints instead of just using generic labels, since that feels more realistic for how the layout presents itself.

## Required parts covered
1. Responsive layout foundation
   - The shared .shell wrapper now uses a constrained width and logical sizing.
   - Section spacing uses clamp() so the spacing stays pretty consistent across different widths.

2. Advanced Grid patterns
   - event-grid, values-grid, ways-grid, resource-grid, and footer-grid all use repeat(auto-fit, minmax( )), which helps them resize more naturally.

3. Subgrid or documented alternative
   - I didn’t end up using subgrid here because the current structure already works pretty well with section wrappers and card containers.
   - If the layout ever gets more complicated and alignment starts being a pain, subgrid would be the next thing I would adjust/refine.

4. Container-query component
   - .event-card-container is set up as a reusable container-query component.
   - The layout inside .event-card changes when the container reaches a usable width.

5. Content-driven breakpoints
   - The media queries are based on actual layout changes, like the header wrapping, content stacking, and the card grids reflowing.
   - So they’re not just random breakpoints for specific device sizes.

6. User preferences
   - I added a prefers-reduced-motion media query so motion gets reduced when the user asks for it.

7. Feature/fallback strategy
   - I used @supports for progressive enhancement, so the advanced layout feature works when supported.
   - If a browser doesn’t support container queries, it goes back to a normal block layout instead of breaking.

## Testing evidence
### 1) Narrow layout check
- At around 360px to 480px, I checked that the mobile menu shows up, the hero content stacks into one column, and the grid cards are on top of each other.
- Expected result: the layout reflows without any horizontal overflow.

### 2) Medium layout check
- At around 768px to 1024px, I checked that the header still works, the content stays readable, and the card grids shift into two columns where there’s enough space.
- Expected result: everything still feels balanced and easy to use.

### 3) Wide layout check
- At widths above around 1100px, I checked that the content stays centered with a good amount of whitespace and that the page uses the wider space without feeling awkward.
- Expected result: the layout feels open and organized.

### 4) 200% zoom 
- I zoomed to 200% and checked that the page stayed readable and didn’t cut out content or make the user scroll sideways.
- Expected result: text and controls stay accessible.

### 5) Keyboard focus check
- I used Tab to move through the nav, buttons, and form fields.
- Expected result: the focus rings are visible and easy to follow and because its ORANGE.

### 6) Preference / fallback condition check
- I checked the prefers-reduced-motion: reduce condition to make sure the smooth scrolling and transitions get suppressed.
- I also checked the fallback path for browsers without container-type: inline-size, and the event cards still lay out in a normal block arrangement.

## Notes
- I intentionally didn’t use subgrid yet because the current layout already feels clean and organized with section wrappers and card containers.
- The breakpoints are based on what the layout actually needs, which makes the system more reliable across different screen sizes.

## AI DISCLOSURE
- AI helped me explain CSS syntax, suggest edge cases, and troubleshoot issues in the responsive layout.