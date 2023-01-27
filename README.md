# Frontend Mentor - FAQ accordion card solution

This is a solution to the [FAQ accordion card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/faq-accordion-card-XlyjD0Oam). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See hover states for all interactive elements on the page
- Hide/Show the answer to a question when the question is clicked

### Screenshot

Desktop 
![](./screenshots/FAQ%20Accordion%20Card%20-%20Desktop.png)

Mobile  
![](./screenshots/FAQ%20Accordion%20Card%20-%20Mobile.png)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- [Sass](sass-lang.com) - CSS Preprocessor

### What I learned

On this one I had to come up with a way to make layers to the illustrations. I chose to create the ``.inside`` and ``outside`` to identify those which would recieve the ``overflow: hidden`` property. I thought this was the best way to crop the part of the images that where beyond the limits of its container.

```html
<div class="illustration">
  <div class="inside">
    <picture>
      <source srcset="./images/illustration-woman-online-mobile.svg" media="(max-width: 600px)">
      <img class="woman" src="./images/illustration-woman-online-desktop.svg" alt="">
    </picture>
    <picture>
      <source srcset="./images/bg-pattern-mobile.svg" media="(max-width: 600px)">
      <img class="pattern" src="./images/bg-pattern-desktop.svg" alt="">
    </picture>
  </div>
  <div class="outside">
    <img class="box" src="./images/illustration-box-desktop.svg" alt="">
  </div>
</div>
```
I also learned about the ``~`` which can work as an conditional operator and ``transition`` and ``transform`` properties to animate the arrow when that question was selected.
```css
.question::after {
  content: url(./images/icon-arrow-down.svg);
  height: 1rem;
  position: absolute;
  top: 30%;
  right: 5%;
  transition: transform 0.5s;
}

input:checked ~ .question-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

input:checked ~ .question {
  font-weight: 700;
}

input:checked ~ .question::after {
  rotate: x 180deg;
}

input:checked ~ .answer {
  display: block;
}
```

### Continued development

I spent too much time on the images and I am not quite satisfied with the result. I intend to find a better way to work out their position and responsivity.

### Useful resources

- [Expand Collapse Section using only HTML & CSS [No JavaScript]🔥](https://www.youtube.com/watch?v=2cPKsxJcF9Y) - This video by [Frontend Guruji](https://www.youtube.com/@FrontendGuruji) helped me with the "toggle" css trick. It may help out you guys as well.

## Author

- GitHub - [Nicholas Albuquerque](https://www.github.com/nicoams)
- Frontend Mentor - [@nicoams](https://www.frontendmentor.io/profile/nicoams)