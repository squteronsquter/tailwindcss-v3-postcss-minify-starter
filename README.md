# How to install Tailwindcss with PostCSS

Create files and folders for your project

mkdir src dist

```
npm init -y

npm install -D tailwindcss postcss autoprefixer

npx tailwindcss init
```


## tailwind.config.js

```
module.exports = {
  content: ["./src/**/*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
## postcss.config.js

Create postcss.config.js

```
vim postcss.config.js
```

And edit it to read like this

```
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```

## package.json

```
{
  "name": "postcss_tailwindcss",
  "version": "1.0.0",
  "description": "",
  "main": "postcss.config.js",
  "dependencies": {
    "autoprefixer": "^10.4.1",
    "postcss": "^8.4.5",
    "tailwindcss": "^3.0.8"
  },
  "devDependencies": {},
  "scripts": {
    "dev": "npx tailwindcss -i src/input.css -o dist/build.css",
    "build": "npx tailwindcss -o dist/build.css --minify"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

## index.html

create index.html 

```
vim src/index.html
```
And edit it to read like this

```
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/dist/build.css" rel="stylesheet">
</head>
<body class="bg-[#1da1f2]">
  <h1 class="text-3xl font-bold text-lime-200">
    Hello world!
  </h1>
</body>
</html>

```
Create tailwind input.css file

```
vim src/input.css
```
Edit it to read like this

```
@tailwind base;
@tailwind components;
@tailwind utilities;

```

## file structure

```
~/Sites/postcss_tailwindcss   87s
❯ ls -la
total 104
drwxr-xr-x   10 gray  staff    320 31 Dec 12:22 .
drwxr-xr-x   11 gray  staff    352 31 Dec 10:27 ..
-rw-r--r--    1 gray  staff   2470 31 Dec 12:02 build.css
drwxr-xr-x    3 gray  staff     96 31 Dec 12:00 dist
drwxr-xr-x  102 gray  staff   3264 31 Dec 10:28 node_modules
-rw-r--r--    1 gray  staff  36076 31 Dec 10:28 package-lock.json
-rw-r--r--    1 gray  staff    382 31 Dec 10:36 package.json
-rw-r--r--    1 gray  staff     81 31 Dec 10:31 postcss.config.js
drwxr-xr-x    4 gray  staff    128 31 Dec 12:26 src
-rw-r--r--    1 gray  staff    100 31 Dec 10:33 tailwind.config.js
```

## run scripts

```
npm run dev

npm run build
```

## how to run these scripts with --watch flag?



