# Password Generator
##### Aim: To create a password generator that gives the user a random password on load

***

## Breakdown
1. First I created the JS code for it (saving the values to variables and logging it to console)
2. Next I created the basic HTML for it
3. Styled it up using CSS
4. Added Copy & Refresh buttons
5. Made the site mobile responsive

## The HTML
I wanted the site to be simple with no excess content.
- Created a heading of **"Password Generator"**
- Created a `<p>` in a `div` with `contenteditable` set to `true`
- Created two columns below, one with a button for **Copy** the other for **Refresh**
- Set the **Copy** buttons `onclick` event to call the `copyToClipboard` function
- Set the **Refresh** buttons `onclick` event to reload the page
- Added **Font Awesome**'s `script`
- Linked my `index.js` script

## The JavaScript
I'm sure there are many better methods to do it than the way I did, but here's what I did:
- Created an array called `characters` with a list of characters available in the password (all letters in the alphabet, all letters in the capitalized version, numbers and common symbols)
- Next I created a variable called `length` to get a random length of the password, a minimum of 8 characters. I used `Math.random()` rounded down times by 14, plus eight (for the minimum)
- I created an empty array called `password`
- Inside a `for` loop, using another `Math.random()` number set up to the length of the `characters` array, I pushed the character at the random numbers position into the empty `password` array I created earlier
- I had the `for` loop run until `i => length`
-  I created a variable called `strongPass` and using the `join` method, concactinated the `password` array into a string with no seperator
-  Using DOM I targeted the `<p>` element on the page where I wanted the generated password to display and set the `innerHTML` to the `strongPass` variable
-  Created a `copyToClipboard` function that writes to clipboard the `strongPass` variable, and displays an `alert` after doing so