# CSS Grids Lab/Drills - Part 1


## Walk-Through:

Write and style a sample `grid` layout to practice the applicable styling properties and develop a template to accommodate a few articles, by following these steps:


1. Write a CSS rule that applies to elements with a class of `layout` and give it the following properties to change the `display` property to a value of `grid` and the `background-color` to `grey`.

    ```css
    .layout {
      display: grid;
      background-color: grey;
    }
    ```

2. In HTML, create a `<main>` element with a class attribute of `layout`. *Test it, what do you see?*

    ```html
    <main class="layout"></main>
    ```

3. In CSS, define the rules for three elements we will create, to easily identify them from each other:

    ```css
    .first { background-color: tomato; }
    .second { background-color: lightgreen; }
    .third { background-color: dodgerblue; }
    ```

4. To the `.layout`, add a single `<article>` child element with sample content in it ("lorem ipsum" or just a few words to test) and give it a class of `first`. *What does our output look like?*

    ```html
    <article class="first">First!<article>
    ```

5. Add two more child `<article>` elements (with sample content) to the `<main>`, giving them classes of `second` and `third` respectively. *Note the way the elements are laid out by default, even though they are in a "grid".*

    ```html
    <article class="second">Second!<article>
    <article class="third">Third!<article>
    ```

6. To see how the `grid` differs from a standard `block` container in how it's elements move and size within it, give the `.layout` some dimension (and center the grid using `margin` - *same as centering a block!*):

    ```
    width: 50em;
    height: 30em;
    margin: 0 auto;
    ```

7. Without selecting the elements inside of the grid directly, we can split the `.layout` into three columns and have the items within adhere to the column pattern automatically by changing the grid template to a value of three measurements (fraction, in this case), which is how we create three columns. *Note the items automatically fall into the defined template pattern!*

    ```css
    grid-template-columns: 1fr 1fr 1fr;
    ```

8. All three items are in a single row because they fit the row's columns perfectly, but what happens if we scale back our `.layout`'s template to only two columns? Override the property from the previous step to show only two columns:

    ```css
    grid-template-columns: 1fr 1fr;
    ```

9. Change the column sizes to see how that affects the layout. To create columns that are split 60%/40%, try either of the following. Note with fractions, we could simply use `6fr 4fr` to mean 6/10 (60%) or 4/10 (40%), but we can also reduce those to their lowest common denominator, 3/5 and 2/5:

    ```css
    grid-template-columns: 60% 40%;
    ```
    #### OR
    
    ```css
    grid-template-columns: 3fr 2fr;
    ```

10. Add a fourth `<article>` to see where it lands within the layout.

    #### HTML
    ```html
    <article class="fourth">First!<article>
    ```

    #### CSS
    ```css
    .fourth { background-color: gold; }
    ```

11. Add some `grid-gap` to the `.layout` to see how the elements space out.

    ```css
    grid-gap: 1em;
    ```
    
12. Notice `grid-gap` add vertical and horizontal gap within the grid, but does not space the outside of the `.layout`. Also add `padding` (or `margin`, context dependant) to apply a "gap" around the grid that looks exactly like the gap inside the grid.

    ``` css
    padding: 1em;
    ```


## Your Turn:

Using your knowledge gained in the above walk-through, create a grid layout for a series of preview posts or articles for the homepage of a blogging website.

1. Fill the four `<article>` elements with better sample content to treat them like four actual article previews. To each, add: **an image** (wrapped in a `<header>`; if you don't have images handy, use [unsplash.com](http://unsplash.com) and save the files as something easy to recall, `1.jpeg`, `2.jpeg`, etc.), **a heading** (either an `<h1>` or `<h2>`), **a short paragraph or two**, and **an anchor** (`<a>`) that's styled to look like a button (`block`) that says "Read more" (wrapped in a `<footer>`).

2. Clean up the CSS to remove all references to the `grid`, including the templates and dimensions that were added to the `.layout`. When the viewport is compressed down to the minimum size (as small as 320px), the site should look like a mobile-friendly website.

3. Write a `@media` query to target a breakpoint at which you think the site would most comfortably be able to fit *two* columns. Add the appropriate CSS rules or changes to make it happen.

4. Write another `@media` query to target a breakpoint at which you think the site would most comfortably be able to fit *three* columns. Modify your CSS accordingly.

5. Set an upper limit to the width of the `.layout` in the final breakpoint (or a new one!). You can do so immediately using `width` or set a `max-width` to accomplish the same thing.
