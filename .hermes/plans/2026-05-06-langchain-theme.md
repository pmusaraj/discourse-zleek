# LangChain-inspired Discourse theme plan

## Reference URL

- Source: https://www.langchain.com/
- Pages inspected: homepage via browser snapshot, visual analysis, and computed CSS variables.
- Goal: translate LangChain's developer-tool visual system into a conservative Discourse theme, not a marketing-page clone.

## Visual extraction

- Palette:
  - Near-black navy background: `#030710`
  - Elevated navy panel: `#07101d`
  - Strong navy border: `#161f34`
  - Pale blue text: `#cce9ff`
  - Near-white text: `#f2faff`
  - Sky blue accent: `#7fc8ff`
  - Soft light-blue panel: `#e5f4ff` / `#f2faff`
- Typography:
  - LangChain uses Aeonik; theme will use system sans fallback for maintainability.
  - Add monospace flavor for buttons, nav labels, metadata, tags, and counters.
- Borders/shadows:
  - Thin blue-gray 1px borders are core.
  - Minimal conventional shadows; use subtle blue glow only on focus/hover.
- Radius/spacing:
  - Compact rectangular radii, around 6–10px; avoid Payway-style pills.
- UI motifs:
  - Dark technical surfaces, light-blue accents, outlined cards, small dot/line details.

## Discourse mapping

- Color scheme:
  - `primary`: pale blue text
  - `secondary`: dark navy page background
  - `tertiary`: sky blue links/actions
  - `quaternary`: muted navy-blue accent
  - `header_background`: near-black navy
  - `header_primary`: near-white blue
  - `highlight`: deep blue-gray
- CSS targets:
  - `body`, root tokens, header, sidebar, nav pills
  - welcome banner/search input
  - topic list/category list/card surfaces
  - buttons, forms, composer, menus, alerts
  - posts, quotes, code blocks, tags/badges
- Keep Discourse layout recognizable and avoid custom JS/connectors.

## Theme scaffold

- Repo: `/Users/pmusaraj/Projects/discourse-langchain-theme`
- Files:
  - `about.json`
  - `common/common.scss`
  - `README.md`
- No external fonts or copied LangChain assets.

## Testing plan

1. Import/update theme into local Discourse Docker instance.
2. Set as default and user-selectable.
3. Clear/rebuild theme stylesheets; restart Unicorn if rendered page keeps old hash.
4. Verify:
   - `/latest` topic list
   - `/categories`
   - a topic page
   - rendered theme meta/link and computed CSS variables
   - no theme alert banners or relevant console errors.
