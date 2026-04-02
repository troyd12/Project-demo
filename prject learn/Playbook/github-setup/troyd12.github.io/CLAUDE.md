# TD Movement — Portfolio Site

## Project Overview
Personal portfolio website for Troy Dixon — "The TD Movement." Single-file HTML/CSS/JS site showcasing recruiting career and brand. Hosted on Netlify with custom domain tdmovement.com.

## Files
- `index.html` — Main portfolio site (~105KB, all HTML/CSS/JS in one file)
- `nike_head.png` — Nike puzzle head hero image (1575x859px, RGBA with baked-in alpha fade)
- `CNAME` — Custom domain config (tdmovement.com)
- `robots.txt` — Search engine crawling rules
- `sitemap.xml` — Site structure for SEO indexing

## Design System
- **Brand color:** Volt green `#C8F900` (CSS variable `--orange`)
- **Background:** Near-black `#0a0a0a` (CSS variable `--bg`)
- **Fonts:** `Bebas Neue` (headings), `Space Grotesk` (body)
- **Custom cursor:** Volt green dot + ring with lerp tracking
- **Scroll progress bar:** Volt green gradient, fixed top

## Hero Section Layout
- Two-column flex row centered on page (justify-content: center; gap: 1vw)
- Image column (`.hero-visual`): flex: 0 0 55vw; margin-left: -10vw; position: relative
- Text column (`.hero-content`): flex: 0 0 auto; max-width: 520px; margin-left: -28vw; z-index: 3
- Volt green glow halo behind image (`.hero-visual::before` radial gradient)
- 5 volt green particles drift upward around image (`#heroParticles` canvas inside `.hero-visual`)

## Animation Sequence
1. 0ms: Black screen, intro overlay (`#puzzleIntro`)
2. 300ms: "TD MOVEMENT" letters fly in from all directions + volt green glow blooms
3. 6000ms: "RELENTLESS . MOVEMENT" tagline appears
4. 8200ms: Intro dissolves, nav + hero text stagger in (10-step sequence)
5. 12400ms: Hero image slides in with `img-live` class + particles start
6. ~15400ms: `imageArrive` keyframe glow burst on image
7. 10400ms: Intro DOM removed (display: none)

## JS Architecture
- Per-letter fly-in intro with `buildLetters()` + `flyIn()` functions
- `setTimeout` chain (not CSS delays) for bulletproof timing
- `initHeroParticles(canvas)` — particle system with `running` boolean flag
- `IntersectionObserver` pauses/resumes particles when scrolled away
- `try/catch` wrapper on entire intro IIFE with graceful fallback
- Null guards on: `introGlow`, `hv` (hero-visual), `pc` (particles), `scard`
- `onerror` handler on hero `<img>` for load failure

## Sections
1. Hero (centered two-column with image + text)
2. Brand marquee strip (CSS `@keyframes marquee-scroll`)
3. Philosophy/About
4. Projects/Work (with modal popups via `.modal-overlay`)
5. Skills (filter tabs using `data-cat`)
6. Stats cards (live hire counter via `requestAnimationFrame`)
7. Contact (copy-to-clipboard with toast)
8. Footer

## Key Features
- Neural network constellation background (`#neuralBg` canvas, 90 nodes)
- Custom cursor (volt green dot + ring)
- Scroll progress bar
- IntersectionObserver scroll-reveal (`.r` to `.v` class)
- Active nav highlighting via IntersectionObserver
- Project modal popups (3 modals)
- Link preview tooltips on social icons
- Dark/light theme toggle
- Back-to-top button

## Mobile Responsive
- `@media(max-width:768px)`: hero switches to flex-direction: column, image becomes width: 90%, animations disabled

## Code Style Rules
- All code stays in a single `index.html` file (HTML + CSS + JS combined)
- Use CSS custom properties for colors (--orange, --bg)
- Use Bebas Neue for any new headings, Space Grotesk for body text
- Animation timing uses setTimeout chains, not CSS animation-delay
- Always add null guards when accessing DOM elements
- Canvas elements need IntersectionObserver for performance
- Keep volt green (#C8F900) as the accent — never change the brand color

## Known Issues
- `Troy_Dixon_Resume.docx` is referenced in HTML but file does not exist — will 404 on click
- nike_head.png must be in the repo root alongside index.html

## Deployment
- Primary host: Netlify (drag-and-drop via Netlify Drop or CI)
- Domain: tdmovement.com
- GitHub repo serves as source of truth
- Any push to main should trigger a Netlify rebuild if CI is connected
