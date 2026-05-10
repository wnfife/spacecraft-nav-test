# 🛰 Spacecraft Navigation Tutorials

Interactive tutorials on orbital mechanics, estimation theory, and navigation algorithms — built with [Quarto](https://quarto.org) and hosted free on GitHub Pages.

## Live Site

> `https://your-username.github.io/spacecraft-nav`

---

## Topics

| Page | Status |
|---|---|
| Least Squares Estimation | ✅ Published |
| Kalman Filter | 🚧 Coming soon |
| Lambert's Problem | 🚧 Coming soon |
| Batch Orbit Determination | 🚧 Coming soon |

---

## Local Development

### Prerequisites

```bash
# 1. Install Quarto  (https://quarto.org/docs/get-started/)
#    Download the installer for your OS from quarto.org

# 2. Install Python dependencies
pip install numpy plotly
```

### Preview locally

```bash
# Live preview — auto-reloads on save
quarto preview

# Or render to /docs once
quarto render
```

### Project structure

```
spacecraft-nav/
├── _quarto.yml          # Site config (navbar, theme, output dir)
├── styles.css           # Custom CSS
├── index.qmd            # Home page
├── least-squares.qmd    # Tutorial: Least Squares
├── docs/                # Rendered HTML output (committed to repo)
└── .github/
    └── workflows/
        └── publish.yml  # Auto-render & deploy on push to main
```

---

## Deploying to GitHub Pages

### Option A — Auto-deploy via GitHub Actions (recommended)

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set **Source** to `GitHub Actions`
4. Push any change to `main` — the action renders and deploys automatically

### Option B — Manual (render locally, push `/docs`)

1. Run `quarto render` locally
2. Commit the `docs/` folder
3. Go to **Settings → Pages**, set source to `Deploy from branch → main → /docs`

---

## Adding a New Tutorial Page

1. Create `my-topic.qmd` in the project root
2. Add it to `_quarto.yml` under `navbar → left`
3. Write content using Markdown + LaTeX + Plotly code chunks
4. Run `quarto preview` to see it live

### Minimal page template

```markdown
---
title: "My Topic"
subtitle: "One-line description"
date: today
format:
  html:
    code-fold: true
---

## Introduction

Text with inline math $\mu = GM$ and display math:

$$
\hat{\mathbf{x}} = \left(\mathbf{H}^\top \mathbf{H}\right)^{-1} \mathbf{H}^\top \mathbf{y}
$$

## Interactive Plot

```python
import plotly.graph_objects as go
fig = go.Figure()
# ... your plot ...
fig.show()
```
```

---

## Dependencies

| Tool | Version | Purpose |
|---|---|---|
| Quarto | ≥ 1.4 | Site rendering |
| Python | ≥ 3.9 | Code execution |
| numpy | any | Numerics |
| plotly | any | Interactive plots |

---

## License

MIT — use and adapt freely.
