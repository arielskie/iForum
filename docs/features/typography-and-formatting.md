# Official Forum Typography & Content Formatting Guide

The **iForum** theme includes a comprehensive suite of custom post-formatting styles and interactive components designed specifically for rich developer documentation, code playgrounds, tutorials, and community discussion threads.

---

## 🎨 Typography & Heading Hierarchy

Organize long threads into structured, readable sections using standardized semantic HTML tags:

```html
<!-- Section Header (H2) -->
<h2>Section Header (H2)</h2>
<p>Main paragraph text under H2 headers. Clean line-height and proportional spacing.</p>

<!-- Subsection Header (H3) -->
<h3>Subsection Header (H3)</h3>
<p>Subsections for detailed breakdowns or subtopics.</p>

<!-- Small Label (H4) -->
<h4>Small Label (H4)</h4>
<p>Used for notes, labels, or captions.</p>

<!-- Drop Cap -->
<p><span class="cap">T</span>his paragraph demonstrates a stylized drop cap for editorial intros.</p>
```

---

## 💻 1. Interactive Developer Sandbox (Live Code Playground)

iForum features an in-thread **Developer Sandbox Playground** with live tabs for **HTML**, **CSS**, and **JS**, plus an instant **Run** button that compiles into an isolated preview iframe!

```html
<div class="code-wrapper">
  <div class="code-header">
    <div class="code-dots">
      <span class="red"></span><span class="yellow"></span><span class="green"></span>
    </div>
    <div class="tab-headers">
      <div class="tab-link active" onclick="switchTab(this, 'demo-html')">HTML</div>
      <div class="tab-link" onclick="switchTab(this, 'demo-css')">CSS</div>
      <div class="tab-link" onclick="switchTab(this, 'demo-js')">JS</div>
    </div>
    <div class="header-actions">
      <button class="run-btn" onclick="runCode(this)"><i class="hgi hgi-stroke hgi-play-circle-02"></i> Run</button>
      <button class="copy-btn" onclick="copyCode(this)">Copy</button>
    </div>
  </div>

  <div id="demo-html" class="tab-content active">
    <pre><code><div class="sandbox-card">
  <h1>Interactive Sandbox</h1>
  <button id="testBtn" class="custom-btn btn-primary">Click Me</button>
</div></code></pre>
  </div>

  <div id="demo-css" class="tab-content" style="display:none;">
    <pre><code>.sandbox-card { padding: 20px; text-align: center; background: #151b28; }</code></pre>
  </div>

  <div id="demo-js" class="tab-content" style="display:none;">
    <pre><code>document.getElementById('testBtn').onclick = () => alert('Live JS execution!');</code></pre>
  </div>

  <div id="result-tab" class="tab-content">
    <iframe class="preview-iframe"></iframe>
  </div>
</div>
```

---

## 📢 2. Semantic Alerts & Callout Boxes

High-visibility callouts with custom Hugeicons / Phosphor icons for dark and light modes:

```html
<!-- Info Alert -->
<div class="alert info">
  <i class="ph-bold ph-info"></i>
  <div><b>Info:</b> General announcements, documentation links, and tips.</div>
</div>

<!-- Success Alert -->
<div class="alert success">
  <i class="ph-bold ph-check-circle"></i>
  <div><b>Success:</b> Confirms releases, verified patches, or status updates.</div>
</div>

<!-- Warning Alert -->
<div class="alert warning">
  <i class="hgi hgi-stroke hgi-alert-02"></i>
  <div><b>Warning:</b> Preventative advice (e.g., "Always backup your theme XML").</div>
</div>

<!-- Danger Alert -->
<div class="alert danger">
  <i class="ph-bold ph-warning-octagon"></i>
  <div><b>Danger:</b> Critical errors, breaking changes, or strict forum rules.</div>
</div>
```

---

## 🎯 3. Action Buttons & Button Groups

Call-to-action buttons with icon support and responsive `.btn-group` alignment:

```html
<!-- Single Primary Button -->
<a href="#" class="custom-btn btn-primary">
  <span class="btn-icon"><i class="hgi hgi-stroke hgi-rocket"></i></span> Launch App
</a>

<!-- Side-by-Side Symmetrical Pair -->
<div class="btn-group">
  <a href="#" class="custom-btn btn-default">
    <span class="btn-icon"><i class="hgi hgi-stroke hgi-eye"></i></span> Preview
  </a>
  <a href="#" class="custom-btn btn-primary">
    <span class="btn-icon"><i class="hgi hgi-stroke hgi-download-04"></i></span> Download
  </a>
</div>
```

---

## 🔒 4. Content Engagement: Spoilers & Locked Downloads

### Visual Blur Spoiler
Clicking reveals the hidden content:
```html
<p>Secret code: <span class="spoiler-blur" onclick="this.classList.toggle('active')">PASSWORD123</span></p>
```

### Database Content Locker (Requires Heart/Like to Unlock)
Integrates directly with Firebase to lock download links until the member hearts the topic:
```html
<div class="dl-card content-locker unlocked">
  <div class="dl-info">
    <div class="dl-icon-box"><i class="ph-bold ph-file-zip"></i></div>
    <div class="dl-meta">
      <span class="dl-name">Theme_Resource.zip</span>
      <span class="dl-size">2.4 MB • <span class="badge-tag badge-free">FREE</span></span>
    </div>
  </div>
  <div class="dl-action-area">
    <div class="lock-notice"><i class="hgi hgi-stroke hgi-favourite"></i><p>Heart to Download</p></div>
    <a class="dl-btn locked-link-btn" href="YOUR_DOWNLOAD_LINK" target="_blank">Download Now</a>
  </div>
</div>
```

---

## 📊 5. Responsive Data & Specification Tables

Tables automatically support horizontal scrolling on mobile screens using `.table-responsive`:

```html
<div class="table-responsive">
  <table>
    <thead>
      <tr>
        <th>Module</th>
        <th>Type</th>
        <th>Version</th>
        <th>Status</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Theme Core</strong></td>
        <td>Theme</td>
        <td>2.4.0</td>
        <td><span class="badge-color badge-green">Released</span></td>
      </tr>
      <tr>
        <td><strong>Forum Engine</strong></td>
        <td>Community</td>
        <td>1.2.1</td>
        <td><span class="badge-color badge-blue">Active</span></td>
      </tr>
    </tbody>
  </table>
</div>
```

---

## 🧩 6. Accordions & Step-by-Step Timelines

### Step Timeline
```html
<div class="step-container">
  <div class="step-item">
    <div class="step-num"><div class="step-number-inner">1</div></div>
    <div class="step-content"><b>Verify:</b> Ensure you are logged into your account.</div>
  </div>
  <div class="step-item">
    <div class="step-num"><div class="step-number-inner">2</div></div>
    <div class="step-content"><b>Heart:</b> Like the post to unlock direct download links.</div>
  </div>
</div>
```

### Collapsible FAQ Accordion
```html
<div class="post-accordion">
  <div class="acc-header">
    How do I obtain my unique File ID?
    <i class="hgi hgi-stroke hgi-arrow-down-01"></i>
  </div>
  <div class="acc-body">
    <p>Use the official Master Generator link provided in the Advanced Section of this thread.</p>
  </div>
</div>
```

---

## 🖼️ 7. Media Galleries & Swipe Scrollers

- **4-Item Grid (`.grid-gallery-2`)**: 2x2 grid for screenshots and mockups.
- **Horizontal Swipe Scroller (`.gallery-with-nav` & `.img-scroll-container`)**: Scroll-snapping single row scroller for mobile devices.
