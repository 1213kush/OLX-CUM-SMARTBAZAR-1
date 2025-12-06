# OLX-CUM-SMARTBAZAR-1 (OLX CLONE )
SmartBazar is a smart online marketplace that offers a fast and convenient shopping experience. Users can explore groceries, essentials, electronics, and fashion in one place. With secure payments, easy navigation, and quick delivery, SmartBazar makes everyday shopping simple and reliable.

# How to Run SmartBazar (Frontend + Firebase)

SmartBazar is a frontend-only application that uses **Firebase** for authentication, database, and storage.
Follow the steps below to run the project locally.

---

## Prerequisites

* Node.js (v16+ recommended)
* npm or yarn
* A Firebase project (free tier works)

---

## 1. Clone the Project

```bash
git clone https://github.com/your-username/smartbazar.git
cd smartbazar
```

---

## 2. Install Dependencies

```bash
npm install
# or
yarn
```

---

## 3. Create a Firebase Project

1. Go to **Firebase Console** → [https://console.firebase.google.com](https://console.firebase.google.com)

2. Click **Add Project** → Create a new project

3. Enable the following services (as per your app):

   * **Authentication**
   * **Cloud Firestore** or **Realtime Database**
   * **Firebase Storage**

4. Go to **Project Settings → General → Your Apps**

5. Add a web app and copy the Firebase config object.

---

## 4. Add Firebase Credentials

Inside the project, create a new file:

```
src/firebaseConfig.js
```

Paste your own Firebase config:

```javascript
// Your Firebase Web App Credentials
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};

export default firebaseConfig;
```

> Make sure **NOT** to commit private keys if the repo is public.
> Add this file to `.gitignore` if needed.

---

## 5. Start the Development Server

```bash
npm start
# or
yarn start
```

The app will open at:

```
http://localhost:3000
```

---

## 6. Folder Structure (Example)

```
smartbazar/
│── src/
│   ├── components/
│   ├── pages/
│   ├── firebaseConfig.js
│   ├── App.js
│   └── index.js
│── public/
│── package.json
```

---

## 7. Deployment (Optional)

You can deploy SmartBazar to:

### Firebase Hosting

```bash
firebase login
firebase init
firebase deploy
```

### Or any platform:

* Vercel
* Netlify
* GitHub Pages

Just make sure to include your Firebase credentials.

---

## Troubleshooting

### Error: *Firebase: Missing or invalid credentials*

* Check your `firebaseConfig.js` values.
* Ensure you copied the exact keys from Firebase Console.

### App not loading data

* Ensure Firestore rules allow read/write for development.
* Example dev rule (not for production):

```
allow read, write: if true;
```

---

## That’s it!

Your SmartBazar app is now running with Firebase as backend.
