# Tailwind CSS

### Install

```
yarn init -y
```

```
yarn add postcss-cli autoprefixer tailwindcss
```

Create a file `postcss.config.js`

```js
module.exports = {
  plugins: [require("tailwindcss"), require("autoprefixer")]
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
```
@tailwind base;

@tailwind components;

@tailwind utilities;
```
Make sure you import "build.css" not index.css
