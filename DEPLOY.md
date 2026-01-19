# Deployment Instructions

## Step 1: Create the GitHub Repository

1. Go to https://github.com/new
2. Repository name: `yrcal`
3. Description: "Your year at a glance — privacy-first calendar visualization"
4. Choose Public or Private
5. **DO NOT** initialize with README (we already have one)
6. Click "Create repository"

## Step 2: Push Your Code

Run these commands in your terminal:

```bash
# Initialize git repository
git init

# Add all files (sensitive files are excluded by .gitignore)
git add .

# Create first commit
git commit -m "Initial commit: yrcal - year at a glance calendar"

# Add your GitHub repository as remote
git remote add origin https://github.com/z0l0/yrcal.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 3: Verify

1. Go to https://github.com/z0l0/yrcal
2. Verify that `client_secret_*.json` is NOT in the repository
3. Check that README.md displays correctly

## Step 4: Enable GitHub Pages (Optional)

To host the app for free on GitHub Pages:

1. Go to your repository settings
2. Navigate to "Pages" in the sidebar
3. Source: Deploy from a branch
4. Branch: main, folder: / (root)
5. Click Save
6. Your app will be live at: `https://z0l0.github.io/yrcal/yrcal.html`

**Note:** You'll need to update your Google OAuth credentials to include this URL in the authorized JavaScript origins.

## Security Checklist

Before pushing, verify:
- [ ] `.gitignore` is in place
- [ ] `client_secret_*.json` is listed in `.gitignore`
- [ ] No API keys or secrets in the code
- [ ] README.md has setup instructions

## Updating Your Repository

After making changes:

```bash
git add .
git commit -m "Description of your changes"
git push
```

## Removing Sensitive Files (If Accidentally Committed)

If you accidentally committed sensitive files:

```bash
# Remove from git history
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch client_secret_*.json" \
  --prune-empty --tag-name-filter cat -- --all

# Force push
git push origin --force --all
```

Then immediately rotate your Google OAuth credentials in the Cloud Console.
