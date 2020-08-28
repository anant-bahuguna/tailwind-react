# Setting Up ReactJs & TailwindCSS 🛠️

- `npx create-react-app react-tailwindcss && cd react-tailwindcss`

- `npm install tailwindcss postcss-cli autoprefixer -D`


- `npx tailwind init tailwind.js --full`
- `touch postcss.config.js`

- Add following lines of code to postcss.config.js
  ```
    const tailwindcss = require('tailwindcss');
    module.exports = {
        plugins: [
            tailwindcss('./tailwind.js'),
            require('autoprefixer')
        ],
    };
  ```
  
- Inside your `src` folder create a folder, name it `assets`, this is where all your styles would be stored. In that folder, create a `tailwind.css` file and `main.css` file respectively.

- Add following lines to tailwind.css
  ```
  @tailwind base;

  @tailwind components;

  @tailwind utilities;
  ```
  
- Add custom scripts in `package.json`
  ```
  "scripts": {
    "start": "npm run watch:css && react-scripts start",
    "build": "npm run build:css && react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "build:css": "postcss src/assets/tailwind.css -o src/assets/main.css", 
    "watch:css": "postcss src/assets/tailwind.css -o src/assets/main.css"
  },
  ```
  
- Import our `main.css` file and delete `import './index.css'`
  ```
  import './assets/main.css'
  ```
  
## React & Tailwind Setup Complete ✔️

[Source ℹ️](https://www.smashingmagazine.com/2020/02/tailwindcss-react-project/)
