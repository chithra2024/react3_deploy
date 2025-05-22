npm create vite@latest my-react-app -- --template react
cd my-react-app
npm install
npm run dev
npm run build
npm run preview

# to deploy to github pages
npm install  gh-pages

# vite.config.js:

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vite.dev/config/
export default defineConfig({
  plugins: [react()],
  base: "/react3_deploy",   // add repo name
})

# package.json

{
  "name": "my-react-app",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "homepage": "https://chithra2024.github.io/react3_deploy",  // add home page
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint .",
    "preview": "vite preview",
    "predeploy":"npm run build",    // add predeploy
    "deploy": "gh-pages -d dist"    // add deploy

  },
  "dependencies": {
    "gh-pages": "^6.3.0",
    "react": "^19.1.0",
    "react-dom": "^19.1.0"
  },
  "devDependencies": {
    "@eslint/js": "^9.25.0",
    "@types/react": "^19.1.2",
    "@types/react-dom": "^19.1.2",
    "@vitejs/plugin-react": "^4.4.1",
    "eslint": "^9.25.0",
    "eslint-plugin-react-hooks": "^5.2.0",
    "eslint-plugin-react-refresh": "^0.4.19",
    "globals": "^16.0.0",
    "vite": "^6.3.5"
  }
}


# push your code to github

cd your-react-app-folder
git init
git remote add origin https://github.com/yourusername/my-react-app.git
git add .
git commit -m "Initial commit"
git branch -M main
git push -u origin main

# run deployment

npm run deploy

# this will create a branch and host in github



# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
