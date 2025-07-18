# CSS Project

A CSS framework.

## 🚀 Quick Start

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the development server:**
   ```bash
   npm start
   ```

3. **Open your browser to:** `http://localhost:8000`

## 📋 Prerequisites

- Node.js (version 14 or higher)
- npm (comes with Node.js)

## 🛠️ Available Commands

| Command | Description |
|---------|-------------|
| `npm start` | Start the development server on port 8000 |
| `npm run dev` | Same as `npm start` (development alias) |
| `npm run serve` | Basic serve command |
| `npm run serve:open` | Start server (manual browser opening) |

## 🏗️ Project Structure

```
css/
├── index.html          # Main HTML file
├── CSS.css            # Stylesheet (referenced but needs to be created)
├── package.json       # Node.js project configuration
├── node_modules/      # Dependencies (auto-generated)
├── LICENSE           # Project license
└── README.md         # This file
```

## 🔧 Development Workflow

1. **Start the server:**
   ```bash
   npm start
   ```

2. **Edit your files:**
   - Modify `index.html` for structure
   - Create/edit `CSS.css` for styling
   - Add any additional assets

3. **View changes:**
   - Navigate to `http://localhost:8000`
   - Refresh browser to see updates

## 📝 Notes

- **Missing CSS file:** The HTML references `CSS.css` which doesn't exist yet. Create it to add styling.
- **Port 8000:** The server runs on port 8000 by default. Change the `-l 8000` flag in package.json scripts to use a different port.
- **Static serving:** Uses Vercel's `serve` package with the `-s` flag for proper static file serving.

## 🔗 Useful Links

- [Serve Documentation](https://github.com/vercel/serve)
- [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS)

## 📦 Dependencies

- **serve** (dev): Vercel's static file server for local development

---

**Happy coding!** 🎉