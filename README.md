# 🪐 Dreaming of Jupiter - A Three.js Scene

## Project Name: Dreaming of Jupiter

An immersive 3D scene built with **Three.js** that simulates a cosmic environment. The scene features a central moon orbiting a large, distant planet, an animated foreground terrain, and a dynamic field of moving stars, all viewed from a subtly moving camera.

> **Note:** As indicated in `script.js`, this code is an archived, early work and may not be production-ready.

## ✨ Features

* **Three.js Environment:** Utilizes the Three.js library for WebGL rendering of the 3D scene .
* **Planetary System:** Features a main, large planet (appears Saturn/Jupiter-like based on the texture URL in the code) and a smaller, orbiting moon.
    * The **Planet** rotates slowly on its Y-axis (`planet.rotation.y += 0.002`).
    * The **Moon** orbits the planet in an elliptical path using trigonometric functions (`moon.position.x = 15 * Math.cos(t)` and `moon.position.z = 20 * Math.sin(t)`).
* **Animated Terrain:** A foreground plane geometry is dynamically deformed using a sine wave function in the `animate` loop to create a sense of moving, undulating terrain or water.
* **Dynamic Stars/Lines:** A field of **1000 lines** is used to represent stars or fast-moving streaks. Their Z-position is continuously reset when they move too far, creating a sense of forward motion and depth.
* **Camera Movement:** The camera subtly moves back and forth on the X-axis (`camera.position.x`) and bobs up and down on the Y-axis (`camera.position.y`) using a cyclical frame counter, enhancing the immersion.
* **Background Sphere:** A large sphere with a star texture covers the background, rotating slowly to add subtle motion to the environment.
* **Performance Control:** Uses a custom `limitFPS` function with `clock.getDelta()` to ensure the rendering loop runs at a capped rate (e.g., 60 FPS), improving performance consistency.
* **Fullscreen Toggle:** A simple button allows the user to easily switch between normal and fullscreen viewing modes.

## 🛠️ Technology Stack

* **HTML (`index.html`):** The basic page structure, including the `#canvas_container` for the Three.js renderer and the fullscreen button.
* **CSS (`style.css`):** Basic styling, setting the canvas to full screen, and styling the fullscreen button. It also sets a starry background image as a fallback/initial loader.
* **JavaScript (`script.js`):** The core application logic.
    * **Three.js Library (r120):** Used for 3D object creation, scene setup, lighting, and rendering.

## 🚀 Getting Started

1.  **Clone the Repository:**
    ```bash
    git clone [Your Repository URL]
    ```
2.  **Run Locally:**
    Since this project relies on external texture links and uses JavaScript, it's best viewed by serving the files via a local server (due to browser security restrictions on local file access).
    * Open `index.html` in your web browser.
3.  **Interaction:**
    * Click the **"Go Fullscreen"** button for an immersive experience.
    * The scene is fully animated and self-running.

## ⚙️ Key Three.js Components

| Component | Object | Purpose |
| :--- | :--- | :--- |
| **`Scene`** | `scene` | The container for all objects, lights, and cameras. Sets a black background and a fog effect (`#3c1e02`). |
| **`Camera`** | `camera` | A `PerspectiveCamera` positioned at `(0, 1, 32)` that moves dynamically in the `animate` loop. |
| **`Planet`** | `planet` | A `MeshLambertMaterial` sphere using an external Saturn/Jupiter texture. |
| **`Moon`** | `moon` | A `MeshPhongMaterial` sphere with an external moon texture, orbiting the planet. |
| **`Stars`** | `lines` | A `LineSegments` object created using `BufferGeometry` to render 1000 dynamic, animated lines for star trails. |
| **`Terrain`** | `terrain` | A `PlaneBufferGeometry` whose vertices are manipulated every frame to create a wave-like effect. |
| **`Background`** | `sphereBg` | A very large sphere with a star map texture rendered on the inside (`side: THREE.BackSide`). |

## 📸 Screenshots

*(Add a screenshot or GIF of your interactive cube here)*
