# adjust_brightness

| Field | Value |
|---|---|
| **Filename** | `adjust_brightness.ijm` |
| **Category** | Brightness_Contrast |
| **Language** | ImageJ Macro |
| **Author** | Selin Kubilay |
| **Date** | 2024 |
| **Fiji version tested** | — |
| **Required plugins** | None |

---

### Publication

> To be filled in.

---

### What this script does

Applies automatic contrast enhancement to all three channels of an open multi-channel image stack. For each channel it runs Fiji's "Enhance Contrast" function with a saturation level of 0.35%, then returns focus to channel 1.

---

### Input

- **File type:** Multi-channel image stack (at least 3 channels)
- **Required image properties:** Must be open in Fiji as the active image

---

### Output

- The active image with contrast enhanced in-place for channels 1, 2, and 3.

---

### Parameters to adjust

| Parameter | Default value | Description |
|---|---|---|
| `saturated` | 0.35 | Fraction of pixels allowed to be saturated during contrast enhancement |

---

### Known limitations

- Hardcoded for exactly 3 channels. Images with fewer or more channels will not have all channels adjusted.
- Applies display enhancement only — pixel values are not modified.

---

### Notes

None.
