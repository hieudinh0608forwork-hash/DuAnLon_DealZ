# Design System

## Brand palette
- Orange `#FD550A` — primary action/brand.
- Deep green `#015D47` — anchor/navigation/strong text.
- Lime `#E0F354` — selective highlight.
Suggested neutrals: ink `#17211D`, warm background `#FFF9F3`, surface `#FFFFFF`, muted surface `#F3F4F0`, border `#E4E8E2`, muted text `#64716B`. Validate contrast before finalizing.

## Direction
Bold editorial travel identity, large expressive headlines, strong color blocking, large destination imagery and energetic CTA. Operational UI (planner, map, finance, checkout) should remain calm and information-dense. Do not use all three accent colors on every component.

## Components
Header/mobile nav; hero/search form; destination/service cards; supplier identity; trip summary; itinerary day cards; map panel + stop list; budget breakdown; booking timeline; partner listing editor; dialog/drawer/toast/forms/skeleton/empty states.

## Interaction
Every action has loading/success/error; destructive action confirms or supports undo; map/list stay synchronized; keyboard access and visible focus; color is never the only status signal; forms explain errors.

## Responsive
Mobile-first. Planner map/list become tabs or collapsible panel on narrow screens; desktop can use split view. Checkout price summary remains visible without obscuring fields. No accidental horizontal overflow.

## Typography and assets
Modern sans-serif with Vietnamese diacritic support. Large display type for marketing, restrained dashboard scale. Use owned/licensed/approved imagery; no random hotlinked images in production.
