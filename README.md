# React + TypeScript + Vite Boilerplate

This is a minimal boilerplate for a React application using TypeScript and Vite. It includes Hot Module Replacement (HMR), ESLint for linting, and a simple counter example to get started quickly.

## Features
- React 19 with TypeScript support
- Vite for fast development and builds
- ESLint configured for code quality
- Strict Mode enabled for development best practices
- Minimal example with a counter component

## Quick Start
1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```
4. Open your browser to `http://localhost:3000`

## Available Scripts
- `dev`: Starts the Vite development server
- `build`: Builds the app for production (outputs to `dist` folder)
- `lint`: Runs ESLint to check for code issues
- `preview`: Previews the production build locally

## Project Structure
```
react-test/
├── src/
│   ├── main.tsx       # Entry point with React root initialization
│   ├── App.tsx        # Main component with counter example
│   ├── App.css        # Component styles
│   └── index.css      # Global styles
├── public/            # Static assets
├── vite.config.ts     # Vite configuration
├── tsconfig.json      # TypeScript configuration
└── package.json       # Project dependencies and scripts
```

## Configuration
- **Vite**: Configured with `@vitejs/plugin-react` for React support
- **TypeScript**: Uses modular config (`tsconfig.app.json` and `tsconfig.node.json`)
- **ESLint**: Basic setup with potential for expansion (see original README for advanced config)

## Dependencies
- React 19
- Vite 6
- TypeScript 5.7
- ESLint 9

## Extending the Project
- Add more components in the `src` folder
- Configure additional ESLint rules as needed
- Customize Vite config for additional features

For advanced ESLint configuration, refer to the original README section on expanding ESLint rules.