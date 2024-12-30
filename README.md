# Uncommon HTML Bug: DOM Element Access Timing

This repository demonstrates a subtle bug related to accessing HTML DOM elements before the browser has finished rendering them.  The bug showcases the importance of proper timing when interacting with the Document Object Model (DOM) in JavaScript.

## Bug Description
The `bug.html` file contains a script that attempts to access and modify a DOM element immediately after the page loads.  This is problematic because the browser might not have fully parsed and rendered the HTML document yet.  If the target element doesn't exist at the time of access, this will lead to unexpected behavior.

## Solution
The solution (`bugSolution.html`) addresses this issue by using the `DOMContentLoaded` event listener. This ensures that the JavaScript code executes only after the HTML document has been fully parsed and the DOM is ready for manipulation.  This is a more robust approach, preventing the timing-related error and ensuring consistent behavior.

## How to Reproduce
1. Clone this repository.
2. Open `bug.html` in your web browser. Observe the expected output.
3. Open `bugSolution.html` in your web browser. Observe the improved behavior.

## Learning Points
* Always wait for the DOM to be fully ready before manipulating it with JavaScript.
* The `DOMContentLoaded` event is a reliable way to achieve this.
* Avoid race conditions between the browser's rendering and your JavaScript code.