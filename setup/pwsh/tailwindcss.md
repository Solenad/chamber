# TailwindCSS Current Setup

TailwindCSS v4.0 is ass rn, kindly use this setup:

Date: 2025-01-09

---

1.

```bash
npm install -d tailwindcss@3.4.17
```

2.

```bash
npm install postcss autoprefixer
```

3.

```bash
npx tailwindcss init
```

4. access `tailwind.config.js` and edit `content`

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

5. access `index.css` or any primary/root .css file and add:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
