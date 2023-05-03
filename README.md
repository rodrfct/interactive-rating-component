# Frontend Mentor - Interactive rating component solution

This is a solution to the [Interactive rating component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)


## Overview

### The challenge

Users should be able to:

- [x] View the optimal layout for the app depending on their device's screen size
- [x] See hover states for all interactive elements on the page
- [x] Select and submit a number rating
- [x] See the "Thank you" card state after submitting a rating


### Links

- Solution URL: [My Solution](https://www.frontendmentor.io/solutions/interactive-rating-component-with-vuejs-Z7sJyhgFeN)
- Live Site URL: [My Live Site](https://rodrfct.github.io/interactive-rating-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- CSS Grid
- [Vue](https://vuejs.org/) - JS library



### What I learned

I started this challenge as a starting point for learning Vue after watching [John Komarnicki's 3h long tutorial](https://www.youtube.com/watch?v=KTFH4P8unUQ). In completing it, I think I have laid down in my mind the basics of Vue. Additionally I have learned a bit of CSS.

```css
/*I used this to center the card on screen */
.card {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

/*I learned about the attr() function,
this has been (and will be) very useful */
.rating-input::before {
    content: attr(value);
}
```

And I think got more confortable and efficient with it


### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.


### Useful resources

- [ChatGPT](https://chat.openai.com/) - I know, I know. Don't worry, I made a responsible use of it. It tought me the bits I mentioned [earlier](#what-i-learned). But I found it is not **as good** as I thought (at least 3.5), anyway, very good resource, totally recomended (privacy issues and potentially destroying my future job aside).
- [MDN](https://developer.mozilla.org/) - Amazing resource as always. Provides in-depth information about every HTML tag, every CSS property and every JS API.

