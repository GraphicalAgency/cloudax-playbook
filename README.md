# Playbook Viewer

A lightweight, interactive HTML viewer for multi-page playbooks and guides. Perfect for presenting branded playbooks, pitch decks, or procedural documents with a clean sidebar navigation and full keyboard support.

## Features

- **Sidebar Navigation** — Chapter-based menu with active state highlighting
- **Image Viewer** — Clean, centered display with loading states
- **Page Counter** — Shows current page and total page count
- **Navigation Controls** — Previous/Next buttons plus keyboard shortcuts
- **Keyboard Support** — Arrow keys to navigate, spacebar for next page
- **Responsive Layout** — Flexbox-based design that works across devices
- **Zero Dependencies** — Pure HTML, CSS, and JavaScript

## Quick Start

### 1. Copy the Template

Copy the `TEMPLATE` folder to your project and rename it:

```
PROJECT_ROOT/
├── playbook-viewer.html
├── JPGs/
│   ├── page_1.jpg
│   ├── page_2.jpg
│   └── ... (all page images)
```

### 2. Organize Your Images

Export or save all playbook pages as JPG images in the `JPGs/` subfolder. Name them consistently (e.g., `page_1.jpg`, `page_2.jpg`).

### 3. Configure the Viewer

Open `playbook-viewer.html` and update two configuration objects:

#### A. Menu Structure

Define your chapters and which pages belong to each:

```javascript
const menuStructure = {
    'Chapter 1': [1, 2, 3],
    'Chapter 2': [4, 5, 6],
    'Chapter 3': [7, 8, 9, 10]
};
```

#### B. File Mapping

Map each page number to its image filename:

```javascript
const fileMapping = {
    1: 'page_1.jpg',
    2: 'page_2.jpg',
    3: 'page_3.jpg',
    // ... continue for all pages
};
```

#### C. Project Name

Update the sidebar heading (search for `[Project Name]`):

```html
<h2>Your Project Name</h2>
```

### 4. Test Locally

Open `playbook-viewer.html` in your browser. Navigate using:
- **Click** menu items in the sidebar
- **Arrow Keys** — Left/Right to go to previous/next page
- **Spacebar** — Jump to next page
- **Buttons** — Use Previous/Next buttons in the toolbar

## File Structure

```
TEMPLATE/
├── playbook-viewer.html    # Main viewer file (update this)
└── JPGs/
    ├── page_1.jpg
    ├── page_2.jpg
    └── ...
```

The HTML file contains:
- **Configuration Section** (top of `<script>`) — Where you customize `menuStructure` and `fileMapping`
- **HTML Structure** — Sidebar, toolbar, and viewer container
- **Styling** — All CSS inline, ready to customize colors and fonts
- **JavaScript** — Navigation, menu building, and keyboard handlers

## Customization

### Change Colors

Look for these CSS classes to update the color scheme:

```css
.menu-item.active {
    background: #e3f2fd;      /* Highlight color */
    color: #1976d2;           /* Text color */
    border-left-color: #1976d2; /* Accent bar */
}

button {
    background: #1976d2;      /* Button color */
}
```

### Adjust Sidebar Width

```css
.sidebar {
    width: 280px; /* Change this value */
}
```

### Change Fonts

```css
body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, ...;
}
```

## Deployment

### GitHub Pages

1. Create a repository on GitHub
2. Push the folder contents (including `playbook-viewer.html` and `JPGs/`)
3. Enable GitHub Pages in Settings → Pages
4. Choose the branch and folder (usually `main` and root)
5. Your playbook will be live at `https://username.github.io/repo-name/playbook-viewer.html`

### Alternative: Netlify

1. Push to GitHub (same structure as above)
2. Connect your repo to Netlify
3. Set build command to `None`
4. Netlify deploys automatically on push
5. View at your Netlify domain

### Local Hosting

For testing, use a simple HTTP server:

```bash
# Python 3
python -m http.server 8000

# Then visit: http://localhost:8000/playbook-viewer.html
```

## Troubleshooting

### Images Not Loading

- Check that image filenames in `fileMapping` exactly match files in `JPGs/` folder
- Ensure all JPG files are in the `JPGs/` subfolder (same directory as HTML file)
- Check browser console (F12) for 404 errors

### Menu Not Showing

- Verify `menuStructure` has correct syntax (chapters as keys, arrays of numbers as values)
- All page numbers in `menuStructure` must exist in `fileMapping`

### Page Counter Shows 0

- Make sure `fileMapping` has at least one entry
- Check for typos in the `fileMapping` object

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). Requires JavaScript enabled.

## Notes

- All styling is inline for easy deployment and customization
- No external libraries or dependencies
- Self-contained single HTML file (plus images folder)
- Images load progressively with loading state feedback
- Keyboard navigation follows standard conventions

## License

Use freely for client work, internal playbooks, and presentations.
