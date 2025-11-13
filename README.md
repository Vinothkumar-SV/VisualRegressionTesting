# 🧪 Visual Regression Testing

## 📖 Overview

**VisualRegressionTesting** is a modern automation framework built using **Playwright**, **Node.js**, and **Pixelmatch** to detect and highlight UI differences between baseline and current screenshots.
This project helps QA engineers ensure that new UI changes do not unintentionally alter the visual appearance of web applications.

---

## 🚀 Key Features

* 🖼️ **Baseline & Current Image Comparison** – Captures screenshots and compares them pixel-by-pixel.
* 🎯 **Visual Diff Generation** – Highlights mismatched regions with color overlays for quick inspection.
* 🧠 **Threshold-Based Tolerance** – Supports configurable tolerance levels to ignore negligible changes.
* 📊 **Automated HTML Report** – Summarizes results with side-by-side image previews.
* ⚙️ **Configurable Execution** – Easily manage URLs, viewport sizes, and output folders from config files.
* 🔄 **Reusable Utility Modules** – For image diff, logging, and report management.

---

## 🧰 Tech Stack

| Category              | Tools / Libraries                  |
| --------------------- | ---------------------------------- |
| **Language**          | JavaScript / TypeScript            |
| **Framework**         | Playwright                         |
| **Image Comparison**  | Pixelmatch                         |
| **Report Generation** | HTML Report / Custom Node Renderer |
| **File System**       | Node.js FS, Path                   |
| **Version Control**   | GitHub                             |

---

## 📁 Project Structure

```
VisualRegressionTesting
│
├── src/
│   ├── tests/                 # Visual regression test scripts
│   ├── utils/                 # Utility modules (imageDiff, fileHandler, logger)
│   └── config/                # Environment & path configuration
│
├── baseline/                  # Reference screenshots (expected UI)
├── current/                   # Screenshots from latest test run
├── diff/                      # Highlighted difference images
│
├── reports/                   # Generated HTML visual reports
├── package.json               # Project dependencies & scripts
├── playwright.config.js       # Playwright configuration file
└── README.md                  # Project documentation
```

---

## ⚙️ Configuration Setup

### 1️⃣ Update Configuration

In your `config/config.js` or `.env`, specify:

```js
module.exports = {
  baseUrl: "https://yourwebsite.com",
  threshold: 0.1, // 10% pixel tolerance
  baselineDir: "./baseline",
  currentDir: "./current",
  diffDir: "./diff",
  reportDir: "./reports"
};
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Add Required Packages

```bash
npm install playwright pixelmatch fs-extra
```

---

## 🧩 How to Run the Tests

### 🖥️ From Command Line

```bash
npx playwright test
```

or, for a specific test:

```bash
npx playwright test visualTest.spec.js
```

### 🧾 After Execution

* Current screenshots saved inside `/current`
* Pixel-by-pixel diffs stored in `/diff`
* Visual summary generated in `/reports`

---

## 🧱 Architecture & Flow

```
       ┌──────────────────────────────┐
       │      Test Execution          │
       │  (Playwright launches site)  │
       └──────────────┬───────────────┘
                      │
                      ▼
          ┌──────────────────────────┐
          │ Capture Current Screenshot│
          └──────────────┬───────────┘
                         │
                         ▼
         ┌────────────────────────────┐
         │ Compare with Baseline (Pixelmatch)│
         └──────────────┬─────────────┘
                        │
                        ▼
           ┌─────────────────────────┐
           │ Generate Diff Image      │
           └──────────────┬──────────┘
                          │
                          ▼
             ┌──────────────────────┐
             │ HTML Report Summary  │
             └──────────────────────┘
```

---

## 📸 Example Output

* **Baseline Image:** `baseline/homepage.png`
* **Current Image:** `current/homepage.png`
* **Diff Image:** `diff/homepage_diff.png`
* **HTML Report:** `reports/visual-report.html`

---

## 👨‍💻 Author

*Vinoth Kumar S*
SDET | Automation Enthusiast 
📧 [vinothkumar.sv@gmail.com](mailto:vinothkumar.sv@gmail.com)
🔗 [GitHub Profile](https://github.com/Vinothkumar-SV)

---

## 🏁 Future Enhancements

* 🔄 Jenkins pipeline integration for automated regression runs
* ☁️ Upload visual reports to AWS S3 or GitHub Pages
* 🧠 AI-based dynamic tolerance (adaptive comparison logic)
* 🐳 Docker support for headless execution in CI environments
* 💬 Slack / Teams notification integration

---

⭐ **If you found this project helpful, don’t forget to give it a star!** ⭐

---

Would you like me to:

* 💾 **Export this as a Word file** for upload to your GitHub repo,
  or
* 🖼️ **Add a sample image/report preview section** to make the README more visually rich on GitHub?
