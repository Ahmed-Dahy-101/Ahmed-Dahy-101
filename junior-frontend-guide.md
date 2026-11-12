# Junior Frontend Developer Guide

Welcome! This guide covers what to learn, how to work day to day, and how to grow. You don't need to master everything at once. Work through it in order and come back often.

---

## 1. Core Fundamentals

### HTML
- Use **semantic elements** (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<button>`) instead of `<div>` for everything.
- Every `<img>` needs an `alt` attribute.
- Every form input needs a `<label>`.
- Use one `<h1>` per page, and keep headings in order (h1 → h2 → h3).

### CSS
- Understand the **box model** (content, padding, border, margin) and set `box-sizing: border-box`.
- Learn **Flexbox** first (one-dimensional layouts), then **Grid** (two-dimensional layouts).
- Build **mobile-first**: write base styles for small screens, then add `min-width` media queries.
- Use **CSS variables** for colors, spacing, and fonts:

```css
:root {
  --color-primary: #2563eb;
  --space-2: 0.5rem;
}

.button {
  background: var(--color-primary);
  padding: var(--space-2) calc(var(--space-2) * 2);
}
```

- Prefer `rem` for font sizes and spacing, `%`/`fr` for layout, and `px` for borders and fine details.

### JavaScript
Make sure you are comfortable with:
- `const` / `let` (avoid `var`)
- Arrow functions, destructuring, spread/rest, template literals
- Array methods: `map`, `filter`, `find`, `reduce`, `some`, `every`
- Promises and `async` / `await`
- `fetch` and handling errors
- The DOM: selecting elements, events, event delegation
- Modules: `import` / `export`

```js
async function getUser(id) {
  try {
    const res = await fetch(`/api/users/${id}`);
    if (!res.ok) throw new Error(`Request failed: ${res.status}`);
    return await res.json();
  } catch (err) {
    console.error(err);
    return null;
  }
}
```

---

## 2. Essential Tools

| Tool | What it's for | Learn first |
|------|---------------|-------------|
| **Git** | Version control | `clone`, `branch`, `add`, `commit`, `push`, `pull`, `merge`, `rebase` |
| **Terminal** | Running commands | `cd`, `ls`, `mkdir`, `rm`, `cat` |
| **npm / pnpm / yarn** | Package management | `install`, `run`, `package.json` scripts |
| **VS Code** | Editor | Multi-cursor, search, debugger, extensions |
| **Browser DevTools** | Debugging | Elements, Console, Network, Performance tabs |
| **ESLint + Prettier** | Code quality and formatting | Run on save |

### Handy Git workflow

```bash
git checkout -b feature/login-form   # create a branch
git add .
git commit -m "Add login form validation"
git push -u origin feature/login-form
# then open a Pull Request
```

Write **small, focused commits** with clear messages.

---

## 3. A Framework (Pick One)

Learn vanilla JS well first, then pick **one** framework and go deep:

- **React**: the most jobs; learn components, props, state, `useEffect`, and custom hooks.
- **Vue**: gentle learning curve; learn the Composition API.
- **Svelte / Angular**: good choices depending on your team.

Concepts that transfer to any framework:
- Components and composition
- Props vs. state
- Lifting state up
- Conditional rendering and lists (with stable `key`s)
- Controlled forms
- Routing
- Data fetching and loading/error states

---

## 4. Daily Workflow

1. **Read the ticket carefully.** Ask questions before coding if anything is unclear.
2. **Pull the latest code** and create a branch.
3. **Build in small steps.** Get something working, then refine.
4. **Test it yourself**: different screen sizes, keyboard only, slow network.
5. **Self-review your diff** before asking for review.
6. **Open a PR** with a clear description and screenshots for UI changes.
7. **Respond to feedback** calmly. Review comments are about the code, not about you.

---

## 5. Best Practices Checklist

Before you open a pull request, check:

- [ ] Works on mobile, tablet, and desktop
- [ ] Usable with keyboard only (Tab, Enter, Esc)
- [ ] Sufficient color contrast
- [ ] Loading, empty, and error states handled
- [ ] No `console.log` leftovers
- [ ] No unused imports or dead code
- [ ] Meaningful variable and function names
- [ ] No hardcoded secrets or API keys
- [ ] Lint and formatting pass

---

## 6. Accessibility Basics

Accessibility (a11y) is part of the job, not an extra.

- Use real `<button>` and `<a>` elements instead of clickable `<div>`s.
- Make focus visible. Never remove outlines without a replacement.
- Use ARIA only when semantic HTML isn't enough.
- Test with a screen reader at least once (VoiceOver, NVDA).
- Run Lighthouse or axe DevTools on your pages.

---

## 7. Performance Basics

- Compress and correctly size images; use `loading="lazy"` for below-the-fold images.
- Avoid shipping large libraries for small tasks.
- Avoid unnecessary re-renders (don't optimize prematurely: measure first).
- Use the **Network** and **Performance** tabs in DevTools to find real bottlenecks.

---

## 8. Debugging Tips

1. **Read the error message**: the whole thing, including the line number.
2. Reproduce the bug consistently.
3. Use `console.log`, then graduate to the **debugger** and breakpoints.
4. Check the **Network** tab: is the request failing, or is the response wrong?
5. Isolate the problem: comment out code until it works, then add it back.
6. Explain the problem out loud (rubber duck debugging).
7. Search the exact error text, then check the official docs.

---

## 9. Asking for Help

Try on your own for a reasonable time (15-30 minutes), then ask. A good question includes:

- **What you're trying to do**
- **What you expected** to happen
- **What actually happened** (error messages, screenshots)
- **What you've already tried**
- A link to the branch or a minimal reproduction

Asking good questions is a skill, and teams value it.

---

## 10. Learning Roadmap

| Stage | Focus |
|-------|-------|
| **Month 1-2** | HTML, CSS (Flexbox, Grid), responsive design, Git |
| **Month 3-4** | JavaScript deep dive, DOM, fetch, async code |
| **Month 5-6** | One framework, state management, routing |
| **Month 7-9** | Testing, accessibility, performance, TypeScript |
| **Ongoing** | Build projects, read other people's code, contribute to the team |

### Project ideas
- Personal portfolio (responsive, accessible)
- To-do app with local storage
- Weather app using a public API
- Movie search app with pagination
- Mini e-commerce cart

---

## 11. Recommended Resources

- [MDN Web Docs](https://developer.mozilla.org): the best reference for HTML, CSS, and JavaScript
- [web.dev](https://web.dev): performance, accessibility, and best practices from Google
- [JavaScript.info](https://javascript.info): modern JavaScript tutorial
- [CSS-Tricks](https://css-tricks.com): guides to Flexbox and Grid
- [Frontend Mentor](https://www.frontendmentor.io): real design challenges to practice with
- [freeCodeCamp](https://www.freecodecamp.org): free structured curriculum
- Official docs for your framework (React, Vue, etc.)

---

## 12. Mindset

- **Nobody knows everything.** Seniors still google things daily.
- **Read code** as much as you write it.
- **Build things**, since projects teach more than tutorials.
- **Be curious about "why"**, not only "how".
- **Take feedback well.** It's the fastest way to grow.
- **Keep notes** on problems you've solved; you'll meet them again.

Happy coding!
