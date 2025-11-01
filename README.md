# Voiden Documentation

> Official documentation for the Voiden platform, built with [Docusaurus](https://docusaurus.io/).

[![Node.js](https://img.shields.io/badge/node-%3E%3D18.0-brightgreen)](https://nodejs.org/)
[![Docusaurus](https://img.shields.io/badge/docusaurus-3.5.2-blue)](https://docusaurus.io/)

## 📖 Table of Contents

- [Quick Start](#-quick-start)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [Development Workflow](#-development-workflow)
- [Styling & Theming](#-styling--theming)
- [Deployment](#-deployment)

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18.0 or above ([Download](https://nodejs.org/))
- **npm** or **yarn** package manager

### Installation & Development

```bash
# 1. Clone the repository (if you haven't already)
git clone https://github.com/VoidenHQ/docs.git
cd docs

# 2. Install dependencies
npm install

# 3. Start the development server
npm start
```

The site will open at `http://localhost:3000/`. Changes are hot-reloaded automatically.

### Build & Preview

```bash
# Build for production
npm run build

# Preview the production build locally
npm run serve
```

## 📁 Project Structure

```
voiden-docs/
├── docs/                          # 📝 Documentation source files (Markdown/MDX)
│   ├── getting-started/
│   ├── guides/
│   └── intro.md
├── src/
│   ├── css/
│   │   └── custom.css            # 🎨 Custom styles (Voiden theme)
│   ├── pages/                    # ⚛️  Custom React pages
│   │   └── index.tsx             # Homepage
│   └── components/               # 🧩 Reusable React components
├── static/                       # 📦 Static assets (images, files)
│   └── img/
├── docusaurus.config.ts          # ⚙️  Main site configuration
├── sidebars.ts                   # 📑 Sidebar navigation structure
└── package.json                  # 📋 Dependencies and scripts
```

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines on:

- How to add or edit documentation
- Code style and formatting
- Submitting pull requests
- Reporting issues

### Quick Contribution Guide

1. **Fork and clone** the repository
2. **Create a branch**: `git checkout -b feature/your-feature-name`
3. **Make your changes** in the `docs/` folder
4. **Test locally**: `npm start`
5. **Commit**: `git commit -m "Add: your change description"`
6. **Push**: `git push origin feature/your-feature-name`
7. **Open a Pull Request** on GitHub

## 💻 Development Workflow

### Adding New Documentation

1. Create a new `.md` or `.mdx` file in the appropriate `docs/` subfolder
2. Add frontmatter at the top:
   ```markdown
   ---
   id: my-doc-id
   title: My Document Title
   sidebar_label: Short Label
   sidebar_position: 1
   ---
   ```
3. Write your content using Markdown or MDX
4. Update `sidebars.ts` if needed (usually auto-generated)

### Editing Existing Docs

Simply edit the Markdown files in `docs/` - changes will hot-reload instantly.

### Working with Images

```markdown
<!-- Place images in static/img/ -->
![Alt text](/img/my-image.png)

<!-- Or use relative paths -->
![Alt text](./images/my-image.png)
```

## 🎨 Styling & Theming

The site features a custom **Voiden brand theme** with:

- **Fonts**: Source Sans 3 (body text), JetBrains Mono (code blocks)
- **Color Palette**:
  - Dark theme: Soft dark backgrounds with refined accent colors
  - Light theme: Warm off-white backgrounds
  - Brand colors: Teal (`#22d3ee`), Purple (`#a78bfa`), Pink (`#f472b6`)
- **Features**: Dark/light mode toggle, responsive design, syntax highlighting

### Customizing Styles

Edit `src/css/custom.css` to modify:
- Color variables (`:root` and `[data-theme='light']`)
- Typography and fonts
- Component styles (buttons, cards, navigation)
- Custom utility classes

## 🚀 Deployment

### Build for Production

```bash
npm run build
```

This generates static content into the `build/` directory that can be served by any static hosting service.

### Deployment Options

- **GitHub Pages**: See [Docusaurus deployment docs](https://docusaurus.io/docs/deployment)
- **Vercel**: Connect your GitHub repo and deploy automatically
- **Netlify**: Drag & drop the `build/` folder or connect via Git
- **Custom Server**: Serve the `build/` folder with any web server

## 📚 Resources

- [Docusaurus Documentation](https://docusaurus.io/docs)
- [Markdown Guide](https://www.markdownguide.org/)
- [MDX Documentation](https://mdxjs.com/)
- [Voiden GitHub](https://github.com/VoidenHQ)

## 📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

Copyright © 2025 ApyHub

## 🙋 Support

- **Issues**: [GitHub Issues](https://github.com/VoidenHQ/feedback)
- **Discussions**: [GitHub Discussions](https://github.com/VoidenHQ/feedback/discussions)

---

Made with ❤️ by the Voiden team
