# 🧊 3D Cube Grid Interactive Animation

A lightweight **3D isometric cube grid animation** built with **pure HTML, CSS, and JavaScript**.

When the mouse moves across the screen:

- Cubes **shrink in height** depending on their distance from the cursor.
- Cubes **change color gradually** from **white → indigo shades → black**.
- A real-time **counter label** displays the number of active (shrunk) nodes.

This project demonstrates interactive UI effects, GPU-friendly CSS 3D transforms, and smooth gradient-based animations without external libraries.

---

## 🎥 Demo

*(Insert a GIF or video preview here, e.g. demo.gif)*

---

## ✨ Features

- **3D Isometric View**: The cube grid is rotated in 3D space using `rotateX` and `rotateZ`.
- **Mouse-based Interaction**: Cubes shrink when the mouse comes close.
- **Gradient Color Transition**: The nearest cube to the mouse turns **white**, and distant cubes gradually fade through **light indigo → indigo → dark indigo → black**.
- **Optimized Animations**:
    - Uses `requestAnimationFrame` for smooth rendering.
    - Adjustable **effect radius** for performance control.
- **No Dependencies**: Pure **vanilla HTML/CSS/JS**. Works in all modern browsers.

---

## 📂 Project Structure

.
├── index.html # Main entry point
├── style.css # (inline in HTML, but can be externalized)
├── [README.md](http://readme.md/) # Documentation
└── demo.gif # (optional preview of animation)

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <https://github.com/your-username/3d-cube-grid.git>
cd 3d-cube-grid
```

### 2. Open in Browser

Simply open **`index.html`** in any modern browser (**Chrome, Firefox, Edge**).

---

## ⚙️ Configuration

You can tweak these values inside **`index.html`**:

```jsx
const gridSize = 10;       // Number of cubes per row/column (10x10 grid)
const effectRadius = 120;  // Mouse effect radius (px)
```

### 🎨 Gradient Colors

The color mapping can be customized by editing the **`colors` array**:

```jsx
const colors = [
  [255, 255, 255],   // White (closest to mouse)
  [197, 210, 255],   // Light Indigo
  [129, 140, 248],   // Indigo
  [79, 70, 229],     // Dark Indigo
  [0, 0, 0]          // Black (farthest)
];
```

Each entry is an **RGB triplet**. The animation interpolates colors smoothly between these stops.

## 🖥️ Technical Details

- **Cubes**: Each cube is composed of 6 `.cube-face` elements (front, back, left, right, top, bottom).
- **3D Perspective**: The container (`.scene`) uses `perspective` and `transform-style: preserve-3d`.
- **Scaling Animation**: `scaleZ()` is applied to shrink cubes vertically.
- **Color Interpolation**: Distance ratio → maps into the `colors[]` gradient array.
- **Performance Optimization**:
    - Uses **`requestAnimationFrame`** to sync updates with browser’s refresh rate.
    - Limits effect radius to reduce DOM operations on far-away cubes.
    - Only recalculates cube transforms on mouse move.

---

## 📊 Performance Tips

- Reduce `gridSize` (e.g., from `10` to `8`) for fewer DOM elements.
- Lower `effectRadius` for smaller hover area → less computation.
- Use **CSS `will-change: transform`** if you want smoother scaling on low-end devices.

## 🔮 Future Enhancements

- [ ]  Add **glowing ripple effect** (light spreads outward on mouse hover).
- [ ]  Enable **click-to-freeze** animation snapshots.
- [ ]  Add **dynamic cube textures** instead of flat colors.
- [ ]  Port to **WebGL (Three.js)** for GPU-powered performance with larger grids.

---

## 📜 License

MIT License © 2025 Jyotirmoy Baidya

Free to use, modify, and distribute.

---

## 🙌 Acknowledgments

- Inspired by modern UI motion design trends.
- Built as an experiment to explore **3D transforms + gradient animations** in pure CSS/JS.

```
Do you want me to also add a **“Quick Code Snippet”** section (so someone can just copy-paste the working dem
```