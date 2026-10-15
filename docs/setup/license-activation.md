# Domain-Locked License System & Activation

iForum includes a proprietary anti-piracy domain locking mechanism based on a hardened 32-bit **DJB2 Hashing Algorithm** combined with a custom security salt.

---

## 🔒 How the License System Operates

1. **Standalone Key Generator**:
   - Buyers use an offline, standalone HTML tool to generate a unique 6-digit hex key for their specific domain.
   - Example domain: `techforum.blogspot.com` $\rightarrow$ Generates Hex: `A1F4C9`.
2. **Discreet Theme Integration**:
   - To prevent unauthorized bypasses while making user activation simple, the license key is inserted via Blogger's native UI customizer.
3. **Execution Verification**:
   - The embedded verification script runs on page load, sanitizes the current `window.location.hostname`, re-computes the DJB2 hash, and verifies against the configured license key.

---

## 🛠️ Activation Instructions for Buyers

### Step 1: Generate Your Key
1. Open your provided `KeyGenerator.html` file in any web browser.
2. Enter your exact live domain name without `https://` or trailing slashes (e.g. `myforum.blogspot.com` or `community.mysite.com`).
3. Click **Generate License Key**.
4. Copy the resulting **6-character uppercase Hex code** (e.g., `8B4F2A`).

### Step 2: Activate in Blogger
1. Go to your **Blogger Dashboard**.
2. Navigate to **Theme → Customize**.
3. In the customization side panel, click **Advanced → Theme Setup** (or **Theme Color** depending on your theme package version).
4. Locate the **Primary Base Hex Code** or **License Key** field.
5. Paste your 6-digit code with the `#` prefix (e.g., `#8B4F2A`).
6. Click the orange **Save** icon in the bottom right corner of the Blogger customizer.

---

## 🛡️ Hashing Logic (DJB2 Implementation Reference)

For reference, the hashing logic applies the following standardized flow:

```javascript
// Domain Sanitization
var str = domain.toLowerCase()
  .replace(/^https?:\/\//, '')
  .replace(/\/$/, '');

str += "ABEFILM"; // Secret Salt

// DJB2 32-bit Bitwise Hashing
var hash = 0;
for (var i = 0; i < str.length; i++) {
  hash = ((hash << 5) - hash) + str.charCodeAt(i);
  hash |= 0; // Force 32-bit integer conversion
}

// 6-Character Hex Representation
var hex = Math.abs(hash).toString(16).toUpperCase();
while (hex.length < 6) {
  hex = '0' + hex;
}
var finalKey = hex.substring(0, 6);
```
