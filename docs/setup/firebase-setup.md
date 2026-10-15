# Firebase Realtime Database & Authentication Setup

Because Blogger is a static blogging CMS, it does not provide native API endpoints for dynamic real-time post views, user-submitted heart reactions, or community rep scores. 

**iForum** seamlessly bridges this with **Google Firebase** (Free Spark Plan).

---

## ⚡ Step 1: Create a Free Firebase Project
1. Open the [Firebase Console](https://console.firebase.google.com/).
2. Click **Add project** (or *Create a project*).
3. Name your project (e.g., `AbeFilm-Forum`) and click **Continue**.
4. You may uncheck Google Analytics for faster initialization, then click **Create project**.
5. Once ready, click **Continue** to open the dashboard.

---

## 🔑 Step 2: Register Web App & Retrieve Config Keys
1. In your project dashboard, click the Web icon (`</>`) to add Firebase to your web app.
2. Enter an App nickname (e.g., `iForum Web`) and click **Register app**.
3. You will receive a code snippet containing `firebaseConfig`. Copy the object keys:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyBxxxxxxxxxxxxxxxxxxxxxxxx",
  authDomain: "your-forum-project.firebaseapp.com",
  databaseURL: "https://your-forum-project-default-rtdb.firebaseio.com",
  projectId: "your-forum-project",
  storageBucket: "your-forum-project.firebasestorage.app",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef123456"
};
```

---

## 🗄️ Step 3: Enable Realtime Database & Rules
1. In the left navigation, click **Build → Realtime Database** (or search "Realtime Database" at the top).
2. Click **Create Database**.
3. Select your closest database region (e.g., `United States` or `Singapore`) and click **Next**.
4. Choose **Start in test mode** and click **Enable**.
5. Click on the **Rules** tab at the top.
6. Replace the existing JSON rules with the optimized iForum rules:

```json
{
  "rules": {
    ".read": true,
    ".write": true,
    "users": {
      ".indexOn": ["points", "name"]
    },
    "posts": {
      ".indexOn": ["views", "hearts"]
    }
  }
}
```
7. Click **Publish**.

---

## 👤 Step 4: Configure Google Authentication & Authorized Domains
1. In the left sidebar, click **Build → Authentication**.
2. Click **Get Started** and navigate to the **Sign-in method** tab.
3. Click on **Google**, enable the toggle switch, enter your support email, and click **Save**.
4. Click on the **Settings** tab at the top of Authentication.
5. In the left column, click **Authorized domains**.
6. Click **Add domain** and register:
   - Your blogspot address: `yourblog.blogspot.com`
   - Your custom domain (if applicable): `forum.yourdomain.com` or `www.yourdomain.com`

> [!IMPORTANT]
> If you omit adding your domain to Authorized Domains, users clicking Google Sign-In will receive an `auth/unauthorized-domain` popup error.

---

## 📝 Step 5: Insert Keys into the Theme
1. In Blogger Dashboard, open **Theme → Edit HTML**.
2. Scroll to the bottom of the document right before `</body>`.
3. Locate `const firebaseConfig = { ... }`.
4. Replace the sample placeholder strings with your actual Firebase project keys.
5. Click the **Save** icon.
