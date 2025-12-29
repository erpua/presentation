# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

# Running and more
- npm run dev ( check up )
- npm install tailwindcss @tailwindcss/vite
- in vite.config.js file change to :

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'


// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
})

- in index.css import tailwind css: 
@import "tailwindcss";
- delete App.css

- update vite.config.js file:

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'
import path from "path"


// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    }
  }
})

- npm install lucide-react ( icon library )
- npm install react-router-dom
- npm install tailwind-merge ( allows us to create a util function, 
  that will allow to combine class names in tailwind, 
  to not write the full class name without knowing which one exists and which are not ).
- npm install @radix-ui/react-toast
- npm install class-variance-authority
- npm install clsx
- npm run dev

# Create and add to GitHub
- ( https://www.google.com/search?q=how+to+create+git+in+project+and+push+to+github&rlz=1C1OZZY_enMX1133MX1133&oq=how+to+create+git+in+project+and+push+&gs_lcrp=EgZjaHJvbWUqBwgCECEYoAEyBggAEEUYOTIHCAEQIRigATIHCAIQIRigATIHCAMQIRigATIHCAQQIRifBTIHCAUQIRiPAjIHCAYQIRiPAtIBCTEzNjM3ajBqN6gCCLACAfEF6JCLjyT6WKjxBeiQi48k-lio&sourceid=chrome&ie=UTF-8 )
- Navigate to your project's root directory in the terminal: cd path/to/your/project
- Initialize a new Git repository: This creates a hidden .git folder in your project directory: git init
- Stage all the files in your project for the first commit. It's also a good practice to create a .gitignore file first to exclude unnecessary or sensitive files (like node_modules/ or .env files): git add .
- Commit the staged files with a descriptive message: git commit -m "Initial project commit"
- Create a new repository on GitHub.com (do not initialize it with a README, license, or .gitignore file, as this can cause merge conflicts later).
- Copy the remote repository URL from GitHub's "Quick Setup" page (either HTTPS or SSH, depending on your setup).
- Link your local repository to the remote GitHub repository (replace <REMOTE_URL> with the URL you copied):
git remote add origin <REMOTE_URL> => git remote add origin https://github.com/erpua/presentation.git
- Verify the remote URL has been added correctly: git remote -v
- git push -u origin master