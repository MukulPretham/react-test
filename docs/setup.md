# Setup Guide

This guide walks through installing dependencies, running the project locally, and building for production.

## Prerequisites

- **Node.js** — v18+ recommended for Vite 6. Check your version:

  ```bash
  node -v
  ```

- **npm** — bundled with Node.js. Check your version:

  ```bash
  npm -v
  ```

## 1. Install Dependencies

From the repository root:

```bash
npm install
```

This installs all runtime and development dependencies listed in `package.json`.

## 2. Run the Dev Server (with HMR)

```bash
npm run dev
```

Vite starts a local development server with Hot Module Replacement enabled. Open the URL printed in the terminal (default: <http://localhost:5173>).

Changes to files under `src/` are reflected instantly in the browser.

## 3. Run the Linter

```bash
npm run lint
```

Runs ESLint over the project using the flat config in `eslint.config.js`.

## 4. Build for Production

```bash
npm run build
```

This runs two things in sequence:

1. `tsc -b` — type-checks the project using the TypeScript project references in `tsconfig.json`
2. `vite build` — bundles the app and emits static assets to `dist/`

If there are type errors, the build stops before Vite bundles anything.

## 5. Preview the Production Build

```bash
npm run preview
```

Serves the output of `dist/` so you can verify the production bundle locally before deploying.

## Troubleshooting

| Issue                                            | Suggested fix                                                     |
| ------------------------------------------------ | ----------------------------------------------------------------- |
| `npm install` fails or has peer dependency errors | Confirm you're on a supported Node version (`node -v`)            |
| Port `5173` is already in use                    | Let Vite pick another port, or pass `--port` to the `dev` script  |
| Build fails with type errors                     | Fix the reported errors, or run `npm run lint` to surface issues  |
| Stale `dist/` results                            | Re-run `npm run build` (Vite clears `dist/` by default)            |

## Environment

This project has no `.env` handling or environment-specific configuration. All runtime behavior is determined by the Vite config in `vite.config.ts`.