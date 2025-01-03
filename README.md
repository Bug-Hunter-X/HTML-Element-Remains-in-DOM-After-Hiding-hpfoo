# HTML Element Remains in DOM After Hiding

This repository demonstrates an uncommon bug in HTML where an element, after having its `display` style set to `none` using JavaScript, might still persist in the Document Object Model (DOM). This can lead to unexpected behavior, especially when interacting with the element using JavaScript later.

The bug is demonstrated in `bug.html`. The solution which shows how to properly remove the element is in `bugSolution.html`.

## Bug Description

The code sets the `innerHTML` of a div to an empty string and then sets its `display` style to `none`.  While this hides the element visually, the element remains in the DOM, potentially causing issues with other JavaScript that depends on the element's absence.

## How to Reproduce

1. Open `bug.html` in your browser.
2. Click the button.
3. Inspect the page's DOM using your browser's developer tools.  Notice that the div element is still present, even though it's hidden.

## Solution

The ideal solution depends on the intended outcome.  If you want to completely remove the element from the DOM, use `remove()` instead of setting `display` to `none`.