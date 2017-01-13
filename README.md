# WebsiteOptimization

## Optimizations in index.html

The next points were implemented to achieve a score of at least 90/100:

1. The style.css is inline in the html file.
2. print.css is deferred by using `media=print`.
3. JavaScript is at the bottom of the <body> section.
4. Where appropriate, `async` is used to load JavaScript files.
5. Google font is loaded asynchronously as described in this [blog](https://www.lockedowndesign.com/load-google-fonts-asynchronously-for-page-speed/).
6. The profilepic.jpeg is compressed.
7. The html file is minified.

The score achieved in PageSpeed is 96/100 for mobile and 97/100 for desktop.


## Optimizations in main.js

The changes needed to get 60 fps are:

1. The `updatePosition` function is simpler and avoids forced synchronous layout.
2. The `updateScroll` function is implemented to control requestAnimationFrame.
3. The number of pizzas (before 200) is determined with the screen height to avoid creating unnecessary pizzas.

The changes needed to resize pizzas under 5 ms are:

1. The function `changePizzaSizes` absorbed the work of the `determineDx` function.
2. `document.querySelectorAll` is computed just one time.
3. To avoid forced synchronous layout, the size of the pizzas is changed by percentage. 