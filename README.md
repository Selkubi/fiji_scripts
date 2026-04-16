# UPGON Lab — Fiji Script Repository

This repository is the central archive of Fiji/ImageJ scripts produced by members of the UPGON lab at EPFL. It is built on the [ImageJ example-script-collection](https://github.com/imagej/example-script-collection) Maven template, which means scripts are packaged into a `.jar` file that can be installed directly into any Fiji installation.

---

## Why This Repository Exists

Fiji scripts are core scientific instruments. When a script is used to produce figures or measurements in a publication, it must be preserved exactly as it was used — not on a personal laptop that may be reformatted, not in an email attachment, and not in a folder called `final_FINAL_v3`.

**When you leave the lab, your scripts leave with you — unless you deposit them here.**

This repository ensures that:

- Every script tied to a publication is permanently archived and version-controlled
- Future lab members can reproduce your results without tracking you down years later
- Reviewers and collaborators can access the exact analysis tools described in your methods section
- The lab does not lose years of methodological development between student rotations

Depositing your scripts here is part of your offboarding checklist. It is not optional.

---

## Repository Structure

Scripts are organized by **analysis category**, not by author. This keeps the repository useful after you leave.

```
src/main/resources/scripts/
└── UPGON/
    ├── Brightness_Contrast/
    ├── Cell_Segmentation/
    ├── Intensity_Analysis/
    ├── Morphology/
    └── Tracking/
```

Each script category maps directly to a submenu in Fiji's **Plugins** menu once the collection is installed. If your script does not fit an existing category, propose a new folder in your merge request.

Each script must have a matching documentation file in `docs/scripts/`. Use the template at `docs/scripts/TEMPLATE.md`.

---

## How to Install the Scripts in Your Personal Fiji

There are two ways to use scripts from this repository in your local Fiji. Use **Method 1** if you want the full collection; use **Method 2** for a single script.

### Method 1 — Install the full collection (recommended)

This installs all scripts from this repository as a Fiji plugin. They will appear under **Plugins > UPGON** in the menu.

**Prerequisites:** Java 8+ and Maven installed.

1. Clone this repository:
   ```
   git clone https://gitlab.epfl.ch/upgon/projects/fiji_scripts.git
   cd fiji_scripts
   ```

2. Build the `.jar` file:
   ```
   mvn package
   ```
   This produces `target/example-script-collection-X.X.X-SNAPSHOT.jar`.

3. Copy the `.jar` into your Fiji plugins folder:
   - **macOS:** `Fiji.app/plugins/`
   - **Windows:** `Fiji\plugins\`
   - **Linux:** `Fiji.app/plugins/`

4. Restart Fiji. The scripts will appear under **Plugins > UPGON**.

To update to the latest version, run `git pull` followed by `mvn package` and replace the `.jar`.

### Method 2 — Run a single script directly

1. Open Fiji.
2. Go to **File > Open** and navigate to the `.ijm`, `.groovy`, or `.py` file from this repository.
3. The Script Editor will open. Click **Run** to execute it.

Alternatively, drag and drop the script file onto the Fiji toolbar to open it in the Script Editor.

---

## How to Contribute — Offboarding Checklist

If you are leaving the lab and have scripts used in publications or shared analyses, follow the steps in [CONTRIBUTING.md](CONTRIBUTING.md).

The short version:

1. Place your script in the correct category folder under `src/main/resources/scripts/UPGON/`
2. Add a header comment block inside the script file (see `docs/scripts/TEMPLATE.md`)
3. Create a documentation file for your script in `docs/scripts/` using the template
4. Open a merge request on GitLab
5. A lab member reviews and merges it

Do this **before your last day**. It takes under an hour per script.

---

## Questions

Post in the lab channel or open an issue on GitLab.
