
# CSS Sprite-Based Flip Carousel Using Scroll-Timeline


This project is a pure CSS-based dynamic interactive book that simulates page-flipping animations using cutting-edge features available in modern Chrome (134–135+). It seamlessly combines several powerful CSS technologies to create a fully scrollable, sprite-driven animated experience resembling a book with turning pages.


## Demo

![Demo](https://github.com/troshkinpavel/CSS-Sprite-Based-Flip-Carousel/blob/main/demo.gif?raw=true)
https://codepen.io/Maseone/pen/WbbGxeO


## Documentation

```html
<style>
    :root {
        /* sprite image */
        --sprite-image: url(book.webp);

        /* ... */
    }

    .container {
        /* sprite columns */
        --sprite-c: 5;
        /* sprite image height */
        --sprite-h: 3000;
        /* sprite image width */
        --sprite-w: 9600;
        /* sprite frames */
        --sprite-f: 7;
        /* animation duration based on frame rate */
        --sprite-as: calc(var(--sprite-f) / var(--sprite-fr) * 1s);

        /* frame rows */
        --sprite-r: round(up, calc(var(--sprite-f) / var(--sprite-c)), 1);
        /* frame height */
        --sprite-sh: calc(var(--sprite-h) / var(--sprite-r));
        /* frame target height, width */
        --sprite-th: calc(var(--sprite-sh) / 2);

        /* aspect ratio */
        --sprite-ar: calc(var(--sprite-th) / var(--sprite-sh));
        --sprite-uh: calc(var(--sprite-h) * var(--sprite-ar));
        --sprite-uw: calc(var(--sprite-w) * var(--sprite-ar));

        /* frame width */
        --sprite-tw: calc(var(--sprite-uw) / var(--sprite-c));

        /* ... */
    }

    .sprite {
        /* ... */

        /* calculate the row and column position */
        --row: calc(round(down, calc(calc(var(--sprite-tw) * var(--sprite-fs-n)) / var(--sprite-uw)), 1) * var(--sprite-th));
        --col: mod(calc(var(--sprite-tw) * var(--sprite-fs-n)), var(--sprite-uw));
        
        background-position: calc(-1px * var(--col)) calc(-1px * var(--row));
    }
</style>
```

