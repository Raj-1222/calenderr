# Wall Calendar

A premium, SaaS-quality interactive wall calendar built with Next.js, Tailwind CSS, and date-fns.

![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-v4-38bdf8?logo=tailwindcss)
![License](https://img.shields.io/badge/license-MIT-green)

---

## Features

- **Date Range Selection** — click to set start, hover to preview, click again to lock end date
- **Notes System** — per-date and per-range notes with 800ms auto-save to `localStorage`
- **Dynamic Hero Banner** — month-specific photography with parallax mouse-tracking effect
- **Light / Dark Mode** — class-based toggle with system preference detection and no flash on load
- **Month Animations** — smooth fade+slide transition when navigating between months
- **Keyboard Shortcuts** — `←` / `→` navigate months, `T` jumps to today, `Escape` clears selection
- **Accent Color System** — each month has its own accent color driving all interactive highlights
- **Glassmorphism UI** — backdrop blur cards, soft shadows, rounded corners throughout
- **Fully Responsive** — split layout on desktop, stacked on mobile, touch-friendly sizing

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| [Next.js 16](https://nextjs.org) | App framework (App Router) |
| [TypeScript](https://typescriptlang.org) | Type safety |
| [Tailwind CSS v4](https://tailwindcss.com) | Styling |
| [date-fns](https://date-fns.org) | Date logic |
| [lucide-react](https://lucide.dev) | Icons |
| `localStorage` | Notes persistence (no backend) |

---

## Getting Started

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Start production server
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Project Structure

```
wall-calendar/
├── app/
│   ├── globals.css          # Tailwind imports, dark mode variant, keyframes
│   ├── layout.tsx           # Root layout with dark mode flash prevention script
│   └── page.tsx             # Entry point
├── components/
│   └── Calendar/
│       ├── CalendarContainer.tsx   # Main layout, theme toggle, keyboard shortcuts
│       ├── CalendarHeader.tsx      # Month/year display, prev/next/today controls
│       ├── CalendarGrid.tsx        # 7-column day grid with weekday headers
│       ├── DayCell.tsx             # Individual day button with range/today/selected states
│       ├── ImageBanner.tsx         # Hero image with parallax and gradient overlay
│       └── NotesPanel.tsx          # Textarea with auto-save, timestamps, delete
├── hooks/
│   ├── useCalendar.ts       # All calendar state: navigation, range selection, hover
│   ├── useNotes.ts          # localStorage CRUD for notes
│   └── useTheme.ts          # Dark mode toggle with useLayoutEffect (no FOUC)
├── lib/
│   └── monthData.ts         # Per-month images, taglines, accent colors, gradients
└── types/
    └── calendar.ts          # Shared TypeScript interfaces
```

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `←` | Previous month |
| `→` | Next month |
| `T` | Jump to today |
| `Esc` | Clear date selection |

---

## How Notes Work

1. Select a single date or a date range on the calendar
2. The Notes panel activates with the selected date(s) as context
3. Type your note — it auto-saves after 800ms of inactivity
4. Click **Save** to save immediately
5. Notes persist in `localStorage` under the key `wall-calendar-notes`
6. Each note is keyed by `YYYY-MM-DD` (single) or `YYYY-MM-DD_YYYY-MM-DD` (range)

---

## License

MIT
