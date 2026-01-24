# Firebase Setup Guide

## Step 1: Enable Firebase Realtime Database

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Select your project: **flamingorhapsodyinfo**
3. In the left sidebar, click **Build** → **Realtime Database**
4. Click **Create Database**
5. Choose a location (e.g., **us-central1**)
6. Start in **test mode** (we'll add security rules next)
7. Click **Enable**

## Step 2: Get Your Firebase Configuration

1. In Firebase Console, click the **gear icon** → **Project settings**
2. Scroll down to **Your apps** section
3. If you don't have a web app:
   - Click **Add app** → **Web** (</> icon)
   - Register app with nickname: "Flamingo Rhapsody Web"
   - Click **Register app**
4. Copy the `firebaseConfig` object

## Step 3: Update index.html

1. Open `public/index.html`
2. Find the Firebase configuration section (around line 586)
3. Replace the placeholder config with your actual config:

```javascript
const firebaseConfig = {
  apiKey: "YOUR_ACTUAL_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  databaseURL: "https://YOUR_PROJECT_ID-default-rtdb.firebaseio.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

## Step 4: Deploy Security Rules

1. In your terminal, navigate to your project directory
2. Run: `firebase deploy --only database`
3. This will deploy the rules from `database.rules.json`

## Step 5: Test the Feature

1. Deploy your site: `firebase deploy --only hosting`
2. Open your site in two different browsers
3. Click the cheer button in one browser
4. Verify the count updates in both browsers in real-time
5. Refresh the page and verify the count persists

## Security Rules Explained

The `database.rules.json` file contains:

- **Read access**: Anyone can read the cheer count
- **Write access**: Users can only write their own cheer once (prevents spam)
- **No deletion**: Users cannot delete or modify existing cheers

## Troubleshooting

**Error: "Permission denied"**
- Make sure you've deployed the database rules
- Check that the databaseURL in your config matches your database

**Count not updating**
- Check browser console for errors
- Verify Firebase config is correct
- Make sure Realtime Database is enabled in Firebase Console

**Multiple cheers from same user**
- Clear localStorage: `localStorage.clear()`
- This will generate a new user ID
