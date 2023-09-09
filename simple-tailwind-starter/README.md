# Simple Tailwind Starter Project

This is a boilerplate codebase to start basic website with Tailwind CSS. It uses Tailwind CLI. 

## Steps to Create Project
- Run `npm init -y` to create an npm project in the current directory you are in.
- Install tailwindcss by running `npm install -D tailwindcss`. The `-D` flag is to set `tailwindcss` as a dev dependency and not required for production.
- To create tailwind config file, execute `npx tailwindcss init`. This would create a tailwind.config.js file in the current project directory.
- To have `tailwindcss` look at or detect tailwind classes, we need to specific where should it look for. This is done by adding `"**/src/**/*.{html,js,ts,jsx,tsx}"` and `"public/**/*.{html,js,ts,jsx,tsx}"` in the `contents` array inside of `tailwind.config.js` file. It will look like this -
  ```js
  {
    // ...
    content: [
      "src/**/*.{html,js,ts,jsx,tsx}", 
      "public/**/*.{html,js,ts,jsx,tsx}"
    ],
    // ...
  }
  ```
- Create `tailwind.css` file inside the `src/styles` folder.
- Add below code snippet to the created file.
  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ``` 
- Create npm scripts now by adding `twbuild` and `twdev` in the `scripts` tag inside `package.json` file as shown below.
  ```js
  // ...
  "scripts": {
    // ...
    "twbuild": "tailwindcss -i ./src/styles/tailwind.css -o ./dist/css/tailwind.css",
    "twdev": "tailwindcss -i ./src/styles/tailwind.css -o ./dist/css/tailwind.css --watch"
    // ...
  },
  // ...
  ```
- Check if the setup works by executing `npm run twbuild`. It should create the `tailwind.css` file inside of `dist/css` as specified above (in package.json file).
- Create an `index.html` file and link the output to it using the `link` tag as shown below. 
  ```html
  <link rel="stylesheet" href="./dist/css/tailwind.css">
  ```
- Write some demo html code with tailwind classes to check if the setup really works. 
- Finally, open the `index.html` file with browser and __Voila__! ✨


## Credits
Thank you [@bradtraversy](https://github.com/bradtraversy) for creating a [detailed course on TailwindCSS](https://www.udemy.com/course/tailwind-from-scratch/)! The starter project you demonstrated in the course has inspired me to create one for myself. So, the credit is all yours! 🙏