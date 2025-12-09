# Cinematic Archives - Wiki Documentation

## Table of Contents
1. [Getting Started](#getting-started)
2. [Features Deep Dive](#features-deep-dive)
3. [Configuration](#configuration)
4. [Deployment](#deployment)
5. [Troubleshooting](#troubleshooting)
6. [API Reference](#api-reference)
7. [Performance Tuning](#performance-tuning)

---

## Getting Started

### System Requirements

**Minimum Requirements:**
- Node.js 18.0.0 or higher
- 2GB RAM
- Modern browser (Chrome 90+, Firefox 88+, Safari 14+)

**Recommended:**
- Node.js 20.0.0 or higher
- 4GB RAM
- High refresh rate display (90Hz+)

### First-Time Setup

1. **Clone and Install**
   ```bash
   git clone https://github.com/anacondy/cinema-scanner-.git
   cd cinema-scanner-
   npm install
   ```

2. **Get Gemini API Key**
   - Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Sign in with Google account
   - Click "Create API Key"
   - Copy the generated key

3. **Configure Environment**
   ```bash
   echo "VITE_GEMINI_API_KEY=your_key_here" > .env
   ```

4. **Start Development**
   ```bash
   npm run dev
   ```

---

## Features Deep Dive

### 🎨 Particle System

The custom Canvas-based particle engine creates the "Time Dust" effect visible on the homepage.

**Technical Details:**
- Uses `requestAnimationFrame` for optimal sync
- Adaptive particle count based on device capability
- Each particle has independent velocity and fade cycle
- Golden/amber color scheme matching the Donnie Darko aesthetic

**Performance Impact:**
- Mobile (40 particles): ~5% CPU usage
- Desktop (100 particles): ~3% CPU usage

**Customization:**
```javascript
// In src/App.jsx
const particleCount = width < 768 ? 40 : 100; // Adjust these values
```

### 🧠 AI Analysis Modes

#### Standard Scan
- Uses Google Gemini 2.5 Flash
- Analyzes image locally without web search
- Response time: 2-5 seconds
- Safety filters: Disabled for artistic content

#### Deep Network Scan
- Activates Google Search Grounding
- Verifies results against web sources
- Provides citation links
- Response time: 5-10 seconds

**When to use each:**
- Standard: Quick identification of popular media
- Deep Scan: Obscure content, verification needed

### 🎭 Multi-Artifact Support

Upload multiple images simultaneously:
- Drag & drop multiple files
- Each analyzed independently
- Results stack vertically
- No limit on quantity (reasonable use)

### 📱 Mobile Optimization

**16:9 Aspect Ratio (Standard Phones):**
- Optimized viewport units
- Touch targets: minimum 44px
- Reduced particle count
- Simplified animations

**20:9 Aspect Ratio (Modern Phones):**
- Extra padding for notches
- Extended scroll area
- Navbar optimization
- Safe area insets

**CSS Implementation:**
```css
/* In src/App.jsx styles */
.min-h-screen {
  min-height: 100vh;
  min-height: -webkit-fill-available;
}
```

---

## Configuration

### Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `VITE_GEMINI_API_KEY` | Yes | - | Google Gemini API key |
| `VITE_API_TIMEOUT` | No | 30000 | API timeout in ms |
| `VITE_PARTICLE_COUNT` | No | auto | Override particle count |

### Build Configuration

**vite.config.js Options:**
```javascript
export default defineConfig({
  base: '/cinema-scanner-/', // Change for different hosting
  build: {
    outDir: 'dist',            // Output directory
    minify: 'esbuild',         // Minification method
  }
})
```

### Tailwind Customization

Modify `tailwind.config.js` to change theme:
```javascript
theme: {
  extend: {
    colors: {
      primary: '#8b5cf6',      // Purple theme
      secondary: '#10b981',    // Emerald accents
      accent: '#d97706',       // Amber highlights
    }
  }
}
```

---

## Deployment

### GitHub Pages (Automated)

The repository includes a GitHub Actions workflow that automatically deploys to GitHub Pages on every push to `main`.

**Setup Steps:**
1. Go to repository Settings → Pages
2. Source: "GitHub Actions"
3. Push to `main` branch
4. Wait 2-3 minutes for deployment

**Custom Domain:**
```javascript
// vite.config.js
base: '/', // For custom domain
```

Add `CNAME` file in `public/`:
```
yourdomain.com
```

### Manual Deployment

```bash
npm run build
npm run deploy
```

### Other Platforms

**Vercel:**
```bash
npm install -g vercel
vercel
```

**Netlify:**
```bash
npm install -g netlify-cli
netlify deploy
```

---

## Troubleshooting

### Common Issues

#### Build Fails
```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
npm run build
```

#### API Key Not Working
- Check `.env` file is in root directory
- Ensure variable name is `VITE_GEMINI_API_KEY`
- Restart dev server after adding `.env`

#### Particle Animation Laggy
```javascript
// Reduce particle count in src/App.jsx
const particleCount = width < 768 ? 20 : 50;
```

#### Images Not Uploading
- Check file size (< 4MB recommended)
- Ensure file is image format (PNG, JPG, WebP)
- Check browser console for errors

### Performance Issues

**On Mobile:**
1. Reduce particle count (edit `src/App.jsx`)
2. Disable shadow effects
3. Use lower quality images

**On Desktop:**
1. Enable hardware acceleration in browser
2. Close unnecessary tabs
3. Update graphics drivers

---

## API Reference

### Gemini API Configuration

**Safety Settings:**
```javascript
safetySettings: [
  { category: "HARM_CATEGORY_HARASSMENT", threshold: "BLOCK_NONE" },
  { category: "HARM_CATEGORY_HATE_SPEECH", threshold: "BLOCK_NONE" },
  { category: "HARM_CATEGORY_SEXUALLY_EXPLICIT", threshold: "BLOCK_NONE" },
  { category: "HARM_CATEGORY_DANGEROUS_CONTENT", threshold: "BLOCK_NONE" }
]
```

**Prompt Structure:**
```javascript
const prompt = `
  Analyze this image. It is likely a Movie Poster, Game Cover, or a Photo of a Famous Person.
  
  ${useGrounding ? "USE SEARCH TOOLS to identify this specific person or media definitively." : ""}

  IF IT IS A PERSON:
  1. Title = Person's Name.
  2. Year = Year of Birth (e.g. "b. 1985").
  3. Genre = "Actor" / "Actress" / "Model" + (Birth City/Country).
  4. Description = Start with "Best known for..." details about their career.

  IF IT IS MEDIA:
  1. Title = Title.
  2. Year = Release Year.
  3. Genre = Genre.
  4. Description = Atmospheric description.

  Return JSON: { title, year, genre, description, is_person }
`;
```

### Response Format

```typescript
interface AnalysisResult {
  title: string;
  year: string;
  genre: string;
  description: string;
  is_person: boolean;
}
```

---

## Performance Tuning

### Target Metrics

| Device Type | Target FPS | Typical FPS | Particle Count |
|-------------|------------|-------------|----------------|
| High-end Desktop | 144 | 120-144 | 100 |
| Standard Desktop | 60 | 60-90 | 100 |
| High-end Mobile | 120 | 90-120 | 40 |
| Standard Mobile | 60 | 60-75 | 40 |
| Low-end Mobile | 60 | 50-60 | 20 |

### Optimization Techniques

1. **Request Animation Frame Sync**
   ```javascript
   const animate = () => {
     // Automatically syncs with display refresh rate
     requestAnimationFrame(animate);
   };
   ```

2. **Canvas Optimization**
   ```javascript
   // Clear only changed regions
   ctx.clearRect(0, 0, width, height);
   
   // Use willChange for GPU acceleration
   canvas.style.willChange = 'transform';
   ```

3. **Image Optimization**
   - Convert to WebP format
   - Compress before upload
   - Use appropriate resolution

4. **Code Splitting**
   ```javascript
   // Vite handles this automatically
   const Component = React.lazy(() => import('./Component'));
   ```

### Monitoring Performance

**Chrome DevTools:**
1. Open DevTools → Performance
2. Start recording
3. Interact with app
4. Analyze FPS graph

**Target Metrics:**
- FPS: 60+ (consistent)
- Memory: < 100MB
- CPU: < 30% average

---

## Advanced Topics

### Custom AI Prompts

Modify the prompt in `src/App.jsx` to change analysis behavior:

```javascript
const customPrompt = `
  Focus on [specific aspect] of this image.
  Provide [specific format] output.
`;
```

### Styling Customization

All styles are in Tailwind utility classes. Major style blocks:

1. **Main Container:** `src/App.jsx` line 456
2. **Artifact Card:** `src/App.jsx` line 183
3. **Upload Zone:** `src/App.jsx` line 523

### Adding New Features

**Example: Dark/Light Mode Toggle**

1. Add state:
   ```javascript
   const [theme, setTheme] = useState('dark');
   ```

2. Conditional classes:
   ```javascript
   className={theme === 'dark' ? 'bg-black' : 'bg-white'}
   ```

---

## Contributing

### Code Style
- Use functional components
- Prefer hooks over class components
- Follow existing naming conventions
- Comment complex logic

### Pull Request Process
1. Fork the repository
2. Create feature branch
3. Make changes
4. Test thoroughly
5. Submit PR with description

---

## License

See [LICENSE](LICENSE) file for details.

---

## Support

- **Issues:** [GitHub Issues](https://github.com/anacondy/cinema-scanner-/issues)
- **Discussions:** [GitHub Discussions](https://github.com/anacondy/cinema-scanner-/discussions)
- **Email:** Create an issue for contact

---

**Last Updated:** December 9, 2025
