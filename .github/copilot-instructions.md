# Ya Ganaste - AI Coding Instructions

## Project Overview

"Ya Ganaste" is a Spanish-language landing page for a sweepstakes/lottery platform. This is a vanilla HTML/CSS/JS website with no build process or external dependencies - open `index.html` directly in a browser to run.

## Architecture & File Structure

- **`index.html`** - Complete single-page application with semantic sections: header, hero, services, about, footer
- **`styles.css`** - CSS custom properties (variables) driven design with mobile-first responsive grid
- **`script.js`** - Vanilla JavaScript for mobile menu, smooth scrolling, and scroll effects

## Design System Conventions

### CSS Variables (`:root`)
```css
--primary-color: #6366f1    /* Primary brand purple */
--secondary-color: #8b5cf6  /* Secondary purple */
--accent-color: #ec4899     /* Pink accent (unused currently) */
```

### Component Patterns
- **Gradient text**: Use `background: linear-gradient()` with `-webkit-background-clip: text`
- **Cards**: White background with `var(--shadow)` and hover transforms (`translateY(-10px)`)
- **Buttons**: Two variants - `.btn-primary` (solid) and `.btn-secondary` (outlined)

## JavaScript Patterns

### Event Handling Structure
All JavaScript is wrapped in `DOMContentLoaded` listener. Key patterns:
- Mobile menu uses CSS class toggles (`nav.active`) 
- Hamburger animation manipulates individual `<span>` transforms
- Smooth scrolling calculates header offset: `targetPosition = targetSection.offsetTop - headerHeight`

### Responsive Behavior
- Mobile breakpoint: `768px` - nav becomes slide-out menu
- Links auto-close mobile menu when clicked
- Scroll effects modify header shadow dynamically

## Spanish Content Strategy

All user-facing content is in Spanish. Key terms:
- "Ya Ganaste" = "You Already Won" (brand name)
- "Sorteos" = "Raffles/Sweepstakes" 
- "Premios" = "Prizes"

## Development Workflow

**No build process required** - modify files directly:

1. **Testing**: Open `index.html` in browser, no local server needed
2. **CSS Changes**: Modify `styles.css`, refresh browser
3. **JS Changes**: Edit `script.js`, refresh browser (check console for errors)
4. **Git Workflow**: **ALWAYS** after making any file changes, execute these commands:
   ```powershell
   git add .
   git commit -m "Descriptive commit message in Spanish"
   git push
   ```

## Git Commit Guidelines

- **Mandatory**: Always commit and push changes immediately after modifications
- **Commit messages**: Use Spanish and be descriptive about the changes made
- **Examples**:
  - `git commit -m "Actualizar estilos del header y menú móvil"`
  - `git commit -m "Agregar nueva sección de testimonios"`
  - `git commit -m "Corregir responsividad en dispositivos móviles"`
- **Process**: Never leave changes uncommitted - always complete the full git workflow

## Mobile-First Guidelines

- Use CSS Grid with `repeat(auto-fit, minmax())` for responsive layouts
- Test mobile menu at `<=768px` viewport
- Verify touch targets are 44px minimum on mobile
- Check gradient text renders correctly across browsers

## Common Modification Patterns

- **Adding sections**: Insert between `<main>` sections, add corresponding nav link
- **Color changes**: Update CSS variables in `:root`
- **New animations**: Follow `@keyframes fadeInUp` pattern with staggered delays
- **Mobile menu items**: Add to `.nav-list` and ensure mobile close handler applies