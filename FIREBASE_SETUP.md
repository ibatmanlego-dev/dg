# Firebase Cloud Sync Setup Guide

VibeTracker includes **free cloud sync** functionality using Google Firebase. This allows you to sync your data across devices and keep it backed up securely.

## 🆓 **What's Free with Firebase Spark Plan**

- **Authentication**: 10,000 monthly active users
- **Firestore Database**: 1 GiB storage
- **50,000 document reads per day**
- **20,000 document writes per day**
- **20,000 document deletes per day**
- **Real-time sync across devices**
- **No credit card required**

This is more than enough for personal use!

## 🚀 **Quick Setup (5 minutes)**

### 1. Create Firebase Project
1. Go to [Firebase Console](https://console.firebase.google.com)
2. Click "Add project" 
3. Enter project name (e.g., "vibetracker-personal")
4. Continue with default settings
5. Create project

### 2. Enable Authentication
1. In your project dashboard, go to "Authentication" 
2. Click "Get started"
3. Select "Email/Password" provider
4. Enable it and save

### 3. Enable Firestore Database
1. Go to "Firestore Database" in left menu
2. Click "Create database"
3. Choose "Start in test mode" (allows read/write access)
4. Select a location (choose closest to you)
5. Create database

### 4. Get Your Config
1. Click the gear icon ⚙️ next to "Project Overview"
2. Select "Project settings"
3. Scroll down to "Firebase config snippet"
4. Copy the config object

### 5. Update VibeTracker
1. Open `src/lib/firebase.ts` in your project
2. Replace the demo config with your real config:
```javascript
const firebaseConfig = {
  apiKey: "your-api-key-here",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789",
  appId: "your-app-id"
}
```

## 🎉 **You're All Set!**

Now you can:
- Login with email/password in Settings → Account & Cloud Sync
- Your data will automatically sync across devices
- Access your data from any device with VibeTracker
- Never worry about losing your data again!

## 📱 **Using Cloud Sync**

1. **Login**: Go to Settings → Account & Cloud Sync → Login
2. **Enter**: Your email and password
3. **Sync**: Data automatically syncs when you make changes
4. **Status**: View sync status and last sync time
5. **Manual Sync**: Click "Sync Now" to force sync

## 🔧 **Troubleshooting**

### "Firebase not initialized" Error
- Make sure you've updated the config in `src/lib/firebase.ts`
- Check that your API keys are correct

### Can't Login
- Ensure Email/Password auth is enabled in Firebase console
- Check your internet connection
- Verify email format is correct

### Sync Not Working
- Check your Firestore database rules (test mode should work)
- Ensure you're logged in correctly
- Try manual sync with "Sync Now" button

## 📊 **Monitoring Usage**

You can monitor your Firebase usage in the console:
- Go to "Usage and billing"
- Check Authentication and Firestore usage
- The free tier is very generous for personal use

## 🔒 **Privacy & Security**

- Your data is stored in your personal Firebase project
- Only you have access with your login credentials
- Data is encrypted in transit and at rest
- You can delete all data anytime in Firebase console

## 💡 **Pro Tips**

1. **Backup Locally**: Also use the Export Data feature as extra backup
2. **Strong Password**: Use a strong password for your Firebase account
3. **Multiple Devices**: Install VibeTracker on multiple devices with same login
4. **Regular Sync**: Data syncs automatically, but you can also sync manually

---

**Need Help?** 
- Check the [Firebase Documentation](https://firebase.google.com/docs)
- Review your Firebase console settings
- Make sure all steps above were completed correctly