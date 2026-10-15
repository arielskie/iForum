# Troubleshooting & Frequently Asked Questions

### 1. Why are Post Views and Hearts showing 0?
- **Root Cause**: Firebase Realtime Database has not been initialized or the rules are rejecting writes.
- **Solution**:
  1. Open your Firebase Console and check **Realtime Database → Rules**.
  2. Make sure `.read` and `.write` are set to `true`.
  3. Verify that `databaseURL` in your theme code matches your exact regional database endpoint (e.g. `https://yourproject-default-rtdb.asia-southeast1.firebasedatabase.app`).

---

### 2. Google Sign-In gives `auth/unauthorized-domain` error
- **Root Cause**: The current blog hostname is not whitelisted in Firebase.
- **Solution**:
  1. Go to Firebase Console $\rightarrow$ **Authentication → Settings → Authorized domains**.
  2. Add your full blog address (e.g., `myblog.blogspot.com` and `www.mycustomdomain.com`).

---

### 3. How do I change the Accent Color of the theme?
- **Solution**:
  1. In Blogger Dashboard, go to **Theme → Edit HTML**.
  2. Locate the `:root` CSS block near the top:
     ```css
     :root {
       --accent: #2563eb; /* Change to your brand color hex */
       --purple: #8b5cf6;
     }
     ```
  3. Update `--accent` and save.

---

### 4. Layout editor won't scroll in Blogger
- **Solution**:
  - iForum includes dedicated `<b:template-skin>` overrides to guarantee seamless vertical scrolling inside Blogger's backend admin iframe while keeping the frontend full-viewport layout pristine. Ensure you have not stripped the `<b:template-skin>` section.
