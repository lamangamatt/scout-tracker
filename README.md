# Scout Tracker ⚾

A mobile-friendly baseball pitch tracking app for high school and youth baseball teams. Track pitches during games, analyze pitcher tendencies, and manage bullpen sessions.

## 🎯 Features

- **Data Entry (entry.html)**: Log pitches with type, location, velocity, and results
- **Coach View (coach.html)**: Real-time predictions and insights for coaching staff
- **Bullpen Tracker (bullpen.html)**: Track bullpen sessions with velocity and command ratings

## 🚀 Quick Start

### Option 1: GitHub Pages (Recommended)

1. Fork this repository
2. Enable GitHub Pages in Settings → Pages → Source: `main` branch
3. Access at `https://[username].github.io/scout-tracker/`

### Option 2: Local Testing

Just open any HTML file in your browser - no server required!

```bash
# Clone the repo
git clone https://github.com/lamangamatt/scout-tracker.git
cd scout-tracker

# Open in browser
open entry.html  # macOS
start entry.html # Windows
```

## 📱 Using the App

### First Time Setup

1. Open any of the HTML files (entry.html, coach.html, or bullpen.html)
2. Enter a **team code** (e.g., `bingham2026` or `miners-varsity`)
3. Use the same team code across all devices to share data

### Team Codes

- Team codes keep your data separate from other teams
- Only lowercase letters, numbers, and hyphens allowed
- Minimum 3 characters
- Example codes: `bingham2026`, `trojans-jv`, `team-demo`

### Data Sync

Currently data syncs via:
- **localStorage**: Works on the same device/browser
- **Firebase** (optional): Real-time sync across devices

## 🔥 Firebase Setup (Optional)

For real-time sync across multiple devices:

### 1. Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project (e.g., `scout-tracker-demo`)
3. Enable Realtime Database in Build → Realtime Database

### 2. Get Your Config

In Project Settings → General → Your apps → Web app:

```javascript
const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    databaseURL: "https://your-project-default-rtdb.firebaseio.com",
    projectId: "your-project",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "123456789",
    appId: "your-app-id"
};
```

### 3. Update entry.html

Replace the Firebase config section (around line 760) with your config.

### 4. Deploy Security Rules

In Firebase Console → Realtime Database → Rules, paste the contents of `firebase-rules.json`:

```json
{
  "rules": {
    "teams": {
      "$teamCode": {
        ".read": true,
        ".write": true
      }
    },
    ".read": false,
    ".write": false
  }
}
```

Click "Publish" to apply.

## 🌐 Hosting Options

### Free Options

| Option | URL Format | Notes |
|--------|------------|-------|
| GitHub Pages | `username.github.io/scout-tracker` | Free, easy setup |
| Netlify | `your-site.netlify.app` | Free tier available |
| Vercel | `your-site.vercel.app` | Free tier available |
| Firebase Hosting | `your-project.web.app` | Free tier available |

### Custom Domain (Paid)

To use a custom domain like `scouttracker.com`:
1. Purchase domain (~$10-15/year from Namecheap, Google Domains, etc.)
2. Configure DNS to point to your hosting provider
3. Enable HTTPS (usually automatic with GitHub Pages, Netlify, etc.)

See `DOMAIN-OPTIONS.md` for detailed instructions.

## 📁 File Structure

```
scout-tracker/
├── entry.html          # Main data entry app
├── coach.html          # Coach view with predictions
├── bullpen.html        # Bullpen session tracker
├── firebase-rules.json # Security rules for Firebase
├── README.md           # This file
└── DOMAIN-OPTIONS.md   # Hosting/domain documentation
```

## 🔧 Troubleshooting

### Data not syncing between devices?

- Make sure you're using the **same team code** on all devices
- If using Firebase, verify your database URL and rules are correct
- Clear browser cache and try again

### Can't see my data after switching browsers?

Data is stored in localStorage by default, which is browser-specific. For cross-device sync, set up Firebase.

### Team code won't accept?

- Must be at least 3 characters
- Only lowercase letters (a-z), numbers (0-9), and hyphens (-) allowed
- No spaces or special characters

## 📄 License

MIT License - feel free to use, modify, and share!

## 🤝 Contributing

Pull requests welcome! For major changes, please open an issue first.

---

Built with ❤️ for baseball
