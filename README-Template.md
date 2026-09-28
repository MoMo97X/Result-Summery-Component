# Frontend Mentor - Results summary component solution

This is a solution to the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contentsgit

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)
- [Acknowledgments](#acknowledgments)
  

---

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page
- **Bonus**: Use the local JSON data to dynamically populate the content

### Screenshot

![](/preview.jpg)

### Links

- Solution URL: [GitHub Repository](https://your-solution-url.com](https://github.com/MoMo97X/Result-Summery-Component)
- Live Site URL: [GitHub Pages]([https://your-live-site-url.com](https://momo97x.github.io/Result-Summery-Component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties (Variables)
- Flexbox
- CSS Grid
- Modern fluid sizing (`clamp()`, `min()`)
- Mobile-first workflow

### What I learned

#### 1. Semantic HTML5 Architecture & Accessibility
To ensure screen readers parse the document cleanly, I structured the component into two logical sections inside a main `<article>` element. I used `aria-hidden="true"` on decorative category icons so screen readers focus strictly on functional text, and structured the scores in an unordered list (`<ul>`) for intuitive navigation:

```html
<li class="summary-item item-reaction">
  <div class="category-info">
    <img src="./assets/images/icon-reaction.svg" alt="" aria-hidden="true" />
    <span class="category-name">Reaction</span>
  </div>
  <p class="category-score">
    <span class="score-obtained">80</span> / 100
  </p>
</li>
```

#### 2. Resolving Intermediate Breakpoint Stretching with CSS clamp()
While testing intermediate viewport widths (between 375px and 900px), the component stretched awkwardly before collapsing. I resolved this by decoupling structural layout direction changes from fluid width scaling:

Used explicit media queries for flex-direction switching at 650px.

Applied clamp() to control the card container's growth smoothly without breaking smaller screens.

```
.card-container {
  width: clamp(21.5rem, 90vw, 43.75rem);
  display: flex;
  flex-direction: column;
  margin-inline: auto;
}

@media (min-width: 650px) {
  .card-container {
    flex-direction: row;
  }
}
```

### Continued development

- Refining multi-column CSS Grid strategies for complex dashboard interfaces.
- Integrating programmatic LLM extensions in VS Code (like Continue.dev and Cursor) for faster visual refactoring.
- Dynamic data fetching using local JSON files and JavaScript to render category scores programmatically.

### Useful resources

- MDN Web Docs: clamp() - Essential reference for understanding boundary limits and dynamic scaling calculations.
- A Complete Guide to Flexbox (CSS-Tricks) - Useful reference for aligning internal elements and handling layout direction changes.

### AI Collaboration

I used Gemini as an AI pair-programmer throughout this project:

- Git Workflow & Debugging: Resolved remote push rejections (git pull --rebase), configured project .gitignore, and           established conventional commit guidelines.
- Responsive Layout Analysis: Analyzed screen recording captures to identify why clamp() logic was pinning container widths   and causing intermediate breakpoint stretching.
- Accessibility & SEO: Implemented WCAG screen reader standards (aria-hidden, semantic list tags) and configured absolute     og:image tags for social media cards.

## Author

- Website - [@MoMo97X](https://www.your-site.com)
- Frontend Mentor - [@MuhammedArrujbani](https://www.frontendmentor.io/profile/yourusername)


## Acknowledgments

Thanks to the Frontend Mentor community for providing realistic design specs that closely mirror professional front-end workflows.
