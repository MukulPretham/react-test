# API Reference

This project is a frontend-only React application built with Vite. It has **no backend API**, **no REST/graph endpoints**, and **no server-side code**. The only "API" exposed to developers is the React component tree and the TypeScript types used by the build tooling.

This document describes the public surface of the application code, the entry points, and the configuration that affects how modules are compiled and served.

## Application Entry Points

### HTML Entry: `index.html`

The Vite dev server and build treat `index.html` as the app entry. Key details:

- `lang="en"`
- Title: **Vite + React + TS**
- Favicon: `/vite.svg`
- Mounts the React app at the element with `id="root"`
- Loads the module script `/src/main.tsx`

### React Bootstrap: `src/main.tsx`

```ts
createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <App />
  </StrictMode>,
)
```

- Mounts the `<App />` component into the `#root` DOM node
- Wraps the tree in React's `<StrictMode>` for extra development checks
- Imports the global stylesheet `./index.css`

## Components

### `App` (in `src/App.tsx`)

The root React component currently contains the default Vite starter counter demo.

- Exported as the default export
- Renders the Vite and React logos, a heading, and an interactive counter button
- Uses the local `useState(0)` hook to track a `count` value
- Imports `./App.css` for styles

> **Costume** (replace as needed): This component is a placeholder. Swap its contents for your application's real UI.

## Configuration Reference

These files are not runtime APIs but define how the app is compiled, linted, and served.

### `vite.config.ts`

- Uses the `@vitejs/plugin-react` plugin (Babel-based Fast Refresh)
- No custom server, build, or alias options — all defaults apply

### `tsconfig.json`

Root config that only wires up project references:

- `tsconfig.app.json` — settings for the application code under `src/`
- `tsconfig.node.json` — settings for Node-side tooling (e.g. `vite.config.ts`)

### `eslint.config.js`

Flat config with:

- `@eslint/js` recommended rules
- `typescript-eslint` recommended rules
- `eslint-plugin-react-hooks` recommended rules
- `eslint-plugin-react-refresh` (warns on exports that break Fast Refresh)

## Scripts / Commands

These are the npm scripts defined in `package.json`:

| Command             | Description                                              |
| ------------------- | -------------------------------------------------------- |
| `npm run dev`       | Start the Vite dev server with HMR                       |
| `npm run build`     | Type-check with `tsc -b`, then run `vite build`          |
| `npm run preview`   | Preview the production build from `dist/` locally        |
| `npm run lint`      | Run ESLint over the project                              |

## Environment / Globals

- **No runtime API calls** — the app performs no `fetch`/`axios` requests and has no API key or endpoint configuration.
- **No environment variables** — no `.env` support or `import.meta.env` usage in the current code.

## TypeScript Build Modes

The `tsc -b` build-mode compilation is a public, externally visible "interface" in the sense that it surfaces type errors. The project uses [project references](https://www.typescriptlang.org/docs/handbook/project-references.html), so both referenced configs must compile successfully for `npm run build` to pass.