# Setup Guide

## Quick Start (No Setup Required)

The easiest way to use yrcal is with .ICS file imports:

1. Export your calendar as .ics from Google Calendar, Outlook, or any calendar app
2. Open `yrcal.html` in your browser
3. Click "Import .ICS" and select your file
4. Done! Your events are now visualized

## Google Calendar OAuth Setup (Optional)

If you want direct Google Calendar import without exporting files:

### Step 1: Create a Google Cloud Project

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Click "Select a project" → "New Project"
3. Name it "yrcal" (or anything you like)
4. Click "Create"

### Step 2: Enable Google Calendar API

1. In your project, go to "APIs & Services" → "Library"
2. Search for "Google Calendar API"
3. Click on it and press "Enable"

### Step 3: Create OAuth Credentials

1. Go to "APIs & Services" → "Credentials"
2. Click "Create Credentials" → "OAuth client ID"
3. If prompted, configure the OAuth consent screen:
   - User Type: External
   - App name: yrcal
   - User support email: your email
   - Developer contact: your email
   - Save and continue through the scopes (no changes needed)
   - Add yourself as a test user
4. Back to "Create OAuth client ID":
   - Application type: Web application
   - Name: yrcal
   - Authorized JavaScript origins:
     - `http://localhost`
     - `http://localhost:8000` (if using local server)
     - Add your domain if hosting online
   - Authorized redirect URIs: (leave empty for now)
5. Click "Create"
6. Copy your Client ID

### Step 4: Update yrcal.html

1. Open `yrcal.html` in a text editor
2. Find line ~850 where it says:
   ```javascript
   const GOOGLE_CLIENT_ID = '934690623052-3ris0n11qnjnlhqrtd9u08uda3mo1a8e.apps.googleusercontent.com';
   ```
3. Replace with your Client ID:
   ```javascript
   const GOOGLE_CLIENT_ID = 'YOUR_CLIENT_ID_HERE.apps.googleusercontent.com';
   ```
4. Save the file

### Step 5: Test It

1. Open `yrcal.html` in your browser
2. Click "Import Google Calendar"
3. Sign in with your Google account
4. Grant calendar access
5. Your events should import!

## Hosting Online

If you want to host this online:

1. Update the OAuth credentials in Google Cloud Console with your domain
2. Upload `yrcal.html` to your web server
3. Make sure `.gitignore` prevents committing sensitive files

## Troubleshooting

**"OAuth error" when importing Google Calendar:**
- Make sure you added your domain to Authorized JavaScript origins
- Try using .ICS export instead (works without OAuth setup)

**Events not showing:**
- Check the year selector at the top
- Try importing .ICS files to verify the app works

**Google Calendar import shows 0 events:**
- Check browser console for errors
- Verify the Calendar API is enabled
- Make sure you're a test user in the OAuth consent screen

## Privacy Note

All data stays in your browser's localStorage. Nothing is sent to any server. Your calendar data never leaves your device.
