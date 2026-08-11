# Development

This document covers the day-to-day development workflow for `react-test` and how to extend its tooling.

## Dev Workflow

1. Install dependencies (first time only):

   ```bash
   npm install
   ```

2. Start the dev server:

   ```bash
   npm run dev
   ```

   Vite serves the app locally with Hot Module Replacement. Edits to files in `src/` (for example `src/App.tsx`) are reflected in the browser immediately without a full page reload.

3. The app is mounted from `src/main.tsx` into `#root` in `index.html`. The root component lives in `src/App.tsx`.

## Production Build

```bash
npm run build
```

This runs two steps:

1. `tsc -b` — type-checks the project using the TypeScript project references defined in `tsconfig.json` (which references `tsconfig.app.json` and `tsconfig.node.json`).
2. `vite build` — bundles the app for production into `dist/`.

If the type check or the build fails, the command exits with a non-zero status and no bundle is emitted.

## Previewing the Production Build

After a build, you can serve the `dist/` output locally:

```bash
npm run preview
```

This is useful to verify that the optimized production bundle behaves correctly before deploying.

## Linting

Run ESLint over the whole project:

```bash
npm run lint
```

The ESLint 9 flat configuration in `eslint.config.js` includes:

- `@eslint/js` recommended rules
- `typescript-eslint` recommended rules
- `eslint-plugin-react-hooks` rules
- `eslint-plugin-react-refresh` rules
- `globals` for browser/Node environment definitions

## Expanding the ESLint Configuration

The template ships with non-type-aware lint rules. If you are developing a production application, you can enable type-aware lint rules by updating `eslint.config.js`:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install `eslint-plugin-react-x` and `eslint-plugin-react-dom` for React-specific lint rules:

```bash
npm install --save-dev eslint-plugin-react-x eslint-plugin-react-dom
```

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```

## Adding Dependencies

Runtime dependencies (shipped to production):

```bash
npm install <package>
```

Development-only dependencies (tooling, types, etc.):

```bash
npm install --save-dev <package>
```