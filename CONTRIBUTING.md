# Contributing to the UPGON Fiji Script Repository

This guide explains how to deposit your scripts when leaving the lab. **You do not need to know Git or use a terminal.** Everything can be done through your web browser on GitLab.

If you do have Git configured and prefer working in a terminal, jump to [Option B — Terminal (for Git users)](#option-b--terminal-for-git-users) at the bottom.

---

## Before You Start

Identify which scripts qualify for deposit. A script qualifies if:

- It was used to generate figures, measurements, or data in a submitted or published paper
- It implements an analysis method that other lab members may need to reuse

You do not need to deposit every script you ever wrote — only those tied to reproducible science.

Also confirm the script still works: open Fiji, run the script on one of the images from your publication, and verify the output matches what appears in the paper. **Note the Fiji version you used**. You can find it under **Help > About Fiji** in the menu bar.

---

## What You Will Upload

For each script, you will upload **two files**:

| File | What it is | Where it goes |
|---|---|---|
| Your script file | The `.ijm`, `.groovy`, or `.py` file | `src/main/resources/scripts/UPGON/<Category>/` |
| A documentation file | A `.md` text file describing the script | `docs/scripts/` |

The documentation file follows the template at `docs/scripts/TEMPLATE.md`. You can write it in any text editor (TextEdit, Notepad, Word — just save it as plain text with a `.md` extension).

---

## Option A — GitLab Web Interface (no Git required)

### Step 1 — Open the repository in your browser

Go to: **https://gitlab.epfl.ch/upgon/projects/fiji_scripts**

Log in with your EPFL credentials if prompted.

---

### Step 2 — Add a header comment to your script

Before uploading, open your script file in any text editor and add these lines at the very top:

**For `.ijm` files:**
```
// Title: Your Script Name
// Author: First Last
// Date: YYYY-MM
// Publication: Authors et al. Journal Year. DOI: https://doi.org/...
// Fiji version tested: 2.x.x / YYYYMMDD
// Required plugins: None  (or list any extra plugins needed)
// Description: One sentence describing what this script does.
```

**For `.py` files**, use `#` instead of `//`.

Save the file.

---

### Step 3 — Upload your script file

1. On the GitLab repository page, click the folder `src` in the file list.
2. Keep clicking through: `main` → `resources` → `scripts` → `UPGON`.
3. Choose the category folder that best fits your script:

   | Folder | Use for |
   |---|---|
   | `Brightness_Contrast` | Display adjustments, LUT changes |
   | `Cell_Segmentation` | Nucleus, cell body, or organelle segmentation |
   | `Intensity_Analysis` | Fluorescence measurements, channel quantification |
   | `Morphology` | Shape descriptors, area, perimeter, circularity |
   | `Tracking` | Particle or cell tracking over time |

   If none fit, contact the repository maintainer to create a new category.

4. Once inside the correct category folder, click the **+** button (top right of the file list) and choose **Upload file**.
5. Drag your script file into the upload box.
6. Scroll down to the **Commit changes** section:
   - In the commit message field, write something like: `Add MyScriptName by First Last (Paper et al. 2024)`
   - Select **Create a new branch and merge request**.
   - GitLab will suggest a branch name — you can leave it as-is.
7. Click **Upload file**.

---

### Step 4 — Write and upload your documentation file

1. Open `docs/scripts/TEMPLATE.md` in the repository (click on it to view it).
2. Copy all the text.
3. Paste it into a plain text editor on your computer. Fill in every field for your script.
4. Save the file as `YourScriptName.md` (use the exact same name as your script file, but with `.md` instead of `.ijm`).
5. Go back to the repository and navigate to `docs/scripts/`.
6. Click **+** → **Upload file**.
7. Upload your filled-in `.md` file.
8. In the commit message, write: `Add documentation for MyScriptName`.
9. **Important:** In the branch selector, choose the **same branch** you created in Step 3 (not `main`). This groups your files into one merge request.
10. Click **Upload file**.

---

### Step 5 — Submit the merge request

After your uploads, GitLab will show a prompt: **"Create merge request"**. Click it.

On the merge request page:
- Give it a title like: `Deposit MyScriptName — First Last (Paper et al. 2024)`
- In the description, paste the content of your documentation file and add a link to the publication
- Assign it to the repository maintainer
- Click **Create merge request**

A current lab member will review your submission and may ask for small corrections. Once approved, your script will be merged into the main repository.

---

## Option B — Terminal (for Git users)

If you have Git configured on your machine and prefer the terminal:

1. Clone the repository:
   ```
   git clone https://gitlab.epfl.ch/upgon/projects/fiji_scripts.git
   cd fiji_scripts
   ```

2. Create a branch for your deposit:
   ```
   git checkout -b deposit/your-name-scriptname
   ```

3. Copy your script into the correct category:
   ```
   src/main/resources/scripts/UPGON/<Category>/YourScript.ijm
   ```

4. Copy the documentation template and fill it in:
   ```
   cp docs/scripts/TEMPLATE.md docs/scripts/YourScriptName.md
   # edit docs/scripts/YourScriptName.md in your editor
   ```

5. Commit and push:
   ```
   git add src/main/resources/scripts/UPGON/<Category>/YourScript.ijm
   git add docs/scripts/YourScriptName.md
   git commit -m "Add YourScriptName by First Last (Paper et al. YYYY)"
   git push -u origin deposit/your-name-scriptname
   ```

6. Open a merge request on GitLab from the link printed in the terminal output.

---

## Offboarding Checklist

- [ ] Script runs end-to-end on a test image from the publication
- [ ] Header comment block added at the top of the script file
- [ ] Script uploaded to the correct category folder
- [ ] `docs/scripts/YourScriptName.md` filled in and uploaded
- [ ] Merge request opened and linked to the publication
- [ ] Merge request reviewed and merged before your last day

---

## Questions

Open an issue on GitLab or contact the repository maintainer directly.
