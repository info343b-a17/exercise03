# Problem 2

In this exercise, you'll practice styling a page using the **Bootstrap** CSS framework, and its responsive grid system in particular..

To complete the exercise, you will need to add structural content (e.g., `div` elements) and utility classes to the included `index.html` file so that it has has the following responsive appearance:

- On extra-small screens (less than `598px` in width):

    ![Example of completed exercise on extra-small screen](img/example-xs-preview.png)

- On small screens (more than `598px` in width), the images move to the sides of the text:

    ![Example of completed exercise on small screen](img/example-sm-preview.png)

- On medium and large screens (more than `768px` in width), the cards arrange into a 2x2 grid:

    ![Example of completed exercise on large screen](img/example-lg-preview.png)

- On extra-large screens (more than `1200px` in width), the cards line up in a single row, with the images back on top:

    ![Example of completed exercise on extra-large screen](img/example-xl-preview.png)

Instructions for achieving this appearance are detailed below:

1. Start by including a `<link>` to the Boostrap 4 CSS framework in the document's `<head>`. This should add some simple font styling to the page.

    - You'll also need to add a `viewport` meta element, as in the previous responsive exercise.

2. Both the `header` content and the `main` content should be inside of Bootstrap [containers](https://getbootstrap.com/docs/4.0/layout/overview/#containers) to give them appropriate padding. Note that this step (and the entire exercise) may require you to "wrap" groups of elements into `div`s.

3. The header should be a [Jumbotron](https://getbootstrap.com/docs/4.0/components/jumbotron/) component.

    - The "subtitle" should be stand out as a [lead](https://getbootstrap.com/docs/4.0/content/typography/#lead)

    - Note that you will need to utilize the appropriate jumobotron classes to make the background "full-width" (while the text is inside a `container` so has spacing on the sides).

    - The header jumbotron should be [colored](https://getbootstrap.com/docs/4.0/utilities/colors/) with a "dark" background and "white" text.

4. Each of the "cards" indicated in the HTML should be styled as a [Card](https://getbootstrap.com/docs/4.0/components/card/) component. Yes, this means you will need to make the same set of changes 4 times... consider it practice!

    - Each card's content should be have [appropriate padding](https://getbootstrap.com/docs/4.0/components/card/#blocks).

    - Use the `.card-title` and `.card-text` classes to style the card's title and text respectively. Note that the image is **not** a "card image" (at the top of the card), but rather should be content that is included in the card's "body".

    - The "Play" links should be styled as [dark-colored buttons](https://getbootstrap.com/docs/4.0/components/buttons/) (but they should remain links!)

    - Use a [utility class](https://getbootstrap.com/docs/4.0/utilities/spacing/) to give the `<img>` elements _bottom padding_ equal to the "spacer" size (a spacing size of `3`).

    - Also give each _`.card`_ 1.5 "spacers" worth of _bottom margin_ (a spacing size of `4`). This will put space between the cards.

5. By default the cards will be lined up in a 1x4 stack. However, on larger devices they should be arranged in a 2x2 or 4x1 grid. To support this, place each of the cards into a single `.row` of a Bootstrap [Grid](https://getbootstrap.com/docs/4.0/layout/grid/).

    - On _medium_ or larger screens, each card should take up 1/2 of the row (e.g., 6 "columns"). On _extra-large_ or larger screens, each card should take up 1/4 of the row.

    - Important: think about each "card" as being the _content_ of the grid column, rather than the grid column _also_ being a card. That is, each grid column should _contain_ a "card" as a child element. 

    - You can make each card the same "height" on larger displays by make each grid column it's own [flexbox container](https://getbootstrap.com/docs/4.0/utilities/flex/) (e.g., via a utility class that gives the `display:flex` property). This will cause the content (the `.card`) to "fill" the parent element (which is the `.row`!)

6. When there is sufficient room (e.g., on _small_, _medium_, or _large_ displays), the image icon should sit to the left side of the text. The easiest way to do this to make the **body of the card** into _another_ grid! Then you can use the responsive sizing utilities to put the image into a different "column" than the rest of the content!

    - _For each card_, you will need to wrap the card's body content inside of another `.row` (think about the card body as having a grid inside of it). This row should have two child "columns": one containing the `<img>`, and one containing the rest of the content.

    - On _small_ or larger displays, the image column should have an `auto` calculated width, and the text column should have a width that takes up the remaining space.

    Note that this will cause the card content to be in "columns" on small or larger devices... but on extra-large displays the overall `container` sizing means that each card isn't large enough for them to be in columns, so they will go back to stacking as desired!

## Testing
This exercise includes a test suite to verify that the outputted web page looks as expected. Note that this uses pixel-based image comparison, so may not fully reflect your solution's accuracy. _This test suite has been tested on Mac machines_.

If you haven't already, you will need to install an additional library called [Puppeteer](https://github.com/GoogleChrome/puppeteer). Note that this it will download a recent version of Chromium (~71Mb Mac, ~90Mb Linux, ~110Mb Win)

```bash
# install globally so only needed once
npm install -g puppeteer

# make available to this project
npm link puppeteer
```

You can then run the test suite with. Note that it can take up to **1 minute** for this suite to run completely.

```bash
jest problem2
```
