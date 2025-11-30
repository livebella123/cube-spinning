# 🧊 ASCII Spinning Cubes

An animated **3D ASCII renderer** written in C, capable of displaying multiple rotating cubes directly in the terminal.  
This project demonstrates how to simulate a basic 3D engine using manual rotation matrices, projection math, and z-buffering — all without external graphics libraries.

---

## 📸 Preview (Concept)
    @@@$$$$####~~~~
  @@@$$$$####~~~~
@@@$$$$####~~~~

*(Real output is animated inside the terminal.)*

---

## 🚀 Features

- 🔄 **Real-time rotating ASCII cubes**
- 🧮 **Manual 3D math** (rotation, projection)
- 📏 **Depth management** via z-buffer
- 🎨 Different ASCII characters for cube faces
- 📐 Three cubes of different sizes and offsets
- ⚙️ Cross-platform sleep implementation (POSIX / Windows)
- 🖥️ Works in any ANSI-compatible terminal

---

## 📂 File Structure


---

## 🛠️ Installation & Compilation

### Linux / macOS
```bash
gcc spinning_cubes.c -o cubes -lm
```
### Windows (MinGW)
``` bash
gcc spinning_cubes.c -o cubes -lm
```

### ▶️ Run the Program
``` bash
./cubes
```

### 🧠 How It Works (Technical Overview)

- 3D Rotation
Each point is rotated using trigonometric functions based on angles A, B, and C.
These correspond to X-axis, Y-axis, and Z-axis rotation.
-  Projection 3D coordinates (x, y, z) are projected into 2D terminal space using:
``` bash
xp = width  / 2 + K1 * (x / z)
yp = height / 2 + K1 * (y / z)
```
- Z-Buffer
  A float array zBuffer[] stores (1/z) Closer elements overwirte father ones.
- ASCII shading
  Each face of each cube uses a different character:
  ``` bash
  @ $ ~ # ; +
  ```
- Frame Rendering
  Each frame:
  - buffers are cleared
  - cubes are recalculated
  - terminal cursor reset (\x1b[H)
  - the full ASCII frame is printed

---

📏 Customization
You can tweak:
| Variable              | Meaning                    |
| --------------------- | -------------------------- |
| `cubeWidth`           | Size of cubes              |
| `incrementSpeed`      | Density of points          |
| `A`, `B`, `C`         | Rotation speed             |
| `backgroundASCIICode` | Background character       |
| `width`, `height`     | Terminal resolution buffer |

---

🤝 Contributing
Pull request, suggestions, or improvements (optimizations, new shapes, etc.) are welcome!
