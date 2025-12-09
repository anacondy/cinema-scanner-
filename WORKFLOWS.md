# GitHub Actions Workflows - Status and Verification Guide

## 🔄 Configured Workflows

This repository has two main GitHub Actions workflows configured for CI/CD:

### 1. **Deploy Workflow** (`deploy.yml`)
**Purpose:** Automatically deploys the site to GitHub Pages when changes are merged to `main`.

**Trigger:** 
- Push to `main` branch
- Manual trigger via workflow_dispatch

**Status:** 
[![Deploy](https://github.com/anacondy/cinema-scanner-/actions/workflows/deploy.yml/badge.svg)](https://github.com/anacondy/cinema-scanner-/actions/workflows/deploy.yml)

**Jobs:**
1. **Build**
   - Checkout code
   - Setup Node.js 20
   - Install dependencies with npm ci
   - Build production bundle
   - Upload build artifacts to GitHub Pages

2. **Deploy**
   - Deploy artifacts to GitHub Pages
   - Set environment URL

**Expected Outcome:** Site deployed to https://anacondy.github.io/cinema-scanner-/

---

### 2. **CI Workflow** (`ci.yml`)
**Purpose:** Runs continuous integration checks on pull requests and branches (excluding main).

**Trigger:**
- Pull requests to `main`
- Push to any branch except `main`
- Manual trigger via workflow_dispatch

**Status:**
[![CI](https://github.com/anacondy/cinema-scanner-/actions/workflows/ci.yml/badge.svg)](https://github.com/anacondy/cinema-scanner-/actions/workflows/ci.yml)

**Jobs:**
1. **Build & Test**
   - Builds the project
   - Verifies build output exists
   - Uploads build artifacts
   - ✅ Pass criteria: Build completes without errors

2. **Lint Check**
   - Checks for console.log statements (warning only)
   - ✅ Pass criteria: No blocking errors

3. **Security Audit**
   - Runs npm audit for vulnerabilities
   - ✅ Pass criteria: No moderate+ vulnerabilities in production deps

4. **Bundle Size Check**
   - Analyzes bundle size
   - Reports JS and CSS sizes
   - ⚠️ Warns if JS bundle > 200KB
   - ✅ Pass criteria: Bundle builds successfully

5. **Summary**
   - Aggregates all job results
   - ✅ Pass criteria: Build & Test must pass

---

## 📊 How to Check Workflow Status

### Method 1: GitHub UI

1. **Go to the Actions tab:**
   - Visit: https://github.com/anacondy/cinema-scanner-/actions

2. **View workflow runs:**
   - See all workflow runs listed chronologically
   - Green checkmark ✅ = Success
   - Red X ❌ = Failed
   - Yellow circle 🟡 = In progress

3. **Click on a workflow run to see details:**
   - View each job's logs
   - Check which steps passed/failed
   - Download artifacts if available

### Method 2: README Badges

The README.md file shows real-time status badges:

- **Deploy Badge:** Shows deployment status
- **CI Badge:** Shows CI pipeline status

Click any badge to see the full workflow history.

### Method 3: Pull Request Checks

When you create or update a pull request:

1. **Status checks appear at the bottom:**
   - You'll see "All checks have passed" or "Some checks failed"
   - Each workflow job is listed separately

2. **Required checks:**
   - CI workflow must pass before merging
   - Deploy workflow runs after merge

3. **Click "Details" next to any check:**
   - Opens the workflow run logs
   - Shows exactly what passed or failed

---

## ✅ Verification Steps Before Merging

### Step 1: Check CI Workflow
1. Go to: https://github.com/anacondy/cinema-scanner-/actions/workflows/ci.yml
2. Find the latest run for your branch
3. Verify all jobs are green ✅
4. If any job fails, click to view logs and fix issues

### Step 2: Review Build Artifacts
1. In the CI workflow run, go to "Build & Test" job
2. Scroll to "Upload build artifacts" step
3. Download artifacts to inspect if needed

### Step 3: Check Bundle Size
1. In the CI workflow run, go to "Bundle Size Check" job
2. Review the bundle size report
3. Ensure JS bundle is under 200KB (threshold)

### Step 4: Verify Security
1. In the CI workflow run, go to "Security Audit" job
2. Check for any vulnerabilities
3. No moderate+ vulnerabilities should exist

### Step 5: Ready to Merge
If all above checks pass:
- ✅ CI workflow shows green checkmark
- ✅ All jobs completed successfully
- ✅ No security vulnerabilities
- ✅ Bundle size is acceptable

**You're ready to merge!**

---

## 🚀 Post-Merge Verification

After merging to `main`:

1. **Monitor Deploy Workflow:**
   - Go to: https://github.com/anacondy/cinema-scanner-/actions/workflows/deploy.yml
   - Watch the deployment progress
   - Should complete in 2-3 minutes

2. **Verify Deployment:**
   - Visit: https://anacondy.github.io/cinema-scanner-/
   - Check that changes are live
   - Test functionality on the live site

3. **Check Environment:**
   - Go to repository Settings → Environments
   - Click "github-pages"
   - See deployment history and URL

---

## 🔧 Troubleshooting

### CI Workflow Fails

**Build & Test fails:**
```bash
# Run locally to reproduce:
npm ci
npm run build
```

**Security Audit fails:**
```bash
# Check vulnerabilities:
npm audit --production

# Fix if possible:
npm audit fix
```

**Bundle too large:**
```bash
# Analyze bundle:
npm run build
du -h dist/assets/*.js
```

### Deploy Workflow Fails

**Common issues:**
1. GitHub Pages not enabled
   - Go to Settings → Pages
   - Source: GitHub Actions

2. Permissions issue
   - Workflow has correct permissions in deploy.yml
   - Check repository settings

3. Build fails
   - Check if it passes in CI first
   - Review deploy workflow logs

---

## 📝 Workflow Files Location

All workflow files are in `.github/workflows/`:
- `deploy.yml` - Deployment workflow
- `ci.yml` - Continuous integration workflow

---

## 🎯 Quick Reference

| Workflow | When | Purpose | Required |
|----------|------|---------|----------|
| CI | PR & branch push | Test & validate | ✅ Yes |
| Deploy | Push to main | Deploy to Pages | ✅ Yes |

---

## 📞 Getting Help

If workflows fail:
1. Check the workflow logs for error messages
2. Review the troubleshooting section above
3. Run the commands locally to reproduce
4. Check [CONTRIBUTING.md](CONTRIBUTING.md) for development setup

---

**Last Updated:** December 9, 2025
**Status:** ✅ All workflows configured and operational
