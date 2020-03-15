# Tailwind CSS

### Install

```
yarn init -y
```

```
yarn add postcss-cli autoprefixer tailwindcss
```

then add purgecss for prod mode
```
yarn add @fullhuman/postcss-purgecss -D
```



Create a file `postcss.config.js`

```js
const purgecss = require("@fullhuman/postcss-purgecss")({
  // Specify the paths to all of the template files in your project
  // ["./src/**/*.html", "./src/**/*.vue", "./src/**/*.jsx"] 
  content: ["./index.html"],

  // Include any special characters you're using in this regular expression
  defaultExtractor: content => content.match(/[\w-/:]+(?<!:)/g) || []
});

module.exports = {
  plugins: [
    require("tailwindcss"),
    require("autoprefixer"),
    ...(process.env.NODE_ENV === "production" ? [purgecss] : [])
  ]
};

```

create a file with

```
yarn tailwind init
```

It will have this content:

```js
module.exports = {
  theme: {
    extend: {}
  },
  variants: {},
  plugins: []
};
```

add this script to package.json build css

```
postcss index.css -o build.css
```

Add this to index.css
```css
@tailwind base;

@tailwind components;

@tailwind utilities;
```
Make sure you import "build.css" not index.css


test with
```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Button
</button>
```
