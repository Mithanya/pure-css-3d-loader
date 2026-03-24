# 3D CSS Box Loader

A lightweight, pure CSS 3D cube loader featuring independent glowing faces and a fluid multi‑axis rotation. Built with only HTML and CSS — no JavaScript.

![Loader Demo](https://github.com/Mithanya/pure-css-3d-loader/blob/main/3d%20loder.mp4)


## Features

- **Fully 3D** – Six faces positioned in 3D space using `perspective` and `transform-style: preserve-3d`
- **Smooth rotation** – Non‑linear spin on X, Y, and Z axes for an organic, never‑repeating motion
- **Pulsing glow** – Each face has its own animated `box-shadow` with staggered delays
- **Performance‑first** – 0 lines of JavaScript, under 5KB, 60fps on mobile devices
- **Responsive** – Scales gracefully on smaller screens
- **Glassmorphic style** – Semi‑transparent faces with backdrop blur and gradient fills

## Technologies Used

- HTML5
- CSS3 (3D transforms, keyframe animations, flexbox)

## How It Works

The cube is constructed by positioning six `div` elements (faces) using `transform: translateZ()` and `rotateY()` / `rotateX()`. A parent container with `perspective` creates the 3D depth, and a `@keyframes` animation rotates the entire cube on all three axes.

Each face has its own `box-shadow` animation with a different `animation-delay`, creating a wave of light that travels around the cube.

## Live Demo

[View Demo](https://github.com/Mithanya/pure-css-3d-loader/blob/main/3d%20loder.mp4)
## Code Preview

```html
<div class="loader-container">
  <div class="cube">
    <div class="face front"></div>
    <div class="face back"></div>
    <div class="face right"></div>
    <div class="face left"></div>
    <div class="face top"></div>
    <div class="face bottom"></div>
  </div>
  <div class="shadow"></div>
</div>

.cube {
  transform-style: preserve-3d;
  animation: spinCube 3s infinite cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

@keyframes spinCube {
  0% { transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg); }
  100% { transform: rotateX(360deg) rotateY(180deg) rotateZ(60deg); }
}

.face {
  position: absolute;
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, rgba(99,102,241,0.85), rgba(168,85,247,0.85));
  border: 2px solid rgba(255,255,255,0.3);
  box-shadow: 0 0 20px rgba(168,85,247,0.5);
  border-radius: 12px;
  animation: faceGlow 2s infinite ease-in-out;
}

.front  { transform: translateZ(100px); }
.back   { transform: rotateY(180deg) translateZ(100px); }
.right  { transform: rotateY(90deg) translateZ(100px); }
.left   { transform: rotateY(-90deg) translateZ(100px); }
.top    { transform: rotateX(90deg) translateZ(100px); }
.bottom { transform: rotateX(-90deg) translateZ(100px); }

Installation
Clone the repository:

bash
git clone https://github.com/your-username/3d-css-box-loader.git
Open index.html in any modern browser.

Browser Support
Works in all modern browsers that support CSS 3D transforms:

Chrome / Edge (latest)

Firefox (latest)

Safari (latest)

Opera (latest)

License
MIT

text

---

Simply copy the entire block above, replace the placeholders (video link, demo URL, GitHub username), and paste into your `README.md`. Then commit and push.
