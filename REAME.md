# SpendWise Dashboard Shell

A responsive financial dashboard layout built using semantic HTML5, modern CSS Grid, Flexbox, and CSS Custom Properties.

## Overview & Architecture

### 1. CSS Grid Layout
- **Page Frame:** The outer container (`.dashboard-container`) uses CSS Grid to divide the desktop view into a fixed 260px sidebar and a flexible (`1fr`) content pane.
- **Card Matrix:** The dashboard cards container (`.cards-grid`) uses `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))` to dynamically manage layout columns without requiring extensive breakpoint rules.

### 2. Flexbox Component Architecture
- **Sidebar & Nav:** `.sidebar` and `.nav-menu` use column-based Flexbox layouts to structure branding and navigation links.
- **Header:** `.header` uses row-based Flexbox with `justify-content: space-between` to separate title context from user profile elements.
- **Cards:** Each `.card` utilizes Flexbox to isolate top-row metadata (Title + Icon) from bottom-row data values (Amount + Status Tag).

### 3. Theme System (CSS Custom Properties)
All colors, shadows, and transition timings are declared on the `:root` selector:
- `--brand-color`: Primary brand action and active states.
- `--accent-color`: Success and positive growth indicators.
- `--surface-color` & `--bg-color`: Contextual background layers.
- `--text-primary` & `--text-secondary`: High and medium contrast text tiers.

**Dark Mode:** Implemented via `@media (prefers-color-scheme: dark)` which overrides only the `:root` variables. No structural code duplication is needed.

### 4. Responsiveness (<768px)
Below `768px`, media queries reconfigure the application into a single-column layout:
- The sidebar shifts to a top navigation row with horizontally scrollable links.
- The main grid collapses to a single-column view on mobile viewports.

### 5. Accessibility & Micro-Interactions
- Cards include `tabindex="0"` to allow standard keyboard focus navigation.
- Focus and hover interactions use smooth, hardware-accelerated transitions (`transform: translateY(-4px)` and `box-shadow`) operating within a 200ms frame limit.