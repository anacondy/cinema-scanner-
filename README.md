# 🌑 Cinematic Archives - AI Artifact Analyzer

[![GitHub Pages](https://img.shields.io/badge/demo-live-brightgreen)](https://anacondy.github.io/cinema-scanner-/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![React](https://img.shields.io/badge/react-18.2.0-61dafb.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/vite-5.0.8-646cff.svg)](https://vitejs.dev/)

---

## 📑 Table of Contents
- [Live Site](#-live-site)
- [Screenshots](#-screenshots)
- [Features](#-features)
- [About](#-about)
- [Quick Start](#-quick-start)
- [Build & Deploy](#-build--deploy)
- [Platform Builds](#-platform-builds)
- [Key Technologies](#-key-technologies)
- [Development](#-development)
- [Performance](#-performance)
- [Browser Support](#-browser-support)
- [Documentation](#-documentation)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔗 Live Site
**🚀 [https://anacondy.github.io/cinema-scanner-/](https://anacondy.github.io/cinema-scanner-/)**

---

## 📸 Screenshots

### Main Interface
![Main Interface](https://via.placeholder.com/800x450/0a0a1a/8b5cf6?text=Cinematic+Archives+Main+Interface)
*The atmospheric landing page with particle effects and drag-and-drop upload zone*

### Scanning in Progress
![Scanning](https://via.placeholder.com/800x450/0a0a1a/10b981?text=AI+Scanning+In+Progress)
*Real-time AI analysis with visual scanning effects*

### Analysis Results
![Results](https://via.placeholder.com/800x450/0a0a1a/a855f7?text=Analysis+Results+Display)
*Detailed information display with grounded search sources*

---

## ✨ Features

| Feature | Status | Last Tested | Working |
|---------|--------|-------------|---------|
| 🎨 **Atmospheric UI** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🧠 **AI Image Analysis (Gemini)** | ✅ Active | 2025-12-09 | ✅ Yes |
| ⚡ **60+ FPS Performance** | ✅ Active | 2025-12-09 | ✅ Yes |
| 📱 **16:9 Mobile Optimization** | ✅ Active | 2025-12-09 | ✅ Yes |
| 📱 **20:9 Mobile Optimization** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🖱️ **Drag & Drop Upload** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🌐 **Deep Search Mode** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🎭 **Multi-Artifact Support** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🌊 **Particle Animation System** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🔒 **Unrestricted AI Analysis** | ✅ Active | 2025-12-09 | ✅ Yes |
| 📊 **Grounded Search Sources** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🎯 **Responsive Design** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🌓 **Dark Theme** | ✅ Active | 2025-12-09 | ✅ Yes |
| 🔄 **High Refresh Rate Support** | ✅ Active | 2025-12-09 | ✅ Yes |

---

## 🎯 About

**Cinematic Archives** is an immersive, high-performance React application designed to analyze movie posters, game covers, and portraits using Google's Gemini AI. Built with a focus on atmosphere and performance, it features:

- 🎨 **Custom Physics Particle Engine** - "Time Dust" particles with 60fps+ animations
- 🧠 **AI Intelligence** - Multi-modal analysis with Google Gemini 2.5 Flash
- 🌐 **Deep Network Scan** - Integrated Google Search Grounding for verification
- ⚡ **Performance Optimized** - Automatic sync with high-refresh-rate displays (90Hz, 120Hz, 144Hz)
- 📱 **Mobile First** - Optimized for 16:9 and 20:9 aspect ratios
- 🎭 **Atmospheric Design** - Inspired by Donnie Darko / Sci-Fi Thriller aesthetic

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ installed
- A Google Gemini API key ([Get one here](https://makersuite.google.com/app/apikey))

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/anacondy/cinema-scanner-.git
   cd cinema-scanner-
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure API Key**
   
   Create a `.env` file in the root directory:
   ```env
   VITE_GEMINI_API_KEY=your_actual_api_key_here
   ```

4. **Run development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   
   Navigate to `http://localhost:3000`

---

## 📦 Build & Deploy

### Build for Production
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

### Deploy to GitHub Pages
```bash
npm run deploy
```

The site will be automatically deployed to GitHub Pages via GitHub Actions on every push to `main`.

---

## 📱 Platform Builds

### Mobile Apps (Android & iOS)

**Coming Soon!** Native mobile builds will be available in the Releases section.

#### Planned Features:
- 📦 Android APK (Easy installation)
- 📦 iOS IPA (TestFlight compatible)
- 🪟 Windows Desktop App
- 🍎 macOS Desktop App

Check the [Releases](https://github.com/anacondy/cinema-scanner-/releases) page for download links and installation instructions.

---

## 🎨 Key Technologies

- **React 18** - UI framework
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first styling
- **Lucide React** - Icon library
- **Google Gemini AI** - Image analysis
- **Canvas API** - Custom particle system

---

## 🔧 Development

### Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build |
| `npm run deploy` | Deploy to GitHub Pages |

---

## 📊 Performance

- **Target:** 60+ FPS on all devices
- **Optimization:** Request animation frame syncing
- **Mobile:** Adaptive particle count (40 on mobile, 100 on desktop)
- **High Refresh Rate:** Automatic sync with 90Hz, 120Hz, 144Hz displays

---

## 🌐 Browser Support

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | 90+ | ✅ Full |
| Firefox | 88+ | ✅ Full |
| Safari | 14+ | ✅ Full |
| Edge | 90+ | ✅ Full |

---

## 📖 Documentation

For more detailed information, check out:
- 📘 [Wiki Documentation](WIKI.md) - Comprehensive setup guides and tutorials
- 📙 [Build Guide](BUILDS.md) - Platform-specific build instructions
- 📕 [Testing Documentation](TESTING.md) - Test results and benchmarks
- 📗 [Contributing Guide](CONTRIBUTING.md) - How to contribute
- 🏷️ [Release Template](RELEASE_TEMPLATE.md) - Release notes format
- 📋 [Project Overview](PROJECT.md) - Detailed project information
- 🐛 [Issues](https://github.com/anacondy/cinema-scanner-/issues) - Report bugs or request features

---

## ⚠️ Disclaimer

This interface uses Google's Generative AI. Responses are generated by a machine and may occasionally be inaccurate. The "Unrestricted Mode" is enabled for artistic analysis purposes; user discretion is advised.

---

## 📄 License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

**Built with ❤️ and AI**