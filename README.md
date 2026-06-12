# SoftTacWorld Challenge Website

A static single-page website for the SoftTacWorld Visuo-Tactile Robot Manipulation Challenge.

## Quick Start

Open `index.html` in any browser — no build step or server required.

For local development with live reload, you can use any static server:

```bash
# Python
python3 -m http.server 8000

# Node.js (npx)
npx serve .
```

## File Structure

```
softtacworld/
├── index.html          # All page sections
├── css/style.css       # Styles (CSS custom properties for theming)
├── js/main.js          # Vanilla JS (nav, scroll, tabs)
├── assets/images/
│   ├── tasks/          # Task illustration images (T0-T3)
│   ├── organizers/     # Team headshots (square, ≥200×200px)
│   └── sponsors/       # Sponsor logos (transparent PNG, ~50px height)
└── README.md
```

## How to Customize

### Change colors / theme

Edit the CSS custom properties at the top of `css/style.css`:

```css
:root {
  --color-primary: #0f6e84;      /* main teal */
  --color-accent: #1a9cb8;       /* links, buttons */
  --color-highlight: #f0c840;    /* gold accents */
  ...
}
```

### Add organizers

Copy an organizer card block in `index.html`:

```html
<div class="organizer-card">
  <img src="assets/images/organizers/firstname-lastname.jpg" alt="Full Name">
  <h4><a href="https://homepage.com">Full Name</a></h4>
  <p class="affiliation">University / Lab</p>
</div>
```

Image recommendation: square crop, at least 200×200px, JPEG or WebP.

### Update leaderboard

Edit the `<tbody>` rows in the leaderboard table. Use classes `rank-gold`, `rank-silver`, `rank-bronze` for the top 3:

```html
<tr class="rank-gold">
  <td>🥇 1</td>
  <td>Team Name</td>
  <td>Method Name</td>
  <td>0.92</td>
  <td>0.87</td>
  <td>0.81</td>
  <td>2026-08-15</td>
</tr>
```

### Update dates / timeline

Find the `#timeline` section and edit `.timeline-item` blocks. Mark the current phase with class `is-current`.

### Add task images

Replace the `<div class="placeholder-img ...">` elements in the Tasks section with actual `<img>` tags:

```html
<img src="assets/images/tasks/t0.png" alt="T0: Rigid Object to Tray" class="task-img">
```

## Deployment

This site works on any static hosting:

- **GitHub Pages**: push to `main` branch, enable Pages in repo settings
- **Netlify / Vercel**: drag-and-drop the folder or connect the repo
- **University server**: upload via FTP/SCP

No build step needed — what you see in the folder is what gets deployed.

## Browser Support

Modern browsers (Chrome, Firefox, Safari, Edge). Uses CSS Grid, Custom Properties, and IntersectionObserver (all supported in browsers from ~2018+).
