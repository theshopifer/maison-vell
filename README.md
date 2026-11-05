# Maison Vell — Runway Depth Lookbook

An immersive, high-fashion interactive runway lookbook inspired by luxury haute couture presentations. Six models stand along a receding depth diagonal that extends into a soft atmosphere; dragging, scrolling, or navigating via keyboard walks the line forward in real-time with continuous looping, dynamic depth blur, synchronized product rail transitions, and fluid typography counters.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Ftheshopifer%2Fmaison-vell)

---

## ✨ Features

- **Unified Mathematical Parameter (`p`)**: One single floating-point coordinate controls every visual element in the viewport—model scale, 3D translation, depth blur, opacity, product rail translation, and rolling numeral indexing.
- **Physics-Based Table-Driven Depth**: Uses a 7-stop discrete depth mapping ($d = -1$ to $5$) linearly interpolated across coordinate vectors:
  - `KX`: Normalized center $X$ positioning across the stage
  - `KF`: Feet baseline $Y$ alignment
  - `KH`: Proportional viewport model height
  - `KB`: Depth of field blur radius (compensated by layer scale)
  - `KO`: Distance opacity and fog attenuation
- **Dual High-Resolution Sprite Sheets**:
  - **Models Sheet (3840 × 2160)**: Transparent 6-model lineup dynamically isolated via responsive nested SVG `<svg viewBox>` viewports.
  - **Products Sheet (2400 × 720)**: 12 individual fashion items mapped with pixel-exact coordinates.
- **Kinetic Multi-Input Controls**:
  - **Direct Pointer Dragging**: 1:1 cursor tethering with momentum easing and automatic magnetic snapping on release.
  - **Mouse Wheel / Trackpad**: Seamless delta accumulation with automatic debounce snapping.
  - **Keyboard Navigation**: Arrow keys (`ArrowLeft`, `ArrowRight`, `ArrowUp`, `ArrowDown`) navigate forward and backward by look index.
  - **Click-to-Focus**: Selecting any visible model in the line smoothly advances the runway directly to that look.
- **Interactive Custom Ring Cursor**: Custom 46px kinetic follower with elastic interpolation that smoothly morphs into an 84px × 34px pill indicator during drag operations.
- **Looping Product Rail**: Infinite vertically-scrolling 3-card presentation displaying synchronized garment items, interactive wishlist bookmark toggles, and live cart counter increments.
- **Adaptive Responsive Architecture**: Seamlessly scales from ultra-wide 4K down to mobile viewports (≤ 820px), where it transforms into a bottom-docked horizontal runway strip.
- **Zero Runtime UI Dependencies**: Built with vanilla JavaScript, modern CSS custom properties (`--u`), hardware-accelerated 3D transforms (`translate3d`), and typography from Google Fonts (`Michroma` & `Inter`).

---

## 📐 Depth Matrix & Mechanics

| Depth ($d$) | Center X (`KX`) | Feet Y (`KF`) | Height (`KH`) | Blur (`KB`) | Opacity (`KO`) | Status |
| :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **-1** | 1.200 | 1.140 | 1.180 | 0.0px | 1.00 | Exiting stage right behind rail |
| **0** | 0.744 | 0.890 | 0.832 | 0.0px | 1.00 | Primary focal runway position |
| **1** | 0.496 | 0.777 | 0.574 | 1.5px | 1.00 | Immediate successor |
| **2** | 0.346 | 0.704 | 0.436 | 4.0px | 1.00 | Mid-distance runway lineup |
| **3** | 0.235 | 0.651 | 0.334 | 8.0px | 0.86 | Receding perspective |
| **4** | 0.150 | 0.616 | 0.258 | 12.0px | 0.50 | Atmospheric haze entry |
| **5** | 0.085 | 0.590 | 0.190 | 17.0px | 0.00 | Distant horizon vanishing point |

---

## 🚀 Quick Start

### Prerequisites
- [Node.js](https://nodejs.org/) (v18.0.0 or later recommended)
- [npm](https://www.npmjs.com/) or [pnpm](https://pnpm.io/)

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/theshopifer/maison-vell.git
   cd maison-vell
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start local development server**:
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

4. **Build for production**:
   ```bash
   npm run build
   ```

5. **Preview production build locally**:
   ```bash
   npm run preview
   ```

---

## 🌐 Deploy to Vercel

This repository is optimized for one-click, zero-configuration deployment on **Vercel**:

1. Push your repository to GitHub:
   ```bash
   git remote add origin https://github.com/theshopifer/maison-vell.git
   git branch -M main
   git push -u origin main
   ```
2. Log into [Vercel](https://vercel.com) and click **"Add New..."** > **"Project"**.
3. Import the `maison-vell` repository.
4. **Vercel Settings**:
   - **Framework Preset**: `Vite`
   - **Build Command**: `npm run build` (or `vite build`)
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`
5. Click **Deploy**.

---

## 📁 Project Structure

```text
maison-vell/
├── index.html         # Main entry point: responsive stage, SVG sprite crops, depth engine
├── metadata.json      # Applet metadata & capabilities specification
├── package.json       # Project manifest, dependencies, and build scripts
├── tsconfig.json      # TypeScript compiler configuration
├── vite.config.ts     # Vite bundling configuration with Tailwind & React plugins
├── .gitignore         # Version control exclusion rules
└── README.md          # Project documentation
```

---

## 📬 Contact & Support

Developed for **Maison Vell** haute couture digital experiences.

- **Developer / Maintainer**: [theshopifer@gmail.com](mailto:theshopifer@gmail.com)
- **Repository**: [https://github.com/theshopifer/maison-vell](https://github.com/theshopifer/maison-vell)

---

## 📄 License

This project is licensed under the Apache-2.0 License.
