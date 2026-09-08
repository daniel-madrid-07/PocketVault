<div align="center">

# PocketVault

**A modern web app for managing and sharing files with Firebase.**

[**Live demo →**](https://pocketvault.space)

</div>

---

## What it does

PocketVault is a web application for storing and sharing files, built on Firebase. It authenticates users with Google, applies per-user storage quotas, and automatically removes files after they expire.

## Features

- Google authentication
- Secure file storage
- Per-user differentiated quotas
- Automatic deletion of expired files
- Modern interface with a custom cursor

## Installation / Usage

### Prerequisites

- A Firebase account
- Node.js (for local development)

### Installation steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/danielmadridg/PocketVault.git
   cd PocketVault
   ```

2. **Configure Firebase**
   - Copy `firebase-config.example.js` to `firebase-config.js`
   - Edit `firebase-config.js` with your Firebase credentials:
     - Go to [Firebase Console](https://console.firebase.google.com)
     - Select your project
     - Go to **Project Settings** > **Your apps**
     - Copy the configuration into the `FIREBASE_CONFIG` object

3. **Create `.firebaserc`**
   ```json
   {
     "projects": {
       "default": "your-project-id"
     }
   }
   ```

4. **Deploy with Firebase**
   ```bash
   npm install -g firebase-tools
   firebase login
   firebase deploy
   ```

### Customizable configuration

In `app.js`, you can adjust:

- `EXPIRY_DAYS`: Days before files are automatically deleted (default: 7)
- `MAX_FILE_MB`: Maximum size per file in MB (default: 100)
- `OWNER_EMAIL`: Owner's email (for the special quota)
- `OWNER_QUOTA_MB`: Owner's quota in MB (default: 4500)
- `GUEST_QUOTA_MB`: Quota for other users in MB (default: 200)
- `SECRET_PASSWORD_HASH`: SHA256 hash of the password for the hidden section

### Security

- Firebase credentials (`app.js` and `.firebaserc`) are excluded from the repository
- Create these files locally with your own credentials
- **Never commit sensitive data**

## Tech stack

- Firebase (Authentication, Hosting, Firestore, Storage)
- Node.js / firebase-tools (deployment tooling)
- HTML, CSS, JavaScript (app.js, index.html, styles.css)
- GitHub Actions (Firebase Hosting deployment on push to `main`)

## License

See [LICENSE](LICENSE).
