# Contributing to Voiden Documentation

Thank you for your interest in contributing to the Voiden documentation! This guide will help you get started.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Documentation Guidelines](#documentation-guidelines)
- [Style Guide](#style-guide)
- [Submitting Changes](#submitting-changes)
- [Review Process](#review-process)

## 🤝 Code of Conduct

We are committed to providing a welcoming and inclusive environment. Please be respectful and constructive in all interactions.

## 🚀 Getting Started

### Prerequisites

- Node.js 18.0 or above
- Git
- A GitHub account
- Basic knowledge of Markdown

### Setup

1. **Fork the repository** on GitHub
2. **Clone your fork**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/docs.git
   cd docs
   ```
3. **Add upstream remote**:
   ```bash
   git remote add upstream https://github.com/VoidenHQ/docs.git
   ```
4. **Install dependencies**:
   ```bash
   npm install
   ```
5. **Start the dev server**:
   ```bash
   npm start
   ```

## 💡 How to Contribute

### Types of Contributions

We welcome:

- 📝 **Documentation improvements** - Fix typos, clarify explanations, add examples
- 🆕 **New documentation** - Add missing guides, tutorials, or API references
- 🐛 **Bug reports** - Report broken links, incorrect information, or rendering issues
- ✨ **Feature suggestions** - Propose new documentation sections or improvements
- 🎨 **Design improvements** - Enhance the documentation site's UI/UX

### Finding Something to Work On

- Check [open issues](https://github.com/VoidenHQ/feedback/issues) labeled `documentation`
- Look for `good first issue` labels if you're new
- Ask in discussions if you're unsure where to start

## 📖 Documentation Guidelines

### File Organization

```
docs/
├── getting-started/       # Installation, quick start guides
├── guides/               # How-to guides and tutorials
├── api/                  # API reference documentation
├── concepts/             # Conceptual explanations
└── troubleshooting/      # Common issues and solutions
```

### Markdown Basics

All documentation is written in Markdown (`.md`) or MDX (`.mdx`) format.

#### Frontmatter

Every documentation page should have frontmatter at the top:

```markdown
---
id: unique-page-id
title: Page Title
sidebar_label: Short Label
sidebar_position: 1
description: Brief description for SEO
tags: [tag1, tag2]
---
```

#### Headings

Use proper heading hierarchy:

```markdown
# Page Title (H1 - only one per page, usually from frontmatter)

## Main Section (H2)

### Subsection (H3)

#### Detail Section (H4)
```

#### Code Blocks

Use fenced code blocks with language identifiers:

````markdown
```javascript
const greeting = "Hello, World!";
console.log(greeting);
```

```bash
npm install package-name
```
````

#### Links

```markdown
<!-- Internal link (relative) -->
[Link text](./other-page.md)

<!-- Internal link (absolute) -->
[Link text](/docs/category/page)

<!-- External link -->
[Link text](https://example.com)
```

#### Images

```markdown
<!-- From static folder -->
![Alt text](/img/screenshot.png)

<!-- Relative to current file -->
![Alt text](./images/diagram.png)
```

#### Admonitions (Callouts)

```markdown
:::note
This is a note
:::

:::tip
This is a helpful tip
:::

:::warning
This is a warning
:::

:::danger
This is important/dangerous information
:::

:::info
This is informational content
:::
```

## ✍️ Style Guide

### Writing Style

- **Be clear and concise** - Use simple language and short sentences
- **Be consistent** - Follow existing patterns and terminology
- **Be accurate** - Ensure technical accuracy and test all code examples
- **Be helpful** - Anticipate user questions and provide context

### Formatting

- Use **bold** for UI elements: "Click the **Save** button"
- Use `code` for:
  - Code, commands, and file names: `npm install`
  - Configuration values: set `debug: true`
  - Keyboard keys: press `Ctrl+C`
- Use *italics* sparingly for emphasis
- Use numbered lists for sequential steps
- Use bullet points for non-sequential items

### Code Examples

- Provide complete, working code examples
- Include comments for complex code
- Show expected output when relevant
- Use realistic examples (avoid `foo`, `bar` when possible)

### Tone

- Use second person ("you") to address readers
- Be friendly but professional
- Avoid jargon when possible; explain technical terms
- Use active voice: "Configure the server" not "The server should be configured"

## 🔄 Submitting Changes

### Branch Naming

Use descriptive branch names:

```
docs/add-authentication-guide
docs/fix-installation-typo
docs/update-api-reference
```

### Commit Messages

Follow this format:

```
Type: Brief description

Longer explanation if needed

Fixes #123
```

**Types:**
- `Add:` New documentation
- `Update:` Changes to existing docs
- `Fix:` Corrections and bug fixes
- `Remove:` Removing content
- `Style:` Formatting/styling changes

**Examples:**
```
Add: Authentication guide for OAuth2

Fix: Broken link in installation guide

Update: API reference with new endpoints
```

### Creating a Pull Request

1. **Ensure your fork is up to date**:
   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```

2. **Create a new branch**:
   ```bash
   git checkout -b docs/your-feature-name
   ```

3. **Make your changes** and test locally:
   ```bash
   npm start
   ```

4. **Commit your changes**:
   ```bash
   git add .
   git commit -m "Add: Your descriptive commit message"
   ```

5. **Push to your fork**:
   ```bash
   git push origin docs/your-feature-name
   ```

6. **Open a Pull Request** on GitHub:
   - Provide a clear title and description
   - Reference any related issues
   - Add screenshots if relevant
   - Request review from maintainers

### Pull Request Checklist

Before submitting, ensure:

- [ ] Content is accurate and tested
- [ ] Spelling and grammar are correct
- [ ] Links work and point to the right locations
- [ ] Images are optimized and display correctly
- [ ] Code examples are complete and functional
- [ ] Frontmatter is properly configured
- [ ] The site builds without errors (`npm run build`)
- [ ] Changes look good in both light and dark themes
- [ ] Content follows the style guide

## 🔍 Review Process

1. **Automated checks** run on all PRs (build, links, etc.)
2. **Maintainer review** - We'll review your changes and provide feedback
3. **Revisions** - Address any requested changes
4. **Approval** - Once approved, your PR will be merged
5. **Deployment** - Changes are deployed automatically after merge

### Review Timeline

- We aim to provide initial feedback within 2-3 business days
- Larger contributions may take longer to review
- Feel free to ping maintainers if you haven't heard back in a week

## 🎨 Working with Styles

If you need to modify styles (rare for documentation contributions):

- Edit `src/css/custom.css`
- Test in both light and dark themes
- Ensure changes are responsive (mobile, tablet, desktop)
- Document any new CSS classes or utilities

## 🧪 Testing

Before submitting:

```bash
# Start dev server and check your changes
npm start

# Build for production to catch any errors
npm run build

# Serve the production build
npm run serve
```

## ❓ Questions?

- **General questions**: Open a [Discussion](https://github.com/VoidenHQ/feedback/discussions)
- **Bug reports**: Open an [Issue](https://github.com/VoidenHQ/feedback/issues)
- **Quick questions**: Comment on existing issues or PRs

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the Apache License 2.0, the same license as the project.

## 🙏 Thank You!

Every contribution, no matter how small, helps make Voiden better for everyone. We appreciate your time and effort!

---

**Happy contributing! 🎉**
