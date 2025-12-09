**🚀 Live Demo:** [https://anacondy.github.io/cinema-scanner-/](https://anacondy.github.io/cinema-scanner-/)

---

# 🌑 Cinematic Archives - AI Artifact Analyzer

[![GitHub Pages](https://img.shields.io/badge/demo-live-brightgreen)](https://anacondy.github.io/cinema-scanner-/)
[![Deploy](https://github.com/anacondy/cinema-scanner-/actions/workflows/deploy.yml/badge.svg)](https://github.com/anacondy/cinema-scanner-/actions/workflows/deploy.yml)
[![CI](https://github.com/anacondy/cinema-scanner-/actions/workflows/ci.yml/badge.svg)](https://github.com/anacondy/cinema-scanner-/actions/workflows/ci.yml)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![React](https://img.shields.io/badge/react-18.2.0-61dafb.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/vite-5.0.8-646cff.svg)](https://vitejs.dev/)

> **🔄 CI/CD Status:** Click the workflow badges above to check build and deployment status. See [WORKFLOWS.md](WORKFLOWS.md) for detailed monitoring instructions.

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

> **📖 Need help setting up your API key?** See the [API Setup Guide](API_SETUP_GUIDE.md) for detailed step-by-step instructions with troubleshooting.

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

3. **Configure API Key** ⚠️ **IMPORTANT**
   
   The application **requires** a valid Gemini API key to function. Follow these steps:
   
   **Step 1:** Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Sign in with your Google account
   - Click "Create API key"
   - Copy the generated key
   
   **Step 2:** Create a `.env` file in the root directory:
   ```bash
   # On Linux/Mac
   touch .env
   
   # On Windows (PowerShell)
   New-Item .env
   ```
   
   **Step 3:** Add your API key to the `.env` file:
   ```env
   VITE_GEMINI_API_KEY=your_actual_api_key_here
   ```
   
   **Example `.env` file:**
   ```env
   # Replace with your actual API key from Google AI Studio
   VITE_GEMINI_API_KEY=AIzaSyC-xxxxxxxxxxxxxxxxxxxxxxxxxxx
   ```
   
   ⚠️ **Security Note:** Never commit the `.env` file to version control. It's already in `.gitignore`.

4. **Run development server**
   ```bash
   npm run dev
   ```

5. **Verify API Connection**
   
   - Open your browser and navigate to `http://localhost:3000`
   - Look at the top-left corner for the API status indicator:
     - 🟢 **AI ONLINE** = API key is valid and working
     - 🔴 **AI NO_KEY** = No API key found (click to see setup instructions)
     - 🔴 **AI INVALID_KEY** = API key is invalid or expired
     - 🟡 **AI CHECKING** = Testing connection
   - If you see "NO_KEY" or "INVALID_KEY", click on the status to see detailed setup instructions

6. **Test the Connection**
   
   - If the API setup modal appears, click "TEST CONNECTION" to verify your API key
   - Once you see "AI ONLINE", you're ready to scan images!

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

#### Option 1: Automatic Deployment (Recommended)
The site will be automatically deployed to GitHub Pages via GitHub Actions on every push to `main`.

**Setup Required:**
1. Go to your repository **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret**
3. Add a secret with:
   - **Name:** `VITE_GEMINI_API_KEY`
   - **Value:** Your Google Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
4. Push to `main` branch to trigger automatic deployment

#### Option 2: Manual Deployment
```bash
npm run deploy
```

**Note:** For manual deployment, ensure your `.env` file contains the API key before building.

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

## 🔧 Troubleshooting

### API Key Setup Issues

The application includes an **interactive setup wizard** to help you configure your API key:

#### Visual Status Indicators

When you open the application, look at the top-left corner for the API status:

- 🟢 **AI ONLINE** → Everything is working! Ready to scan images
- 🔴 **AI NO_KEY [CLICK_TO_SETUP]** → Click to see setup instructions
- 🔴 **AI INVALID_KEY [CLICK_TO_SETUP]** → Your API key is invalid or expired
- 🟡 **AI CHECKING** → Testing your connection
- 🟠 **AI OFFLINE** → Cannot reach the API service (check internet)

#### Step-by-Step Fix

If you see **NO_KEY** or **INVALID_KEY**:

1. **Click on the status indicator** in the top-left corner
2. A setup modal will appear with detailed instructions
3. Follow the 5-step guide in the modal:
   - Get your API key from Google AI Studio
   - Create a `.env` file
   - Add `VITE_GEMINI_API_KEY=your_key`
   - Restart the dev server
   - Refresh the page
4. Click the **"TEST CONNECTION"** button to verify
5. You should see "API CONNECTION SUCCESSFUL" ✅

### AI Scanning Not Working

If you see error messages like "SECURITY_CLEARANCE_FAILED" or "AI_SERVICE_OFFLINE", follow these steps:

1. **Check API Key Configuration**
   - **Local Development:** Ensure `.env` file exists with `VITE_GEMINI_API_KEY=your_key_here`
   - **GitHub Pages:** Verify the secret is set in repository Settings → Secrets → Actions
   - Get a valid API key from [Google AI Studio](https://makersuite.google.com/app/apikey)

2. **Verify API Key Validity**
   - Test your API key at [Google AI Studio](https://aistudio.google.com/)
   - Ensure billing is enabled on your Google Cloud account (free tier available)
   - Check that the API key has not expired

3. **Check Internet Connection**
   - The app requires an active internet connection to reach Google's AI service
   - Check browser console (F12) for network errors

4. **Common Error Messages**
   - **"NO_API_KEY_CONFIGURED"**: Create a `.env` file or set the GitHub secret
   - **"AUTHENTICATION_FAILED" (401)**: Invalid or expired API key
   - **"ACCESS_FORBIDDEN" (403)**: Check API permissions and billing
   - **"NETWORK_ERROR"**: Internet connection issue or service temporarily unavailable
   - **"REQUEST_TIMEOUT"**: Service is experiencing high load, try again

5. **Status Indicator**
   - Look for the status indicator in the top-left corner:
     - 🟢 **AI ONLINE**: Service is working properly
     - 🟡 **AI CHECKING**: Testing connection
     - 🔴 **AI OFFLINE**: Service unavailable or API key invalid
     - 🔴 **AI NO_KEY**: No API key configured

### Still Having Issues?

- Check [GitHub Issues](https://github.com/anacondy/cinema-scanner-/issues) for similar problems
- Create a new issue with error details from browser console (F12)

---

## 📖 Documentation

For more detailed information, check out:
- 🔑 [**API Setup Guide**](API_SETUP_GUIDE.md) - Step-by-step Gemini API key configuration ⭐ **Start here!**
- 📘 [Wiki Documentation](WIKI.md) - Comprehensive setup guides and tutorials
- 📙 [Build Guide](BUILDS.md) - Platform-specific build instructions
- 📕 [Testing Documentation](TESTING.md) - Test results and benchmarks
- 📗 [Contributing Guide](CONTRIBUTING.md) - How to contribute
- 🔄 [Workflows Guide](WORKFLOWS.md) - CI/CD workflows and status verification
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