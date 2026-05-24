# B30) Generate an AI-Created Image and Apply an Imperceptible Watermark That Survives Editing

# Overview

For this activity, I generated an AI-created image using the prompt:

```text
“Generate an engineer carrying a kitten”
```

The image was generated using the AI image generation system Grok.

I then developed Python scripts using the Pillow and NumPy libraries to:
- embed an imperceptible watermark into the image using Least Significant Bit (LSB) steganography
- extract and verify the hidden watermark after image modifications

The hidden watermark text used was:

```text
ANNMARIA_CYBER_PORTFOLIO_B30
```

The purpose of the activity was to test whether hidden watermarking could survive image editing and regeneration processes.

---

# Objective

The objective of this activity was to:
- generate an AI-created image
- embed a hidden watermark into the image
- modify the image through editing and regeneration processes
- verify whether the hidden watermark remained detectable afterward

---

# Tools and Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Watermark scripting |
| Pillow (PIL) | Image processing |
| NumPy | Pixel manipulation |
| Grok AI | AI image generation |
| LSB Steganography | Imperceptible watermark embedding |

---

# Step 1 — Generating the AI Image

An AI-generated image was created using the following prompt:

```text
Generate an engineer carrying a kitten
```

The generated image was saved as:

```text
ai_image.png
```

## Generated Image

![Generated AI Image](ai-image.png)

---

# Step 2 — Creating the Watermark Embedding Script

A Python script named:

```text
embed_watermark.py
```

was created to hide the watermark text inside the image using Least Significant Bit (LSB) steganography.

The script modified the least significant bits of image pixels to invisibly store binary watermark data.

## Watermark Embedding Script

```python
from PIL import Image
import numpy as np

input_image = "ai_image.png"
output_image = "watermarked_image.png"
watermark_text = "ANNMARIA_CYBER_PORTFOLIO_B30"

img = Image.open(input_image).convert("RGB")
arr = np.array(img)

bits = ''.join(format(ord(c), '08b') for c in watermark_text)
bits += '00000000'

flat = arr.flatten()

for i, bit in enumerate(bits):
    flat[i] = (flat[i] & 254) | int(bit)

watermarked = flat.reshape(arr.shape)

Image.fromarray(watermarked.astype(np.uint8)).save(output_image)

print("Watermark embedded into", output_image)
```

## Evidence

![Embedding Script](embed-script.png)

---

# Step 3 — Embedding the Imperceptible Watermark

The script was executed using:

```bash
python3 embed_watermark.py
```

The output confirmed:

```text
Watermark embedded into watermarked_image.png
```

The resulting image visually appeared identical to the original image because the watermark was hidden inside pixel-level data.

## Evidence

![Watermark Embedded Terminal Output](embed-terminal.png)

---

# Step 4 — Editing and Regenerating the Image

To test whether the watermark could survive image modifications, multiple transformations were performed on the watermarked image, including:

- brightness adjustments
- contrast adjustments
- exposure changes
- saturation changes
- resizing operations

These edits simulated realistic ways AI-generated media may be modified, redistributed or regenerated online.

## Edited Image Evidence

![Edited Watermarked Image](edited-image.png)

---

# Step 5 — Creating the Watermark Extraction Script

A second Python script named:

```text
extract_watermark.py
```

was created to recover the hidden watermark from the modified image.

The script extracted the least significant bits from image pixels and reconstructed the hidden text.

## Watermark Extraction Script

```python
from PIL import Image
import numpy as np

image_file = "watermarked_image.png"

img = Image.open(image_file).convert("RGB")
arr = np.array(img).flatten()

bits = [str(pixel & 1) for pixel in arr[:5000]]

chars = []

for i in range(0, len(bits), 8):
    byte = bits[i:i+8]

    if len(byte) < 8:
        break

    char = chr(int(''.join(byte), 2))

    if char == '\x00':
        break

    chars.append(char)

watermark = ''.join(chars)

print("Extracted watermark:", watermark)
```

## Evidence

![Extraction Script](extract-script.png)

---

# Step 6 — Extracting the Watermark After Editing

The extraction script was executed using:

```bash
python3 extract_watermark.py
```

The watermark was successfully recovered:

```text
Extracted watermark: ANNMARIA_CYBER_PORTFOLIO_B30
```

This confirmed that the hidden watermark survived the image editing and regeneration process.

## Evidence

![Extracted Watermark Output](extract-terminal.png)

---

# Analysis

The activity successfully demonstrated that imperceptible watermarking techniques can survive moderate image transformations.

Although the image underwent:
- brightness changes
- contrast modifications
- exposure adjustments
- saturation changes
- resizing

the hidden watermark remained detectable and recoverable.

This demonstrates how watermarking can:
- verify ownership of AI-generated media
- support authenticity validation
- assist digital forensics investigations
- help identify redistributed AI-generated content

---

# Security and Cybersecurity Relevance

Imperceptible watermarking is increasingly important in cybersecurity and digital media verification because it helps:
- identify manipulated AI-generated content
- prove media ownership
- support attribution and authenticity checking
- combat misinformation and deepfake redistribution
- track unauthorised reuse of generated media

LSB steganography specifically demonstrates how hidden data can exist within seemingly unchanged files.

---

# Skills and Concepts Demonstrated

This activity demonstrated:
- Python scripting
- image processing
- steganography
- AI-generated media analysis
- digital watermarking
- data embedding techniques
- watermark extraction
- media authenticity verification

---

# Conclusion

Overall, this activity successfully demonstrated the creation of an AI-generated image and the implementation of an imperceptible watermark using LSB steganography.

The watermark survived multiple image editing and regeneration operations and was successfully extracted afterward using a custom Python extraction script.

This demonstrated how hidden watermarking techniques can help maintain authenticity, ownership verification and traceability of AI-generated media even after images have been modified.
