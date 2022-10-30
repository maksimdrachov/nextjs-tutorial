## Next.js Tutorial

[SOURCE](https://www.youtube.com/watch?v=9P8mASSREYM&list=PLC3y8-rFHvwgC9mj0qv972IO5DmD-H0ZH)

### 1 - Introduction

1. File based routing
2. Pre-rendering
3. API routes
4. Support for CSS modules
5. Authentication
6. Dev and Prod build system

Pre-requisites

- HTML, CSS and JavaScript Fundamentals
- ES6 + features
- React Fundamentals

### 2 - Hello World

To create a project:

```
npx create-next-app 2-hello-world
```

To run:

```bash
yarn dev
# or: npm run dev
```

### 3 - Project Structure

- `package.json`: contains dependencies and scripts required for the project
  - scripts:
    - dev: script runs our nextjs app in development mode
    - build: compiles our nextjs app and prepares for production 
    - start: starts compiled app in production mode
    - lint: lints all the files

```json
{
  "name": "2-hello-world",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  },
  "dependencies": {
    "next": "13.0.0",
    "react": "18.2.0",
    "react-dom": "18.2.0"
  },
  "devDependencies": {
    "eslint": "8.26.0",
    "eslint-config-next": "13.0.0"
  }
}
```

- `yarn.lock`/`package-lock.json`: ensure consistent installation of dependencies

- `next.config.js`: nextjs configuration file
  - `reactStrictMode`: development mode feature to highlight potential issues

```js
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  swcMinify: true,
}

module.exports = nextConfig
```

- `.eslintrc.json`: configuration file for linter

```
{
  "extends": "next/core-web-vitals"
}
```

#### Folders

- `.next`: generated when we run `dev` or `build`, from this folder serves the web app

- `node_modules`: all the dependencies are installed here

- `styles`: css files

- `public`: all the public resources for our application: icons, images,...

- `pages`: routing
  - `index.js`: gets served as first page
  - `_app.js`: define layout
  - `api`

#### Control flow

`run dev` -> `_app.js` which contains `MyApp`

```js
function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />
}
```

When we go to home, `Component` is refering to `Home` (from `index.js`)

```
export default function Home() {
  return (
```

### 4 - Routing Section Intro


