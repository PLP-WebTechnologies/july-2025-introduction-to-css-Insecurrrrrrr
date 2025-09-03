Below are the two deliverable files with extra demos (block vs inline vs inline-block) and slightly adjusted colors/spacing.

---

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>CSS Box Model Practice</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header class="site-header container">
      <h1>Styling with the CSS Box Model</h1>
      <p class="tagline">Margins, padding, borders, and backgrounds—visually demonstrated.</p>
      <nav class="nav">
        <a class="nav__link is-active" href="#intro">Intro</a>
        <a class="nav__link" href="#cards">Cards</a>
        <a class="nav__link" href="#demo">Box Model Demo</a>
        <a class="nav__link" href="#display">Display Types</a>
        <a class="nav__link" href="#cta">Buttons</a>
      </nav>
    </header>

    <main class="container">
      <section id="intro" class="section">
        <h2>Introduction</h2>
        <p>
          This page uses an external stylesheet to apply basic CSS properties. Notice
          the consistent spacing controlled via <strong>margin</strong>,
          <strong>padding</strong>, <strong>border</strong>, and
          <strong>background</strong> colors.
        </p>
        <p>
          Inspect each element (header, nav, cards, and demo boxes) to see how the
          Box Model and <code>display</code> property influence size and spacing.
        </p>
      </section>

      <section id="cards" class="section">
        <h2>Card Layout</h2>
        <div class="grid">
          <article class="card">
            <h3 class="card__title">Card One</h3>
            <p>
              Cards use padding for internal spacing, borders for definition, and
              margins to separate from neighbors.
            </p>
            <a href="#" class="btn btn--primary">Action</a>
          </article>
          <article class="card">
            <h3 class="card__title">Card Two</h3>
            <p>
              Background colors help visualize box boundaries.
            </p>
            <a href="#" class="btn">Secondary</a>
          </article>
          <article class="card">
            <h3 class="card__title">Card Three</h3>
            <p>
              Borders contribute to the element's total size.
            </p>
            <a href="#" class="btn btn--ghost">Ghost</a>
          </article>
        </div>
      </section>

      <section id="demo" class="section">
        <h2>Box Model Demo</h2>
        <div class="demo-row">
          <div class="demo-box demo-box--a">
            <h4>Box A</h4>
            <p>Padding: 24px · Border: 2px · Margin: 16px</p>
          </div>
          <div class="demo-box demo-box--b">
            <h4>Box B</h4>
            <p>Padding: 8px · Border: 6px · Margin: 32px</p>
          </div>
        </div>
      </section>

      <section id="display" class="section">
        <h2>Display Property Demo</h2>
        <p>
          Below are three boxes using different <code>display</code> values: block,
          inline, and inline-block.
        </p>
        <div class="display-demo">
          <span class="box block-box">Block</span>
          <span class="box inline-box">Inline</span>
          <span class="box inlineblock-box">Inline-Block</span>
        </div>
      </section>

      <section id="cta" class="section">
        <h2>Buttons</h2>
        <div class="btn-row">
          <button class="btn btn--primary">Primary</button>
          <button class="btn">Default</button>
          <button class="btn btn--ghost">Ghost</button>
          <button class="btn btn--danger">Danger</button>
        </div>
      </section>
    </main>

    <footer class="site-footer">
      <div class="container footer__inner">
        <small>&copy; 2025 Box Model Lab</small>
        <small><a href="#top" class="footer__link">Back to top</a></small>
      </div>
    </footer>
  </body>
</html>
```

```css
/* styles.css */
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  color: #1e293b;
  background: #f1f5f9;
}
:root {
  --brand: #3b82f6;
  --brand-dark: #1d4ed8;
  --border: #cbd5e1;
  --muted: #64748b;
}
.container { max-width: 960px; margin: 0 auto; padding: 0 1rem; }
.section { margin: 2rem 0; }

.site-header {
  background: white;
  border-bottom: 2px solid var(--border);
  padding: 1.5rem 1rem;
}
.site-header h1 { margin: 0; color: var(--brand-dark); }
.tagline { margin: .25rem 0 0; color: var(--muted); }

.nav { display: flex; gap: .5rem; margin-top: 1rem; }
.nav__link { padding: .5rem .75rem; border: 1px solid var(--border); border-radius: .5rem; text-decoration: none; }
.nav__link.is-active { background: var(--brand); color: white; }

.grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1rem; }
.card { background: white; border: 1px solid var(--border); padding: 1rem; border-radius: .75rem; }
.card__title { margin-top: 0; }

.demo-row { display: flex; flex-wrap: wrap; gap: 1rem; }
.demo-box { flex: 1 1 240px; border: 2px dashed var(--border); background: #e2e8f0; border-radius: .5rem; }
.demo-box--a { padding: 24px; margin: 16px; }
.demo-box--b { padding: 8px; border-width: 6px; margin: 32px; }

.display-demo { border: 1px solid var(--border); padding: 1rem; background: #fff; }
.box { padding: .5rem; background: #93c5fd; margin: .25rem; }
.block-box { display: block; }
.inline-box { display: inline; }
.inlineblock-box { display: inline-block; }

.btn { display: inline-block; padding: .5rem 1rem; margin: .25rem; border-radius: .5rem; border: 1px solid var(--border); cursor: pointer; }
.btn--primary { background: var(--brand); color: white; border-color: var(--brand-dark); }
.btn--ghost { background: transparent; border: 1px dashed var(--brand); color: var(--brand-dark); }
.btn--danger { background: #ef4444; color: white; border-color: #b91c1c; }

.site-footer { background: #0f172a; color: #e2e8f0; padding: 1rem; margin-top: 3rem; text-align: center; }
.footer__link { color: #cbd5e1; text-decoration: none; }
.footer__link:hover { text-decoration: underline; }
```

