# Framework Recommendation: Bootstrap vs Tailwind CSS

## Project Context

Rueda Libre is a two-page ecosystem: the main site (v2.0) built with Bootstrap,
and the Rueda Nocturna campaign landing built with Tailwind CSS. Both frameworks
were used in the same project to compare their strengths in practice.

## Verdict: Tailwind CSS for the modular project

For the modular project (a multi-page responsive site with custom branding),
Tailwind CSS is the better choice. Here is why:

### 1. Design control

Bootstrap gives you pre-built components (cards, navbars, modals) that look the
same on every site. Tailwind gives you atomic utilities that you combine freely.
When the project needs a unique visual identity — like Rueda Nocturna's night
theme — Tailwind lets you build it without fighting default styles.

### 2. Brand theming

With `@theme`, custom brand tokens (`--color-farol`, `--color-noche`) generate
utilities automatically (`bg-farol`, `text-noche`). Changing the entire brand
palette means editing one block in `input.css`. In Bootstrap, overriding Sass
variables or writing custom CSS on top of the framework adds complexity.

### 3. Dark mode

Tailwind's `dark:` variant makes dark mode a first-class feature — you add
`dark:bg-noche` next to `bg-luna` and it follows the user's system preference.
Bootstrap requires manual CSS or a third-party solution for dark mode.

### 4. CSS output size

Tailwind scans your files and generates only the CSS for classes you actually
use. Bootstrap ships its full CSS unless you manually configure tree-shaking.
For a landing page with a handful of components, Tailwind produces significantly
smaller CSS.

### 5. Responsive design

Both frameworks support responsive breakpoints, but Tailwind's prefix system
(`sm:`, `md:`, `lg:`) keeps responsive logic inline with the element, making it
easier to see how each element behaves at every screen size without switching
between HTML and CSS files.

## When Bootstrap is the better choice

- **Rapid prototyping**: Bootstrap's ready-made components get a functional UI
  faster when custom design is not a priority.
- **Team familiarity**: If the team already knows Bootstrap, switching adds a
  learning curve.
- **Complex interactive components**: Bootstrap includes JavaScript for modals,
  dropdowns, carousels, and tooltips out of the box. Tailwind is CSS-only.

## Conclusion

For a project that demands custom branding, responsive design, dark mode, and
optimized CSS, Tailwind CSS is the stronger choice. Bootstrap remains valuable
for projects where speed matters more than design uniqueness, or when built-in
JavaScript components are needed.
