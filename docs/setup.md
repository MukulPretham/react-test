# Setup

This guide walks through everything you need to get `react-test` running on your machine, from prerequisites to building for production.

## Prerequisites

- **[Node.js](https://nodejs.org/)** 18+ (or a version compatible with Vite 6)
- A package manager — **npm** is used in this guide, but `yarn`/`pnpm`/`bun` work too.

Verify your installation:

```bash
node --version
npm --version
```

## 1. Install dependencies

From the repository root, install the project dependencies:

```bash
npm install
```

This installs everything listed in `package.json`:

- **Dependencies** — `react` and `react-dom` (v19)
- **Dev dependencies** — TypeScript, Vite, `@vitejs/plugin-react`, ESLint and its plugins, and the React type definitions

## 2. Run the dev server

```bash
npm run dev
```

Vite starts a local dev server (usually at `http://localhost:5173`). Open that URL in your browser. With Hot Module Replacement enabled, edits to `src/App.tsx` (or any imported module) are applied instantly without a full page reload.

## 3. Lint the code

```bash
npm run lint
```

Runs ESLint (with the flat config in `eslint.config.js`) over the TypeScript/TSX source files. The `dist/` output folder is ignored.

## 4. Build for production

```bash
npm run build
```

This runs two commands in sequence:

1. `tsc -b` — type-checks the project and builds the TypeScript references.
2. `vite build` — bundles the app and emits production-optimized assets to `dist/`.

Because TypeScript runs in strict mode (plus `noUnusedLocals`, `noUnusedParameters`, etc.), any type errors will fail the build.

## 5. Preview the production build

```bash
npm run preview
```

Serves the `dist/` folder locally so you can verify the production bundle before deploying.

## Project configuration files

| File                | Purpose                                                            |
| ------------------- | ------------------------------------------------------------------ |
| `vite.config.ts`     | Vite configuration — enables the React plugin (`@vitejs/plugin-react`) |
| `tsconfig.json`      | Root TS config — wires together the app and node project references |
| `tsconfig.app.json`  | TS config for `src/` — strict mode, bundler module resolution, JSX |
| `tsconfig.node.json` | TS config for the Node-side tooling (e.g. Vite config)             |
| `eslint.config.js`   | ESLint flat config — `typescript-eslint`, `react-hooks`, `react-refresh` |
| `index.html`         | HTML entry — mounts `#root` and loads `/src/main.tsx`               |

## Troubleshooting

- **Port already in use** — Vite will automatically pick a different port; otherwise, use `--port` to set one explicitly.
- **Build fails with type errors** — the project uses strict TypeScript. Fix the reported type issues in `src/` and re-run `npm run build`.
- **Dependencies out of date** — run `npm update` or re-install with `npm install` if you switch branches/versions.

## Next steps

See [intro.md](./intro.md) for an overview of the project structure, or continue into the code by editing `src/App.tsx`.