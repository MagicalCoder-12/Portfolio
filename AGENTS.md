# AGENTS.md - Agent Coding Guidelines

This file provides guidance for agentic coding agents working in this repository.

## Project Overview

This is a static HTML/CSS/JS portfolio website for "AJI Creators" game development studio. The site showcases mobile games and provides contact functionality.

## Technology Stack

- **HTML5** - Static pages with embedded CSS and JavaScript
- **CSS3** - Embedded styles with CSS variables for theming
- **JavaScript** - Vanilla JS (no frameworks)
- **External Services** - EmailJS (contact form), Font Awesome, Google Fonts

## File Structure

```
My Portfolio/
├── index.html          # Main portfolio page
├── portfolio.html      # Additional portfolio page
├── solar_nexus.html   # Game info page
├── dino_info.html     # Dino Birthday game page
├── privacy.html       # Privacy policy
├── assets/            # Images and media
│   ├── me.jpg
│   ├── app_icon_resized.png
│   ├── dev_icon_resized.png
│   ├── Dino.jpg
│   └── Slime.png
└── .qoder/rules/      # Agent rules
    └── byterover-rules.md
```

## Build/Lint/Test Commands

This is a **static HTML project** - there is no build system, test framework, or linter configured.

### Running the Project

Simply open `index.html` in a web browser, or use a local server:

```bash
# Python 3
python -m http.server 8000

# Node.js (if available)
npx serve
```

Then navigate to `http://localhost:8000`

### Testing

- **Manual testing only** - Open each HTML page in browser
- **Responsive testing** - Test at various viewport sizes (mobile, tablet, desktop)
- **Form testing** - Test contact form submission with valid/invalid inputs

### Code Validation

- Use browser DevTools to check for console errors
- Validate HTML at https://validator.w3.org/
- Check accessibility with browser accessibility tools

## Code Style Guidelines

### General Principles

- Keep HTML, CSS, and JS in a single file per page (current pattern)
- Use semantic HTML5 elements (`header`, `nav`, `section`, `footer`)
- Maintain consistent 2-space indentation
- Use descriptive class and id names (kebab-case)

### HTML Conventions

- Use `<!DOCTYPE html>` and include `lang` attribute
- Include meta viewport for responsive design
- Place CSS in `<style>` in `<head>`, JS in `<script>` at end of `<body>`
- Use `rel="noopener"` when using `target="_blank"` on external links

### CSS Guidelines

- Use CSS custom properties (`:root`) for colors and constants
- Follow BEM-like naming for complex components (e.g., `.game-card`, `.game-card__title`)
- Group related styles together
- Use flexbox and grid for layouts
- Include responsive breakpoints with `@media`
- Use semantic class names (e.g., `.nav-link`, not `.nl`)

### JavaScript Guidelines

- Use modern ES6+ syntax (const/let, arrow functions, template literals)
- Use `addEventListener` instead of inline event handlers
- Cache DOM queries when used multiple times
- Use `const` for DOM elements that won't be reassigned
- Handle errors gracefully with try/catch for async operations

### Naming Conventions

- **Files**: kebab-case (e.g., `solar-nexus.html`)
- **CSS Classes**: kebab-case (e.g., `.game-card`)
- **JavaScript**: camelCase (e.g., `mainContainer`, `animateParticles`)
- **IDs**: camelCase (e.g., `mainNav`, `backToTop`)

### Accessibility

- Include `alt` attributes on all images
- Use semantic headings (h1 -> h2 -> h3 hierarchy)
- Ensure sufficient color contrast
- Include `aria-label` on icon-only buttons
- Make interactive elements keyboard accessible

### Error Handling

- Use try/catch for async operations (EmailJS calls)
- Show user-friendly error messages in alerts
- Log errors to console for debugging
- Validate form inputs before submission

## Existing Agent Rules

This project uses the Byterover MCP server. See `.qoder/rules/byterover-rules.md`:

- Use `byterover-store-knowledge` when learning new patterns, finding solutions, or completing tasks
- Use `byterover-retrieve-knowledge` when starting new tasks or debugging

## Common Tasks

### Adding a New Game Card

1. Add new `<div class="game-card">` in the games grid section
2. Include game image, title, description, and links
3. Update the staggered animation delay in the JavaScript

### Adding a New Section

1. Add `<section id="section-name">` with semantic heading
2. Add corresponding nav link
3. Add CSS for any new component styles

### Modifying Colors/Theme

Edit CSS variables in `:root` at the top of the `<style>` block:

```css
:root {
  --neon-blue: #00ffff;
  --neon-purple: #9d00ff;
  --dark-bg: #0a0a1a;
}
```
