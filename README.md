# Nuxt 3 / Tailwind starter

Set up a Nuxt application via the [nuxt 3 documentation](https://v3.nuxtjs.org).

## Setup

cd to the application's root folder

Fork this repo.

Install the dependencies:

```bash
# yarn
yarn install

or

# npm
npm install

or

# pnpm
pnpm install --shamefully-hoist
```

## Development Server

Start the development server on http://localhost:3000

```bash
npm run dev

or

yarn dev
```

Or just add/update the following files in your code as follows:

/assets/css/main/css

```bash
@tailwind base;
@tailwind components;
@tailwind utilities;
```

nuxt.config.js

```bash
export default defineNuxtConfig({
  css: ["@/assets/css/main.css"], //make sure this file exists or matches what you currently have
  build: {
    postcss: {
      postcssOptions: require("./postcss.config.js"),
    },
  },
});
```

package.json

```bash
  "devDependencies": {
    ...
    "autoprefixer": "^10.4.12",
    "postcss": "^8.4.18",
    "tailwindcss": "^3.2.0"
  }
```

postcss.config.js

```bash
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

tailwind.config.js

```bash
/** @type {import('tailwindcss').Config} */
module.exports = {
  mode: "jit",
  content: [
    "./assets/**/*.css",
    "./components/*.{vue,js}",
    "./components/**/*.{vue,js}",
    "./pages/*.vue",
    "./pages/**/*.vue",
    "./plugins/**/*.{js,ts}",
    "./*.{vue,js,ts}",
    "./nuxt.config.{js,ts}",
  ],
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
};
```
