# React Test

A minimal [React](https://react.dev) + [TypeScript](https://www.typescriptlang.org/) + [Vite](https://vite.dev) starter project (bootstrapped from the official Vite React-TS template).

## Features

- ⚡ **Vite 6** for a fast dev server and optimized production builds
- ⚛️ **React 19** with Strict Mode enabled
- 🧰 **TypeScript ~5.7** with strict type checking
- 🧹 **ESLint 9** (flat config) with `typescript-eslint`, `react-hooks`, and `react-refresh` rules
- 🔥 Hot Module Replacement (HMR) out of the box

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 18+ (or a version compatible with Vite 6)
- npm (or your package manager of choice)

### Install

```bash
npm install
```

### Run the dev server

```bash
npm run dev
```

Vite will start a local dev server (usually at `http://localhost:5173`). Edit `src/App.tsx` and save — the page hot-reloads instantly.

### Build for production

```bash
npm run build
```

This runs the TypeScript compiler (`tsc -b`) followed by `vite build`, emitting production-ready assets to `dist/`.

### Preview the production build

```bash
npm run preview
```

Serves the `dist/` output locally so you can verify the production bundle.

### Lint

```bash
npm run lint
```

Runs ESLint over the project (ignoring `dist/`).

## Scripts

| Command            | Description                          |
| ------------------ | ------------------------------------ |
| `npm run dev`      | Start the Vite dev server with HMR   |
| `npm run build`    | Type-check and build to `dist/`      |
| `npm run preview`  | Preview the production build locally |
| `npm run lint`     | Lint source with ESLint              |

## Project Structure

```
├── index.html            # HTML entry point (mounts #root, loads /src/main.tsx)
├── vite.config.ts        # Vite config (React plugin)
├── tsconfig.json         # TS project references root
├── tsconfig.app.json     # App TS config (strict, bundler resolution)
├── tsconfig.node.json    # Node-side TS config (for Vite config)
├── eslint.config.js      # ESLint flat config
├── public/
│   └── vite.svg          # Static assets
└── src/
    ├── main.tsx          # React entry — mounts <App /> in StrictMode
    ├── App.tsx           # Root component (starter demo with counter)
    ├── App.css           # Styles for App
    ├── index.css         # Global styles
    └── assets/
        └── react.svg     # React logo asset
```

## Tech Stack

| Tool        | Version  |
| ----------- | -------- |
| React       | ^19.0.0  |
| React DOM   | ^19.0.0  |
| TypeScript  | ~5.7.2   |
| Vite        | ^6.3.1   |
| ESLint      | ^9.22.0  |

## Notes

- This is a bare starter template — there's no application-specific logic yet, just the default Vite + React demo (a clickable counter). Replace the contents of `src/App.tsx` to start building your app.
- TypeScript is configured in strict mode (`strict: true`, plus `noUnusedLocals`, `noUnusedParameters`, etc.), so type errors will fail the build.
