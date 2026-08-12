# Introduction

A short overview of the `react-test` repository: what it is, what it's for, and how the pieces fit together.

## What is this project?

`react-test` is a minimal front-end starter project built with **React**, **TypeScript**, and **Vite**. It was bootstrapped from the official Vite React-TS template and currently contains no application-specific logic — just the default counter demo that ships with the template.

It's intended to be a clean, modern starting point for building a React application, with fast hot module replacement during development and strict type checking to catch errors early.

## Why Vite + React + TypeScript?

- **Vite** provides an instant dev server with HMR and optimized production builds.
- **React** is the UI library used to build the components.
- **TypeScript** adds static type checking on top of JavaScript, configured here in strict mode.

This combination gives a fast, type-safe development experience out of the box.

## How the pieces fit together

1. The app is served from `index.html`, which has a `<div id="root">` and loads `/src/main.tsx` as a module script.
2. `src/main.tsx` is the entry point: it imports the global styles and renders `<App />` (wrapped in React's `<StrictMode>`) into the `#root` element.
3. `src/App.tsx` is the root component. It currently renders the starter demo — the Vite and React logos and a clickable counter that uses React's `useState` hook.
4. Vite is configured in `vite.config.ts`, which only enables the React plugin. TypeScript configuration is split across `tsconfig.json` (references), `tsconfig.app.json` (app code), and `tsconfig.node.json` (Vite config side).
5. ESLint (`eslint.config.js`) enforces code quality via `typescript-eslint`, the `react-hooks` rules, and the `react-refresh` component-export rule.

## What's included

- ✅ React 19 with Strict Mode
- ✅ TypeScript ~5.7 in strict mode
- ✅ Vite 6 dev server and build tooling
- ✅ ESLint 9 flat config

See [README.md](../README.md) for the quick start, and [setup.md](./setup.md) for a detailed setup walkthrough.

### Next steps

The project is a blank slate. To start building, edit `src/App.tsx` (and add new components under `src/`) to replace the starter demo with your own UI.