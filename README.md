# React + TypeScript + Vite Starter

This repository provides a minimal yet powerful setup for building React applications with TypeScript and Vite. It includes configurations for development, linting, and production builds, ensuring a smooth workflow from start to finish.

## Features

- **React 19**: Latest version of React for building dynamic UIs.
- **TypeScript**: Strong typing for better code quality and maintainability.
- **Vite**: Blazing-fast build tool with Hot Module Replacement (HMR).
- **ESLint**: Pre-configured for linting with optional type-aware rules.
- **Minimal Dependencies**: Focused setup with only essential dependencies.

## Quick Start

1. **Clone the repository**:
   ```bash
   git clone https://github.com/MukulPretham/react-test.git
   cd react-test
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the development server**:
   ```bash
   npm run dev
   ```

4. **Open in browser**:
   Navigate to `http://localhost:5173` to see the app in action.

## Scripts

- `npm run dev`: Start the development server.
- `npm run build`: Build the application for production.
- `npm run lint`: Run ESLint to check for linting errors.
- `npm run preview`: Preview the production build locally.

## Project Structure

```
react-test/
├── src/
│   ├── App.tsx       # Main React component
│   ├── main.tsx      # Entry point for the app
│   ├── App.css       # Styles for the App component
│   └── assets/       # Static assets (e.g., logos)
├── vite.config.ts    # Vite configuration
├── tsconfig.json     # TypeScript configuration
└── package.json      # Project metadata and dependencies
```

## Configuration

### Vite

The `vite.config.ts` file is minimal, using the `@vitejs/plugin-react` plugin:
```typescript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
})
```

### TypeScript

The `tsconfig.json` references two additional configuration files:
- `tsconfig.app.json`: For the application.
- `tsconfig.node.json`: For Node.js-specific settings.

### ESLint

The project includes ESLint for linting. For stricter rules, update the ESLint configuration as described in the [README.md](./README.md#expanding-the-eslint-configuration).

## Customization

- **Add Dependencies**: Install additional packages as needed.
- **Extend ESLint**: Follow the guide in the README to enable type-aware linting or React-specific rules.

## License

This project is open-source and available under the MIT License.
