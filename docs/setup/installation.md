# Installation & Blogger Theme Setup

This guide walks you through installing the **iForum Premium** Blogger template and ensuring all native layout components are ready.

---

## 📋 Requirements
- A Google Account with access to [Blogger Dashboard](https://www.blogger.com).
- An active or new Blogger blog.
- The `iForum Premium.xml` file (from your purchased product package).

---

## 🚀 Step 1: Install the Theme File

You can install the theme using either **Restore** (recommended for beginners) or **Edit HTML** (recommended if preserving custom tags).

### Method A: Restore (Clean Install)
1. Log into your [Blogger Dashboard](https://www.blogger.com).
2. Select your blog from the top-left dropdown.
3. In the left navigation menu, click **Theme**.
4. Click the three vertical dots (or the downward chevron) next to the orange **Customize** button.
5. Select **Restore**.
6. Click **Upload** and browse to your downloaded package folder:
   - Select `iForum Premium.xml`
7. Wait a few seconds until Blogger shows the confirmation toast: `Theme restored`.

### Method B: Edit HTML (Manual Paste)
1. Navigate to **Theme → Edit HTML**.
2. Press `Ctrl + A` and `Delete` to clear any default Blogger code.
3. Open `iForum Premium.xml` in Notepad or VS Code, select all code, and copy it.
4. Paste it into the Blogger editor and click the **Save** floppy icon in the top right.

---

## ⚙️ Step 2: Configure Mobile View
To ensure your forum displays in full responsive modern mode rather than Blogger's legacy mobile skin:
1. In the **Theme** tab, click the arrow next to **Customize**.
2. Select **Mobile settings**.
3. Choose **Desktop** (or choose *Custom* and ensure the mobile theme does not override the primary layout).
4. Click **Save**.

---

## 🎨 Step 3: Blogger Layout & Widgets Configuration
Navigate to the **Layout** tab in Blogger. iForum is organized into standard widget zones:
- **Header**: Logo, navigation links, and theme toggle.
- **Top Bar / Announcements**: Notification pills or pinned banners.
- **Main Forum Feed**: Blog Posts widget (Topics list).
- **Sidebar Right**: 
  - *Community Pulse Widget*: Realtime live counters.
  - *Author Card / Profile*: Current user card.
  - *Trending Labels*: Tag cloud and categories.
  - *Telegram Community CTA*: Quick link button to your community channel.
- **Footer**: Copyright, legal page links, and developer info.

---

## ⏭️ Next Steps
Proceed to the [Firebase Setup Guide](firebase-setup.md) to enable Google Logins, real-time post views, and heart reaction counters!
