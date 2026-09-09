# Design System

## Visual Theme

Restrained paper index. Near-white field, 14px Inter, hairline rules, a left year column and a right day/month. Hover dims sibling rows; the active row and the year stay full.

Reference: [benji.org](https://benji.org/) Writing list only.

## Color Palette

| Role | Value | Usage |
|------|--------|--------|
| Canvas | `#fdfdfc` | Page background |
| Ink | `#111111` | Row titles |
| Muted | `rgba(0, 0, 0, 0.4)` | Section label, year, dates |
| Rule | `#f2f2f2` | Section underline, row hairlines |
| Year-group rule | `#f2f2f2` | Divider under a year block |
| Selection ink | `#111111` | `::selection` |
| Selection wash | `#ededed` | `::selection` |
| Focus | `rgba(0, 122, 255, 0.5)` | `:focus-visible` outline |
| New (unused) | `rgb(255, 0, 170)` | Reserved; not shown |

## Typography

- Family: Inter (variable, opsz + wght), fallback system-ui / -apple-system
- Size: `0.875rem` (14px) for label, title, date
- Weight: `460` (variable)
- Letter-spacing: `-0.00563rem`
- Line-height: `normal` / `1.25rem` on the section label
- Dates: `font-variant-numeric: tabular-nums`
- No all-caps body. No second display face on this page.

## Layout

- Shell: contained. `max-width: 36.375rem`, centered
- Gutter: `1rem` desktop, `1.5rem` below 768px
- Top inset: `5rem` desktop, `2rem` below 768px
- Bottom inset: `5rem`
- Row padding: `0.735rem 0`, title inset `6.75rem` (`3rem` below 520px)
- Year sits in the left inset of the first row of each year group
- Month abbreviation and day sit on the right (`Sep 8`)
- Hairline under in-year rows starts at the title inset, not under the year

## Components

- Section label: muted 14px, `padding-bottom: 0.5rem`, bottom hairline
- Year groups: nested lists. Outer `li` is a year. Inner `li` is a row
- Row is one `<a>`: title + `<time>`
- No cards, no borders besides 1px `#f2f2f2` rules, no shadows, no radius on content

## Motion

- First load: `staggerIn` 500ms ease, 8px rise, 50ms steps
- Hover (min-width 520px): sibling titles and dates to opacity `0.3` in 140ms ease; hovered row back to `1`; years stay `1`
- `prefers-reduced-motion: reduce`: no stagger; hover opacity may remain
