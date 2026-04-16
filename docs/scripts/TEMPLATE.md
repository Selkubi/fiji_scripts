# Script Documentation Template

Copy this file and rename it to match your script filename (e.g. `Segment_Nuclei.md`).
Fill in every field. Do not leave fields blank — write "None" or "N/A" if genuinely not applicable.
Delete these instructions before submitting.

---

## [Script Name]

| Field | Value |
|---|---|
| **Filename** | `ScriptName.ijm` |
| **Category** | e.g. Cell_Segmentation |
| **Language** | ImageJ Macro / Groovy / Python |
| **Author** | First Last |
| **Date** | YYYY-MM |
| **Fiji version tested** | e.g. 2.14.0 / 20231125 — find this under Help > About Fiji |
| **Required plugins** | List any non-default plugins, e.g. StarDist, CLIJ2, MorphoLibJ. Write "None" if only core Fiji. |

---

### Publication

> Paste the full citation here.
> Example: Doe J, Smith A. Title of paper. *Nature Methods*. 2023;20(1):1–10. DOI: https://doi.org/...

---

### What this script does

Describe in plain language what the script does, step by step. Write this as if explaining to a new lab member who is not yet familiar with your project. Two to five sentences is usually enough.

---

### Input

Describe what the script expects as input:

- **File type:** e.g. `.tif`, multi-channel, 16-bit
- **Required image properties:** e.g. "3-channel z-stack, channel 1 = DAPI, channel 2 = GFP, channel 3 = mCherry"
- **Batch mode:** Does it process a single open image or a folder of images?

---

### Output

Describe what the script produces:

- e.g. ROI set saved to the image directory
- e.g. Results table exported as `measurements.csv`
- e.g. Processed image saved as `original_name_processed.tif`

---

### Parameters to adjust

List any parameters embedded in the script that a user may need to change for their data:

| Parameter | Default value | Description |
|---|---|---|
| `threshold` | 500 | Manual intensity threshold for segmentation |
| `sigma` | 2.0 | Gaussian blur sigma before thresholding |

If the script has no user-adjustable parameters, write "None."

---

### Known limitations

List any known edge cases, failure modes, or imaging conditions where the script does not work well.

- e.g. "Does not work correctly on images with more than 3 channels."
- e.g. "Threshold value was tuned for 63x oil objective on the lab Zeiss LSM 980 — may need adjustment for other magnifications."

---

### Notes

Any additional context that would help someone reproduce or adapt this script. Optional.
