# React Test

A minimal [React](https://react.dev) + [TypeScript](https://www.typescriptlang.org/) + [Vite](https://vite.dev) starter project bootstrapped from the official Vite template. It provides a lightweight base for prototyping React applications with fast hot module replacement (HMR) and linting for React Hooks and Fast Refresh.

## Features

- **Vite dev server** with fast hot module replacement (HMR)
- **React 19** with TypeScript type-checking
- **ESLint** configured for React Hooks and Fast Refresh
- **Production builds** that type-check then bundle with Vite

## Tech Stack

| Technology | Version |
|------------|---------|
| [React](https://react.dev) | ^19.0.0 |
| [React DOM](https://react.dev) | ^19.0.0 |
| [TypeScript](https://www.typescriptlang.org/) | ~5.7.2 |
| [Vite](https://vite.dev) | ^6.3.1 |
| [ESLint](https://eslint.org/) | ^9.22.0 |

## Prerequisites

- [Node.js](https://nodejs.org/) (v18 or later recommended)
- npm (bundled with Node) or your preferred package manager

## Getting Started

### Installation

```bash
# Clone the repository
git clone <repo-url>
cd react-test

# Install dependencies
npm install
```

### Start the dev server

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser. Edit `src/App.tsx` — the page updates instantly thanks to HMR.

### Build for production

```bash
npm run build
```

This runs type checking (`tsc -b`) followed by `vite build`, outputting the production bundle to `dist/`.

### Preview the production build

```bash
npm run preview
```

Serves the `dist/` folder locally so you can verify the production bundle before deploying.

### Lint

```bash
npm run lint
```

Runs ESLint over the whole project using the rules in `eslint.config.js`.

## Project Structure

```
react-test/
├── index.html              # HTML entry point
├── package.json            # Dependencies and scripts
├── vite.config.ts          # Vite config (uses the React plugin)
├── tsconfig.json           # Root TS config (project references)
├── tsconfig.app.json       # TS config for src/
├── tsconfig.node.json      # TS config for Vite / Node files
├── eslint.config.js        # ESLint flat config
├── public/
│   └── vite.svg            # Static asset served at /
└── src/
    ├── main.tsx            # App entry point (mounts App into #root)
    ├── App.tsx             # Main App component (counter demo)
    ├── App.css             # App component styles
    ├── index.css           # Global styles
    ├── assets/
    │   └── react.svg       # Imported asset used in App
    └── vite-env.d.ts       # Vite client type declarations
```

## Available Scripts

| Script    | Description                                        |
|-----------|----------------------------------------------------|
| `npm run dev`      | Start the Vite dev server with HMR       |
| `npm run build`    | Type-check (`tsc -b`) then build with Vite |
| `npm run lint`     | Lint all files with ESLint                |
| `npm run preview`  | Serve the production build locally        |

## License

This project is unlicensed — use it freely as a starting point for your own work.