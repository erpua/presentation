# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

# Installations React / VITE
- npx create-vite ( => Vite => JavaScript )
- npm install ( to install all packages )
- npm run dev ( first running to check up )

# Installations TAILWIND CSS
- npm install tailwindcss @tailwindcss/vite ( @tailwindcss/vite = plugin )

# Configurations of TAILWIND CSS
- in vite.config.js file => import tailwind:

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

- add to plugins:
// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
})

# Adding tailwindcss to index.css file
- in index.css import tailwind css: 
@import "tailwindcss";

# Deleting extra files
- delete App.css

# update vite.config.js file ( add alieas for src folder )
- import path

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'
import path from "path"

- add alias with path to defineConfig
// https://vite.dev/config/
export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    }
  }
})

# importing all neccessary packages
- npm install lucide-react ( access to icon library )
- npm install react-router-dom ( going to make routing )
- npm install tailwind-merge ( allows us to create a util function, 
  that will allow to combine class names in tailwind, 
  to not write the full class name without knowing which one exists and which are not ).
- npm install @radix-ui/react-toast
- npm install class-variance-authority
- npm install clsx
- npm run dev

# Updating App.jsx for first run
- delete import "./App.css";
- delete all unneccesary code;

# Creating 2 pages to check routing
- in src folder create folder pages
- in pages create Home.jsx and NotFound.jsx
- add content / planning for the Home page and tailwind ( if it's working ):

export const Home = () => {
  return  (
    <div className="min-h-screen">
      <h1 className="text-blue-700">Home page</h1>
      {/* Theme Toggle */}

      {/* Background effects */}

      {/* Navbar */}

      {/* Main Content */}

      {/* Footer */}
    </div>
  )
 
}

- add content to NotFound:

export const NotFound = () => {
  return <div>The page you are looking for was NOT FOUND</div>
}

# Update App.jsx to see routing

import { BrowserRouter, Route, Routes } from "react-router-dom";
import { Home } from "./pages/Home";
import { NotFound } from "./pages/NotFound";

function App() {

  return (
    <>
      <BrowserRouter>
        <Routes>
          <Route index element={ <Home /> } />
          <Route path="*" element={ <NotFound />} />
        </Routes>
      </BrowserRouter>
    </>
  )
};

export default App;

# final checking
- in http://localhost:5173/ => must be blue content: "Home Page"
- in any other routings must be black content: "The page you are looking for was NOT FOUND"

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