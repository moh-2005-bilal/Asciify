# ASCIIFY — Image to ASCII Art & Compressor

**ASCIIFY** is a fully client-side web tool that converts images into ASCII art and compresses them without uploading anything to a server. It's built with pure HTML, CSS, and JavaScript — no frameworks, no dependencies, no tracking.

## ✨ Features

### ASCII Art Generator
- **6 rendering modes**:
  - Shaded (dark-to-light character ramp)
  - Binary (1/0 threshold with adjustable cutoff)
  - Color (each character colored with original pixel color)
  - Blocks (solid block characters)
  - Edges (Sobel edge detection)
  - Matrix (green-on-black style)
- Adjustable **resolution** (columns), **aspect ratio**, **brightness**, **contrast**, and **invert**.
- Live preview with debounced conversion.
- Export options: copy as plain text, copy as HTML (for colored modes), download as `.txt` or `.png`.

### Image Compressor
- Upload any image (JPG, PNG, WebP).
- Adjust **quality** (10–100%).
- Choose output format: **JPEG**, **PNG**, or **WebP**.
- See original and compressed file sizes instantly.
- Download the compressed image.

### General
- **Dark / Light theme** toggle with persistent user preference (localStorage).
- **Responsive design** — works on desktop, tablet, and mobile.
- Custom scrollbars and touch-friendly controls.
- **No server uploads** — everything runs locally in the browser.

## 🚀 Demo

You can try it live by opening `index.html` in any modern browser.  
*(If hosted, provide a link here)*

## 📁 Usage

1. Clone or download the repository.
2. Open `index.html` in your browser.
3. For ASCII art: upload an image, choose a mode, adjust settings, and export.
4. For compression: upload an image, set quality/format, and download the compressed result.

No installation or build step required.

## 🛠️ Technologies Used

- **HTML5** — semantic structure, canvas API for pixel manipulation.
- **CSS3** — custom properties (variables), grid/flexbox, transitions, dark/light theming.
- **JavaScript (ES6+)** — FileReader, Canvas 2D context, Blob downloads, Clipboard API with fallback.
- **Font Awesome** — icons for UI elements.
- **Google Fonts** — Poppins (UI) and JetBrains Mono (ASCII output).

## 🔍 How It Works

### ASCII Generation
1. The image is drawn onto an offscreen `<canvas>` at the user-selected resolution.
2. Each pixel's RGB values are read and converted to brightness using the formula:  
   `brightness = 0.299·R + 0.587·G + 0.114·B`
3. Brightness is optionally adjusted by contrast/brightness sliders and inverted.
4. The brightness value is mapped to a character from a ramp (dark → light) or used for binary thresholding.
5. For edge detection, a Sobel operator is applied to the grayscale image before character mapping.
6. The resulting character grid is displayed in a monospaced font and can be copied or exported.

### Image Compression
1. The original image is drawn onto a canvas.
2. The canvas is converted to a data URL using the selected MIME type and quality factor.
3. The resulting size is estimated from the base64 string length.
4. The compressed image is displayed as a preview and can be downloaded.

## 📱 Browser Compatibility

Works in all modern browsers that support Canvas, FileReader, and Clipboard API:
- Chrome / Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Android Chrome)

## 👤 Author

**Mohammad Bilal**  
GitHub: [moh-2005-bilal](https://github.com/moh-2005-bilal)

---

Feel free to contribute, report issues, or suggest improvements!
