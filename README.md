# AUDEN Age-Suitability Checker 🛡️

**A simple, safe tool to help parents check if apps are appropriate for their children.**

AUDEN is a research-based scoring system that looks at five areas — Affordances, Use Patterns, Developmental fit, Environment fit, and Norms — to give each app a Safety Index (0–5). We also show how confident we are in each score, let you tweak priorities, and modify results to match your family context (device quality, languages, and parental literacy). Every recommendation links to evidence and includes an audit trail so you can see who reviewed the rating and when.

---

## 🚀 How to Put This on the Web (In 2 Minutes)

You do **not** need to be a programmer. You do **not** need a server.

### Step 1: Copy this Repository
1. Create a new repository on GitHub (e.g., named `my-auden-checker`).
2. Add the files provided here to the **root** of your repository (so `package.json` is at the top level).

### Step 2: Add Your PDF Evidence
*Important: To make the evidence links work, you must add your files manually.*
1. Create a folder named `public` in your repository.
2. Inside `public`, create a folder named `assets`.
3. Upload your two PDF files here:
   - `public/assets/reading_course.pdf`
   - `public/assets/literature_review.pdf`

### Step 3: Enable the Website
1. Go to your repository **Settings** (top menu bar, near the gear icon).
2. On the left sidebar, click **Pages**.
3. Under "Build and deployment" > "Source", select **GitHub Actions**.
   *(Note: If you don't see "GitHub Actions", just select "Deploy from a branch", choose `gh-pages` branch if it exists, and click Save. But usually, the "GitHub Actions" option is best).*

### Step 4: Wait a Moment
1. Click on the **Actions** tab in the top menu.
2. You will see a workflow running called "Deploy to GitHub Pages".
3. Wait for the green checkmark ✅ (takes about 45 seconds).

### Step 5: Visit Your Site
1. Go back to **Settings** > **Pages**.
2. At the top, you will see a link: `Your site is live at...`
3. Click it! You are done.

---

## 🔧 Troubleshooting

* **Problem: "Why is the screen blank when I open the code?"**
  * **Answer:** This is a React app. It needs to be "built" to run. It won't work if you just double-click `index.html` on your computer. Once you push to GitHub, the automated workflow builds it for you and it will work perfectly on the web.
* **Problem:** "I see a 404 error when I click the link."
  * **Fix:** Wait 1 more minute and refresh. It takes time for GitHub to copy the files to the web servers.
* **Problem:** "The Actions tab has a red X."
  * **Fix:** Click on the red X to see the error. Ensure you didn't change the folder structure. If it says "permission denied", go to Settings > Actions > General > Workflow permissions and select "Read and write permissions".
* **Problem:** "The Evidence PDF links don't work."
  * **Fix:** Ensure you created the `public/assets/` folder and put the PDFs there. The build process copies everything in `public` to the final website.

---

## 📝 How to Add Apps or Edit Scores

You can edit the database directly in your browser:

1. Go to the **Code** tab.
2. Navigate to `src/data/apps.json`.
3. Click the Pencil icon ✏️ to edit.
4. Add a new app block (copy-paste an existing one) or change numbers.
   * `A, U, D, E, N`: Scores from 0 (bad) to 5 (good).
   * `id`: must be unique (e.g., "new-app").
5. Click **Commit changes** (green button).
6. The site will automatically rebuild and update in about 1 minute.

---

## 🧪 For Developers (Testing)

To run the scientific test vectors (checking if the math is correct):

1. Install Node.js on your computer.
2. Download this code.
3. Open a terminal in the folder.
4. Run:
   ```bash
   node test/test_vectors.js
   ```
5. You should see "ALL TESTS PASSED SUCCESSFULLY".

---

## ⚠️ Disclaimer

This tool provides guidance based on a theoretical framework. It is not medical or legal advice. Every child is unique. Do not enter personal identifiable information (PII) into this tool.