# Design Guidelines: Staff Report & HR Management System

## Design Approach: Vibrant Enterprise Dashboard
**Selected Approach:** Reference-Based (Monday.com + ClickUp + Notion aesthetics)
**Justification:** Modern HR platforms successfully blend data utility with engaging visuals. Vibrant color systems increase user engagement and make complex data approachable while maintaining professional credibility.

**Core Principles:**
- Color-driven hierarchy: Strategic gradients and vibrant accents guide attention
- Dynamic data visualization: Charts and metrics with bold, differentiated colors
- Energetic professionalism: Playful color paired with clean structure
- Visual delight: Smooth gradients, colorful cards, and micro-interactions create joy

---

## Color Palette

### Primary Gradients
- **Hero Gradient:** 250 100% 65% → 280 100% 70% (Purple to Pink)
- **Card Accent 1:** 200 100% 50% → 220 100% 60% (Cyan to Blue)
- **Card Accent 2:** 340 100% 65% → 10 100% 60% (Pink to Orange)
- **Card Accent 3:** 160 90% 50% → 190 100% 45% (Teal to Turquoise)

### Light Mode
- **Background Primary:** 0 0% 99%
- **Background Secondary:** 240 20% 97%
- **Background Tertiary:** 250 30% 98%
- **Text Primary:** 240 15% 15%
- **Text Secondary:** 240 10% 50%
- **Border:** 240 15% 88%

### Dark Mode
- **Background Primary:** 240 15% 8%
- **Background Secondary:** 240 12% 12%
- **Background Tertiary:** 240 10% 15%
- **Text Primary:** 0 0% 98%
- **Text Secondary:** 240 8% 70%
- **Border:** 240 10% 22%

### Vibrant Functional Colors
- **Primary (CTA):** 250 95% 65% (Vibrant Purple)
- **Success:** 150 85% 50% (Bright Green)
- **Warning:** 40 100% 55% (Vivid Orange)
- **Error:** 350 90% 60% (Bright Red)
- **Info:** 200 95% 55% (Electric Blue)

### Data Visualization Palette
- **Chart Colors:** 270 100% 65%, 340 100% 60%, 200 100% 55%, 160 90% 50%, 30 100% 60%, 180 85% 50%
- **Performance Indicators:** Green (>85%), Orange (60-85%), Red (<60%)

---

## Typography

**Font Stack:** Inter (Google Fonts), system-ui fallback

**Scale:**
- Display: 36px/44px, Bold (700)
- H1: 28px/36px, Semibold (600)
- H2: 22px/30px, Semibold (600)
- H3: 18px/26px, Medium (500)
- Body Large: 16px/24px, Regular (400)
- Body: 14px/22px, Regular (400)
- Small: 13px/20px, Regular (400)
- Micro: 12px/18px, Medium (500)

---

## Layout System

**Spacing Primitives:** Tailwind units of 2, 4, 6, 8, 12, 16, 20, 24
- Micro: 2-4
- Component: 6-8
- Section: 12-20
- Page: 16-24

**Grid Structure:**
- Sidebar: 280px fixed, gradient background, collapsible to 72px
- Main content: flex-1, max-w-7xl container, px-6 lg:px-8
- Dashboard grid: 12-column (grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4)
- Data tables: Full-width with horizontal scroll, sticky headers

---

## Component Library

### Navigation
- **Sidebar:** Gradient background (250 100% 65% → 280 100% 70%), white text, frosted glass effect on hover, active state with white rounded pill background
- **Top Bar:** White bg with subtle shadow, 72px height, gradient underline accent, search with gradient focus ring, profile avatar with status indicator ring

### Cards & Panels
- **Stat Cards:** White bg, gradient left border (4px), rounded-xl, p-6, shadow-md, hover:shadow-xl with scale-102 transform
- **Metric Cards:** Gradient backgrounds with white text, large numbers, icon in colored circle (white/20 opacity)
- **Data Panels:** Subtle gradient borders, frosted backgrounds, rounded-2xl

### Data Display
- **Tables:** White rows, gradient hover states, 48px row height, colorful status badges, gradient column headers
- **Performance Indicators:** Circular progress with gradient strokes, percentage in center, micro trend arrows
- **Charts:** Gradient fills for area charts, vibrant multi-color bars, smooth curve lines, colored grid at 240 10% 92%

### Forms & Inputs
- **Text Inputs:** 44px height, gradient focus ring (2px), rounded-lg, transition-all 200ms
- **Select/Dropdowns:** Gradient arrow icon, colored option groups
- **File Upload:** Dashed gradient border, 140px height, gradient background on drag-over
- **Date Pickers:** Gradient selected dates, colored weekday headers

### Buttons
- **Primary:** Gradient bg (250 100% 65% → 280 100% 70%), white text, px-6 py-3, rounded-lg, shadow-lg, hover:shadow-xl
- **Secondary:** White bg, gradient text, gradient border (2px), hover:gradient background with white text
- **Icon Buttons:** 44px, gradient on hover, rounded-lg

### Overlays
- **Modals:** max-w-3xl, gradient top border, backdrop-blur-lg, shadow-2xl
- **Dropdowns:** Gradient dividers, hover states with gradient backgrounds
- **Toasts:** Gradient left border, slide-in from right, auto-dismiss 4s

---

## Key Page Layouts

### Dashboard Landing
- **Hero Section:** Full-width gradient banner (200px), welcome message, quick stats overlay with frosted cards, profile photo with gradient ring
- **Metrics Grid:** 4 cards with different gradient accents, large numbers, trend indicators, sparkline charts
- **Charts Row:** 2-column (line chart with gradient fill + colorful bar chart)
- **Quick Actions:** Gradient card backgrounds, white text, icon buttons

### Reports Hub
- **Filter Bar:** Sticky, frosted glass background, gradient pill toggles for date ranges, colorful department badges
- **Report Cards:** Masonry grid, gradient top borders by category, hover:lift effect, status indicators with gradient dots
- **Export Panel:** Gradient button, format selector with colored icons

### Staff Performance
- **Profile Header:** Gradient banner background, 120px avatar with colored ring, contact buttons with gradient backgrounds
- **KPI Dashboard:** 6 gradient cards in 3-column grid, large metrics, colored trend arrows, mini charts
- **Timeline Chart:** Full-width, gradient area fills, milestone markers with colored dots
- **Achievement Badges:** Colored pills with gradient backgrounds, earned vs. locked states

### HR Management
- **Staff Grid:** Card view with gradient hover states, avatar with department color ring, quick action buttons
- **Calendar View:** Month grid with gradient event blocks, color-coded by type (meetings, shifts, leave)
- **Leave Requests:** Timeline cards with status gradient pills, approve/reject with colored buttons

### Settings
- **Tab Navigation:** Vertical gradient pills, active state with full gradient background
- **Form Sections:** Gradient section dividers, helper text in muted color, save button with primary gradient

---

## Images

### Hero Images
- **Dashboard:** Abstract gradient mesh background (1920x400px), overlaid with frosted stat cards
- **Performance Pages:** Professional team collaboration photos with gradient overlays
- **Empty States:** Colorful illustrations (500x400px) for no data scenarios

### Profile & Avatars
- **User Avatars:** 44px circular default, 120px on profile pages, gradient ring borders for online status
- **Department Icons:** 32px gradient-filled circles with white icons from Heroicons

### Data Visualizations
- **Chart Thumbnails:** 240x180px preview cards with gradient backgrounds
- **Report Covers:** Generated gradient patterns based on category colors

---

## Animations

- **Hover States:** 200ms ease-out, scale-102 for cards, shadow transitions
- **Loading:** Gradient skeleton screens matching layouts, shimmer effect
- **Data Updates:** 600ms gradient pulse on new values
- **Page Transitions:** Instant (enterprise priority)
- **Scroll Reveals:** Subtle fade-up for dashboard cards (100ms stagger)