# Contributing to Cinematic Archives

Thank you for your interest in contributing to Cinematic Archives! This document provides guidelines and instructions for contributing.

## 🤝 How to Contribute

### Reporting Bugs

Before creating a bug report, please check existing issues to avoid duplicates.

**When reporting a bug, include:**
- Clear, descriptive title
- Steps to reproduce
- Expected behavior
- Actual behavior
- Screenshots (if applicable)
- Browser/OS/Device information
- Console errors (if any)

**Example:**
```markdown
**Bug:** Particle animation stutters on mobile

**Steps to Reproduce:**
1. Open site on iPhone 12
2. Navigate to main page
3. Observe particle animation

**Expected:** Smooth 60 FPS
**Actual:** Drops to 30 FPS intermittently

**Device:** iPhone 12, iOS 17.1, Safari
**Console:** No errors
```

### Suggesting Features

Feature requests are welcome! Please provide:
- Clear description of the feature
- Use case / problem it solves
- Proposed implementation (optional)
- Mockups or examples (if applicable)

### Pull Requests

1. **Fork the repository**
   ```bash
   git clone https://github.com/your-username/cinema-scanner-.git
   cd cinema-scanner-
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow existing code style
   - Add comments for complex logic
   - Test thoroughly

4. **Commit your changes**
   ```bash
   git add .
   git commit -m "Add: brief description of changes"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**
   - Provide clear description
   - Reference related issues
   - Include screenshots for UI changes

## 💻 Development Setup

### Prerequisites
- Node.js 18+
- npm or yarn
- Git
- Code editor (VS Code recommended)

### Setup Steps

1. **Clone and install**
   ```bash
   git clone https://github.com/anacondy/cinema-scanner-.git
   cd cinema-scanner-
   npm install
   ```

2. **Configure environment**
   ```bash
   cp .env.example .env
   # Edit .env and add your Gemini API key
   ```

3. **Start dev server**
   ```bash
   npm run dev
   ```

4. **Build for production**
   ```bash
   npm run build
   ```

## 📝 Code Style

### JavaScript/React

- Use functional components with hooks
- Prefer `const` over `let`
- Use descriptive variable names
- Add JSDoc comments for complex functions

**Good:**
```javascript
const ArtifactCard = ({ file, onRemove }) => {
  const [status, setStatus] = useState('IDLE');
  // Component logic
};
```

**Avoid:**
```javascript
function Card(props) {
  var s = 'IDLE';
  // Legacy patterns
}
```

### CSS/Tailwind

- Use Tailwind utility classes
- Group related utilities
- Use responsive prefixes (sm:, md:, lg:)
- Add custom CSS only when necessary

**Good:**
```jsx
<div className="flex items-center justify-center gap-4 p-4 bg-purple-600 hover:bg-purple-500 transition-colors">
```

**Avoid:**
```jsx
<div className="flex items-center bg-purple-600 transition-colors gap-4 hover:bg-purple-500 p-4 justify-center">
```

### Commit Messages

Use conventional commit format:

- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Formatting, no code change
- `refactor:` Code restructuring
- `perf:` Performance improvements
- `test:` Adding tests
- `chore:` Maintenance tasks

**Examples:**
```
feat: add dark mode toggle
fix: particle animation performance on mobile
docs: update API configuration guide
refactor: simplify image upload logic
```

## 🧪 Testing

### Before Submitting PR

- [ ] Code builds without errors
- [ ] No console errors/warnings
- [ ] Features work as expected
- [ ] Mobile responsive (test on actual device if possible)
- [ ] No performance regressions
- [ ] Documentation updated

### Manual Testing

1. **Desktop Testing**
   - Chrome, Firefox, Safari, Edge
   - Different screen sizes
   - Drag & drop functionality

2. **Mobile Testing**
   - iOS Safari
   - Android Chrome
   - Touch interactions
   - Orientation changes

3. **Performance Testing**
   - Check FPS in DevTools
   - Monitor memory usage
   - Test with multiple images

## 🎨 UI/UX Guidelines

### Design Principles

1. **Atmospheric:** Maintain the dark, cinematic aesthetic
2. **Performance:** 60+ FPS is non-negotiable
3. **Clarity:** UI should be intuitive
4. **Consistency:** Follow existing patterns

### Color Palette

```
Primary: #8b5cf6 (Purple)
Secondary: #10b981 (Emerald)
Accent: #d97706 (Amber)
Background: #0a0a1a (Dark)
```

### Typography

- Headers: `font-mono`, uppercase, wide tracking
- Body: `font-sans`, normal case
- Accents: `font-serif`, italic

## 📱 Mobile Guidelines

- Minimum touch target: 44x44px
- Test on actual devices when possible
- Consider safe area insets for notched displays
- Optimize particle count for mobile

## ⚡ Performance Guidelines

- Keep bundle size minimal
- Use lazy loading for large components
- Optimize images before upload
- Minimize re-renders with React.memo
- Use useCallback for event handlers

**Performance Budget:**
- First Contentful Paint: < 1.5s
- Time to Interactive: < 3.5s
- Bundle size: < 200KB (gzipped)
- FPS: 60+ (desktop), 60+ (mobile)

## 🔐 Security

- Never commit API keys or secrets
- Sanitize user input
- Follow OWASP guidelines
- Report security issues privately

## 📚 Documentation

When adding features, update:
- README.md (if user-facing)
- WIKI.md (for detailed guides)
- Code comments (for complex logic)
- CHANGELOG.md

## 🏷️ Versioning

We follow [Semantic Versioning](https://semver.org/):
- MAJOR: Breaking changes
- MINOR: New features
- PATCH: Bug fixes

## 📜 License

By contributing, you agree that your contributions will be licensed under the same license as the project.

## 🙏 Recognition

Contributors will be recognized in:
- README.md contributors section
- Release notes
- GitHub contributors page

## ❓ Questions?

- Create a [Discussion](https://github.com/anacondy/cinema-scanner-/discussions)
- Ask in [Issues](https://github.com/anacondy/cinema-scanner-/issues)
- Check [Wiki](https://github.com/anacondy/cinema-scanner-/blob/main/WIKI.md)

---

**Thank you for contributing to Cinematic Archives!** 🎬✨
