# Tauri Svelte Tailwind Template

A template for creating a Tauri app with Svelte and Tailwind CSS.

I created this template because the obvious method of adding Tailwind CSS to a Tauri project with Svelte produces a confusing PostCSS "Unknown Word" error when the dev server is started.
The error goes away when the server refreshes, but it is still annoying. 
The method I used in this template seems to work consistently on my machine.

This template was made for my own use, but if you find it useful, feel free to use it.

The following steps were used to create this template:

1. Create a new Svelte project using:
```bash
npm create svelte@latest tauri-svelte-tailwind-template
```

2. Add Tailwind CSS to the project using:
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

3. Modify `tailwind.config.js` and add `src/app.css` and `src/routes/+layout.svelte` as follows according to [this guide](https://tailwindcss.com/docs/guides/sveltekit).

4. Add Tauri to the project using:
```bash
npm install -D @tauri-apps/cli@next
```

5. Initialize Tauri using:
```bash
npx tauri init
```
When prompted, specify `../src` as the directory containing the Web assets, and `http://localhost:5173` as the URL of the dev server.

6. Add `src/routes/+layout.ts` with the following contents:
```typescript
export const prerender = true;
export const ssr = false;
```

## Usage

To start developing, run:
```bash
npx tauri dev
```
