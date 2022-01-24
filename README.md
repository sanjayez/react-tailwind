
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
&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;      const tailwindcss = require('tailwindcss')  
&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;      module.exports = {  
&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; plugins: [  
&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  tailwindcss('./tailwind.js'),  
&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp;  require('autoprefixer')  
&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;  &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;         ]  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;     }  
  
**create assets folder and main.css & tailwind.css in src folder**  
within tailwind.css add these imports  
- @import 'tailwindcss/base';  
- @import 'tailwindcss/components';  
- @import 'tailwindcss/utilities';  
  
**in package.json add these scripts**  
- "build:css": "postcss src/assets/tailwind.css -o src/assets/main.css"  
- "watch:css": "postcss src/assets/tailwind.css -o src/assets/main.css"  
- "start": "npm run watch:css && react-scripts start"  
- "build": "npm run build:css && react-scripts build"  

then execute **npm run start**
