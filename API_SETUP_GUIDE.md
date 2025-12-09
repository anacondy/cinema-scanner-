# 🔑 Gemini API Key Setup Guide

This guide will help you set up your Google Gemini API key for the Cinematic Archives application.

## 📋 Quick Setup (5 Steps)

### Step 1: Get Your API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API key"**
4. Copy the generated API key to your clipboard

### Step 2: Create `.env` File

In the project root directory, create a file named `.env`:

```bash
# On Linux/Mac
touch .env

# On Windows (PowerShell)
New-Item .env
```

### Step 3: Add Your API Key

Open the `.env` file and add this line:

```env
VITE_GEMINI_API_KEY=your_actual_api_key_here
```

Replace `your_actual_api_key_here` with the API key you copied in Step 1.

**Example:**
```env
VITE_GEMINI_API_KEY=AIzaSyC-xxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### Step 4: Restart Development Server

If the dev server is already running, stop it (Ctrl+C) and restart:

```bash
npm run dev
```

### Step 5: Verify Connection

1. Open your browser to `http://localhost:3000`
2. Look at the top-left corner for the status indicator
3. You should see: 🟢 **AI ONLINE**
4. If you see 🔴 **NO_KEY** or 🔴 **INVALID_KEY**, click on it for help

## 🎯 Visual Status Guide

### Status Indicators Explained

| Status | Indicator | Meaning | Action |
|--------|-----------|---------|--------|
| **Online** | 🟢 AI ONLINE | API key is valid and working | Ready to scan! |
| **No Key** | 🔴 AI NO_KEY [CLICK_TO_SETUP] | No API key configured | Click to see setup instructions |
| **Invalid** | 🔴 AI INVALID_KEY [CLICK_TO_SETUP] | API key is invalid or expired | Click for help, get new key |
| **Checking** | 🟡 AI CHECKING | Testing your connection | Please wait... |
| **Offline** | 🟠 AI OFFLINE | Cannot reach API service | Check internet connection |

## 🔧 Troubleshooting

### "AI NO_KEY" after adding .env file

**Problem:** You created the `.env` file but still see NO_KEY status.

**Solution:**
1. Make sure the file is named exactly `.env` (not `.env.txt`)
2. Check that the line starts with `VITE_GEMINI_API_KEY=` (no spaces)
3. Restart the development server completely
4. Clear your browser cache and refresh

### "AI INVALID_KEY" with a valid key

**Problem:** You have a valid API key but status shows INVALID_KEY.

**Solution:**
1. Verify the API key is copied correctly (no extra spaces or newlines)
2. Check that your Google Cloud billing is enabled
3. Try generating a new API key from Google AI Studio
4. Click the "TEST CONNECTION" button in the modal for details

### "AI OFFLINE" status

**Problem:** Status shows OFFLINE even with a valid key.

**Solution:**
1. Check your internet connection
2. Verify you can access https://generativelanguage.googleapis.com in your browser
3. Check if a firewall or ad blocker is blocking the API
4. Wait a moment and try the "TEST CONNECTION" button again

## 🌐 GitHub Pages Deployment

If you're deploying to GitHub Pages:

1. Go to your repository **Settings**
2. Navigate to **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Add:
   - **Name:** `VITE_GEMINI_API_KEY`
   - **Value:** Your Gemini API key
5. The GitHub Actions workflow will use this during deployment

## 🔒 Security Notes

- ✅ Never commit the `.env` file to Git (it's already in `.gitignore`)
- ✅ Never share your API key publicly
- ✅ If you accidentally expose your key, revoke it immediately in Google AI Studio
- ✅ Use repository secrets for GitHub Pages deployment

## ❓ Still Need Help?

1. Click on the status indicator in the app for interactive help
2. Use the **"TEST CONNECTION"** button to verify your setup
3. Check the [README.md](README.md) for more details
4. Open an [issue](https://github.com/anacondy/cinema-scanner-/issues) if problems persist

---

**Built with ❤️ and AI**
