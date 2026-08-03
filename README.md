# Root_Label_Tool

![HTML](https://img.shields.io/badge/HTML-5-E34F26?logo=html5&logoColor=white)
![License](https://img.shields.io/badge/License-AGPL--3.0-blue)

A web-based tool for segmenting and labelling roots in images using ONNX models. Your data is not shared; everything is local!

[DIRECT LINK](https://dicarusb.github.io/Root_Label_Tool/root_label_tool.html)


## Features

- Load image directories (PNG, JPG, JPEG, BMP, TIFF, WEBP)
- Load ONNX segmentation models
- Predict masks using loaded models
- Manual mask editing with brush tool (label/erase)
- Undo for manual edits
- Save masks as JPEG files
- Zoom in/out with mouse wheel or buttons

## Quick Start

### Option 1: Online (No Installation)
Open the provided URL in any modern browser.

[CLICK HERE!](https://dicarusb.github.io/Root_Label_Tool/root_label_tool.html)

### Option 2: Local Installation
1. Download the file `root_label_tool.html`

2. **Double-click `root_label_tool.html`** to open it in your browser.

Or run a local server:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000`

---

## 📖 How to Use

1. Open the HTML file in a modern browser (Chrome, Edge, Opera recommended)
2. Click **📦 Load Model (ONNX)** and select your `.onnx` file
3. Click **📂 Load Directory** and select a folder with images
4. Click an image name in the list to open it
5. Click **🔮 Predict Mask** to run segmentation
6. Use the brush to manually correct the mask:
   - **✏️ Label mode**: Paint green areas (add to mask)
   - **🧹 Erase mode**: Remove green areas
   - **Brush size**: Slider or keys `1` (smaller) / `2` (larger)
7. Click **💾 Save Mask** to export as `original_name_mask.jpg`
8. Use **↩️ Undo** (`Ctrl+Z`) to revert brush strokes

## How It Works

- Images are automatically resized to fit your model's requirements (sizes divisible by 32)
- Large images (over 1024px) are scaled down for performance
- Masks are displayed as solid green overlay on the image
- Saved masks are grayscale (white = labelled, black = background)
- Masks are saved at original image resolution

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `1` | Decrease brush size |
| `2` | Increase brush size |
| `Ctrl+Z` | Undo last brush stroke |

## Requirements

- Modern browser with WebAssembly support
- ONNX Runtime Web (loaded from CDN)
- ONNX model file (`.onnx`) compatible with the tool
