
React-tailwind practice project
===============================

**use this incase of global installation issue**
npx create-react-app@latest . --use-npm

**install tailwind css, postcss-cli & autoprefixer**
npm i -D tailwindcss postcss-cli autoprefixer

**generate tailwind config file**
npx tailwind init tailwind.js --full

**create postcss config file**
 touch postcss.config.js
 
 in that file:
    const tailwindcss = require('tailwindcss')
    module.exports = {
        plugins: [
            tailwindcss('./tailwind.js'),
            require('autoprefixer')
        ]
    }

**create assets folder and main.css & tailwind.css in src folder**

within tailwind.css add these imports
@import 'tailwindcss/base';
@import 'tailwindcss/components';
@import 'tailwindcss/utilities';

**in package.json add these scripts**
"build:css": "postcss src/assets/tailwind.css -o src/assets/main.css"
"watch:css": "postcss src/assets/tailwind.css -o src/assets/main.css"

"start": "npm run watch:css && react-scripts start"
"build": "npm run build:css && react-scripts build"

**run npm start**
