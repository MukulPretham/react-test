# react-test

A minimal [React](https://react.dev) + [TypeScript](https://www.typescriptlang.org/) starter project built with [Vite](https://vite.dev). It comes preconfigured with Hot Module Replacement (HMR), ESLint, and a production build pipeline.

> **Note:** This repo currently contains the default Vite starter template (a counter demo in `src/App.tsx`). Replace `src/App.tsx` and related assets with your actual application code.

## Tech Stack

- [React 19](https://react.dev)
- [TypeScript ~5.7](https://www.typescriptlang.org/)
- [Vite 6](https://vite.dev) with [`@vitejs/plugin-react`](https://github.com/vitejs/vite-plugin-react) (Babel-based Fast Refresh)
- [ESLint 9](https://eslint.org) with `typescript-eslint`, `eslint-plugin-react-hooks`, and `eslint-plugin-react-refresh`

## Prerequisites

- [Node.js](https://nodejs.org) (v18+ recommended for Vite 6)
- npm (bundled with Node.js)

## Getting Started

Install dependencies:

```bash
npm install
```

Start the dev server with HMR:

```bash
npm run dev
```

Open the URL printed in the terminal (default: <http://localhost:5173>).

## Available Scripts

| Script            | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `npm run dev`     | Start the Vite development server with HMR                               |
| `npm run build`   | Type-check with `tsc -b`, then create a production build in `dist/`      |
| `npm run preview` | Preview the production build locally                                     |
| `npm run lint`    | Run ESLint over the project                                              |

## Project Structure

```
.
├── index.html               # HTML entry point (mounts #root)
├── public/
│   └── vite.svg             # Static Vite logo (served at /vite.svg)
├── src/
│   ├── main.tsx             # React bootstrap / entry point
│   ├── App.tsx              # Root component (currently the Vite counter demo)
│   ├── App.css              # Styles for App
│   ├── index.css            # Global styles
│   └── assets/
│       └── react.svg        # React logo asset
├── vite.config.ts           # Vite configuration (React plugin)
├── tsconfig.json            # TS project references (app + node)
├── tsconfig.app.json        # TypeScript config for the app code
├── tsconfig.node.json       # TypeScript config for tooling/config files
├── eslint.config.js         # ESLint flat config
└── package.json
```

## TypeScript Configuration

The project uses TypeScript [project references](https://www.typescriptlang.org/docs/handbook/project-references.html) via the root `tsconfig.json`:

- `tsconfig.app.json` — settings for the application source (`src/`)
- `tsconfig.node.json` — settings for Node-side tooling (e.g. `vite.config.ts`)

The `build` script runs `tsc -b` (build mode) before Vite bundles the app, so type errors fail the build.

## Linting

ESLint is configured using the flat config format (`eslint.config.js`) and includes:

- `@eslint/js` recommended rules
- `typescript-eslint` recommended rules
- `eslint-plugin-react-hooks` recommended rules
- `eslint-plugin-react-refresh` (warns on exports that would break Fast Refresh)

Run it with:

```bash
npm run lint
```

## Building for Production

```bash
npm run build
```

The output is emitted to `dist/`. Preview it locally with:

```bash
npm run preview
```

Deploy the contents of `dist/` to any static host (e.g. Netlify, Vercel, GitHub Pages).

## License

_Add a license here if applicable — the project does not currently specify one._
