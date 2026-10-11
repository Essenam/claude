# Motion System

## Principles
1. **Motion explains** — reveal structure, show cause → effect, guide the eye to the next action.
2. **Motion is quiet** — most UI motion is 150–300ms; only storytelling moments go longer.
3. **One physics** — a single set of easings and durations used everywhere.
4. **Respect the user** — `prefers-reduced-motion: reduce` swaps movement for opacity fades or nothing.

## Tokens
| Token | Value | Use |
|---|---|---|
| --dur-instant | 100ms | press states |
| --dur-fast | 180ms | hovers, toggles |
| --dur-base | 260ms | menus, popovers, tabs |
| --dur-slow | 480ms | panels, route transitions |
| --dur-story | 800–1400ms | hero entrances, scrollytelling |
| --ease-out | cubic-bezier(.2,.8,.2,1) | entrances |
| --ease-in-out | cubic-bezier(.65,0,.35,1) | moves |
| --ease-spring | framework spring (stiffness ~260, damping ~26) | draggables, cards |

## Patterns and where they belong
| Pattern | Good for | Implementation hints |
|---|---|---|
| Hero video / ambient loop | setting place and scale | see media-curation.md |
| Scroll reveal (fade + 12–24px rise, staggered) | section entrances | IntersectionObserver or framework `whileInView`; once only |
| Sticky storytelling | "how it works", multi-step workflows | `position: sticky` visual + scrolling steps that swap UI states |
| Subtle parallax | depth in cinematic sections | ≤ 10–15% offset, transform only, disabled on reduced motion and low-power mobile |
| Animated counters | proof stats | count once on view, tabular numerals, final value in HTML for no-JS/SEO |
| Chart draw-in | dashboards, data stories | stroke-dashoffset / library transitions, ≤ 800ms |
| Map animation | geography, flows, networks | fly-to, animated arcs/routes, pulsing nodes for live activity |
| Layered UI reveal | product showcase | stacked panels sliding into place with slight rotation/shadow depth |
| Route/page transitions | app navigation | shared-element or cross-fade ≤ 300ms; never block input |
| Microinteractions | buttons, toggles, saves, copy | state change + confirmation (check, toast) |
| Skeletons / shimmer | loading | match final layout exactly; no spinners on full pages |

## Libraries (use what the stack already has)
CSS transitions/animations and View Transitions API first; then Framer Motion / Motion One (React/JS), GSAP + ScrollTrigger (complex scroll), Lottie (designed vector animation), Mapbox GL / MapLibre / deck.gl (maps), Recharts / visx / ECharts / D3 (charts).
