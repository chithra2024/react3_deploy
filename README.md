npm create vite@latest my-react-app -- --template react
cd my-react-app
npm install
npm run dev
npm run build
npm run preview

cd your-react-app-folder
git init
git remote add origin https://github.com/yourusername/my-react-app.git
git add .
git commit -m "Initial commit"
git branch -M main
git push -u origin main


npm install --save gh-pages

Open package.json and add this line at the top level (replace yourusername and my-react-app):

{
  "name": "my-react-app",
  "version": "0.1.0",
  "private": true,
  "homepage": "https://yourusername.github.io/my-react-app",
  ...
}


in package.json

"scripts": {
  "start": "react-scripts start",
  "build": "react-scripts build",
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build",
  ...
}



# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
