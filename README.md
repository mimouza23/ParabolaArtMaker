# ✨ Parabola Builder: Interactive Conic Section Visualizer

### Site at: [Parabola Builder](https://mimouza23.github.io/ParabolaArtMaker/)

## 📐 1. Overview

The Parabola Builder is a standalone, single-page web application designed for visualizing conic sections (primarily parabolas) and lines on an interactive Cartesian coordinate grid. It allows users to define curves using two points, manipulate the view (pan and zoom), and manage data via export/import functions. The application uses HTML, pure JavaScript, and Tailwind CSS (via a CDN) for styling and interactivity.

---

## ⚙️ 2. Core Features

*   **Interactive Curve Drawing:** Create parabolas and line segments directly on the canvas grid.
*   **Real-time Equations:** Hovering over a curve displays its standard form equation (and vertex form for parabolas) in a dynamic tooltip.
*   **Grid Manipulation:** Supports smooth zooming via mouse wheel and panning via **Alt + Drag** (or middle mouse button).
*   **Persistent State:** Utilizes `localStorage` for auto-saving the entire set of curves, zoom level, and pan offset.
*   **Data Management:** Allows exporting all current curves as a JSON file and importing curves from a JSON file.
*   **Background Image Support:** Import an image to use as a background for tracing or reference, with dedicated tools for moving and resizing the image.
*   **Toolset:** Includes dedicated tools for drawing, erasing, and resizing curve endpoints.
*   **Customization:** Toggles for Line Mode, showing/hiding construction points, showing/hiding dashed "full" curves, and a Light/Dark Mode theme switch.
*   **Undo/Redo:** History management using **Ctrl+Z** and **Ctrl+Y/Ctrl+Shift+Z**.

---

## ✏️ 3. Drawing and Curve Modes

The Draw tool has two primary sub-modes, controlled by the **"Line Mode"** toggle in the Options panel:

| Mode | Toggle | Steps to Create | Curve Type |
| :--- | :--- | :--- | :--- |
| **Parabola** | Line Mode **OFF** | 1. Click Point 1. 2. Click Point 2. 3. Click Point 1 or 2 as the Vertex. | Parabola (cut at P1 & P2) |
| **Line Segment** | Line Mode **ON** | 1. Click Point 1. 2. Click Point 2. | Line Segment (between P1 & P2) |

---

## 🛠️ 4. Tools Explained

| Tool | Shortcut | Action | Description |
| :--- | :--- | :--- | :--- |
| **Draw** | D | Click sequence (see above) | Creates a Parabola or Line Segment based on the Line Mode toggle. |
| **Erase** | E | Click on a curve | Permanently deletes the selected curve. |
| **Resize** | R | Click, then Drag endpoint | Allows adjustment of a curve's endpoints (P1, P2). |
| **Img Tool** | I | Drag body, Drag corner handles | Used to move the entire background image or resize it proportionally. |

---

## ⌨️ 5. Keyboard Shortcuts

| Key Combination | Action |
| :--- | :--- |
| **Ctrl + Z** (or **Cmd + Z**) | Undo last action (curve creation, resize, delete). |
| **Ctrl + Y** (or **Cmd + Y**) / **Ctrl + Shift + Z** | Redo last undone action. |
| **Scroll** (Mouse Wheel) | Zoom the canvas grid in or out. |
| **Ctrl + Scroll** / **Ctrl + +/-** | Fine-tune zoom. |
| **Alt + Drag** (or **Middle Mouse**) | Pan the canvas view. |
| **Esc** | Cancel any multi-step drawing process (e.g., stop placing points for a parabola). |
| **E** | Toggle the Eraser tool. |
| **R** | Toggle the Resize tool. |

---

## 💾 6. Data Management

The application manages two primary data types:

1.  **Curves Data:** Stored as an array of JSON objects (curves). Each object contains point data (`p1`, `p2`, etc.), curve-specific parameters (`a`, `h`, `k` for parabola, `m`, `b` for line), and color information. This data can be manually exported/imported using the corresponding buttons.
2.  **Configuration Data:** Includes `gridSize`, `panOffsetX`, `lightMode`, `bgGridX/Y/Width`, etc. This data is automatically saved to and loaded from `localStorage` in the browser to maintain the view state across sessions.

---

## ⚠️ 7. Known Limitations

*   Sometimes the same colour code is assigned to two different lines, which may cause the tracking to fail.
*   Support for arc drawing (partial circle) is unfinished and requires future development work.
*   Might potentially include support for bezier curves and exponential equations.
### License: MIT
