# Favorites

A minimal React + Vite + TypeScript starter wired with Tailwind CSS v4 and Lucide icons.

**Tech Stack**
- **Build**: `vite@7` + TypeScript
- **UI**: `react@19`, `tailwindcss@4` (via `@tailwindcss/vite`)
- **Icons**: `lucide-react`
- **Linting**: ESLint (TypeScript + React hooks + React Refresh)

## Getting Started
- **Prerequisites**: Node 18+ and a package manager (`pnpm` recommended; lockfile included)
- **Install**: `pnpm install` (or `npm i` / `yarn`)
- **Dev**: `pnpm dev` — starts Vite dev server
- **Build**: `pnpm build` — type-checks then builds for production
- **Preview**: `pnpm preview` — serves the production build locally

## Project Structure
```
.
├─ index.html                 # App entry HTML
├─ src/
│  ├─ main.tsx               # React root + Tailwind CSS import
│  ├─ App.tsx                # Example component using Lucide + Tailwind
│  ├─ index.css              # Tailwind v4 entry (`@import 'tailwindcss'`)
│  └─ vite-env.d.ts          # Vite TS types
├─ public/                   # Static assets (served at /)
├─ vite.config.ts            # Vite + React + Tailwind plugins
├─ eslint.config.js          # ESLint config (TS + React)
├─ tsconfig*.json            # TypeScript configs (app/node)
├─ package.json              # Scripts and dependencies
└─ pnpm-lock.yaml            # Lockfile (pnpm)
```

## Tailwind CSS (v4) Setup
- **Wiring**: Tailwind is enabled by the Vite plugin in `vite.config.ts` and loaded via `src/index.css`.
  - `vite.config.ts`: `plugins: [react(), tailwindcss()]`
  - `src/index.css`: `@import 'tailwindcss';`
- **Usage**: Apply utility classes directly in JSX. Example in `src/App.tsx`:
  - `className="flex items-center gap-2"`
  - `className="h-6 w-6 text-blue-500"`
- **Custom Theme (optional)**: Tailwind v4 supports the `@theme` at-rule and CSS variables. If you need a theme, you can add to `src/index.css`:
  ```css
  @theme {
    --color-brand: #3b82f6; /* blue-500 */
  }
  ```
  Then use via `text-[--color-brand]`, `bg-[--color-brand]`, etc.

## Lucide Icons
- **Library**: `lucide-react` is installed and tree-shakeable.
- **Usage**: Import the icon component and render it in JSX.
  ```tsx
  import { Home } from 'lucide-react'

  export function Header() {
    return <Home className="h-6 w-6 text-blue-500" />
  }
  ```
- See all icons and props: https://lucide.dev/icons

## Scripts
- `pnpm dev`: Run dev server
- `pnpm build`: Type-check + production build
- `pnpm preview`: Preview production build
- `pnpm lint`: ESLint across the repo

## Conventions
- **TypeScript**: Strict mode is enabled; no unused locals/params.
- **Imports**: Vite bundler resolution with ESM is used; keep paths ESM-friendly.
- **Styling**: Prefer Tailwind utilities; colocate component-specific CSS if needed.

## Deployment
- The app builds to `dist/`. Host the static output on any static host (Vercel, Netlify, GitHub Pages, etc.).
- Local check: `pnpm build && pnpm preview`.

## Troubleshooting
- Tailwind classes not applying: Ensure `src/index.css` is imported in `src/main.tsx` and the plugin exists in `vite.config.ts`.
- Node version issues: Use Node 18+ (`nvm use 18` or later).

---

Generated from the repository’s current setup. Update as your app grows.
