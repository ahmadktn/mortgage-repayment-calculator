# Frontend Mentor - Mortgage repayment calculator solution

This is a solution to the [Mortgage repayment calculator challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/mortgage-repayment-calculator-Galx1LXK73). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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

- Input mortgage information and see monthly repayment and total repayment amounts after submitting the form
- See form validation messages if any field is incomplete
- Complete the form only using their keyboard
- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

![](screenshot.png)
<img src="screenshot.png" />
### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [https://mortgage-repayment-calculator-zeta.vercel.app/](https://mortgage-repayment-calculator-zeta.vercel.app/)

## My process

### Built with

- Semantic HTML5 markup
- Flexbox
- Mobile-first workflow
- [Vue js](https://vuejs.org/) - JS library

### What I learned

This is my second project using the Vue 3 and the composition api. It's an opportunity to practice my skill using this challange. I was able to make use of what I've learnt such as components, forms, emits and props to complete the project. I started learning Vue js using the Options API, and I make use of this opportunity to transition to Composition API which provides a more readable way of writing Vue code. I learned the new way of using props with the Composition API, and the use of script setup and ref for reactivity
```js
<script setup>
import { ref } from 'vue';

defineProps();

const var = ref();
</script>
```

### Continued development

I will pay extra attention to emits and slots. Also, I will learn and understand how to use watchers, mixings, and managing states in Vue js

### Useful resources

- [Vue js official documentation](https://vuejs.org/guide)

## Author

- Frontend Mentor - [@ahmadktn](https://www.frontendmentor.io/profile/ahmadktn)
