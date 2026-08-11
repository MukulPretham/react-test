# react-test

A minimal [React](https://react.dev) + [TypeScript](https://www.typescriptlang.org/) starter project powered by [Vite](https://vite.dev). It is scaffolded from the official `react-ts` Vite template and includes a small counter demo to verify that Hot Module Replacement (HMR) and the build pipeline are working.

## Features

- **React 19** with the modern JSX transform and `StrictMode` enabled in development.
- **TypeScript ~5.7** for type-safe components, compiled with project references (`tsc -b`).
- **Vite 6** dev server with instant startup and HMR via [`@vitejs/plugin-react`](https://github.com/vitejs/vite-plugin-react) (Babel-based Fast Refresh).
- **ESLint 9** flat config with `typescript-eslint`, `eslint-plugin-react-hooks`, and `eslint-plugin-react-refresh`.
- **Production build** that type-checks the project and emits static assets for any host.
- **Minimal footprint** — the only runtime dependencies are `react` and `react-dom`.

## Tech Stack

| Tool | Version (from `package.json`) |
| --- | --- |
| React | ^19.0.0 |
| React DOM | ^19.0.0 |
| Vite | ^6.3.1 |
| TypeScript | ~5.7.2 |
| ESLint | ^9.22.0 |

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org) 18+ (20+ recommended) and npm.

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/MukulPretham/react-test.git
cd react-test

# 2. Install dependencies
npm install
```

### Start the dev server

```bash
npm run dev
```

Vite starts a local dev server (printed in the terminal, by default `http://localhost:5173`) with HMR enabled. Open the URL in your browser — you should see the Vite + React landing page with a working counter button.

## Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite dev server with HMR. |
| `npm run build` | Type-check with `tsc -b`, then create a production bundle with `vite build`. Output goes to `dist/`. |
| `npm run lint` | Run ESLint over the project (`eslint .`). |
| `npm run preview` | Serve the production build locally so you can preview the `dist/` output. |

## Project Structure

```
react-test/
├── index.html          # HTML entry point; loads /src/main.tsx
├── package.json        # Dependencies and npm scripts
├── vite.config.ts      # Vite configuration (react plugin)
├── tsconfig.json       # TypeScript project references
├── tsconfig.app.json   # TypeScript config for src/
├── tsconfig.node.json  # TypeScript config for Vite config files
├── eslint.config.js    # ESLint 9 flat config
└── src/
    ├── main.tsx        # React entry; mounts <App /> into #root in StrictMode
    ├── App.tsx         # Root component (counter demo)
    ├── App.css         # Styles for App
    ├── index.css       # Global styles
    └── assets/
        └── react.svg   # React logo asset
```

## How It Works

- `index.html` is the single HTML entry and contains a `<div id="root">` mount point.
- `src/main.tsx` uses `createRoot(...).render(...)` to mount the `<App />` component wrapped in `<StrictMode>`.
- `src/App.tsx` is the root component. It renders the Vite and React logos, a heading, and a counter button driven by React's `useState` hook. The HMR note in the UI ("Edit `src/App.tsx` and save to test HMR") reflects that editing this file hot-reloads in the browser.
- `src/App.css` and `src/index.css` contain the styling, including the logo-spin animation and `prefers-reduced-motion` handling.

## Linting

Run the linter at any time:

```bash
npm run lint
```

The project ships with ESLint 9 flat config and recommended rules for TypeScript, React Hooks, and React Refresh. See [docs/development.md](docs/development.md) for guidance on enabling type-aware lint rules.

## License

No license is specified for this repository.