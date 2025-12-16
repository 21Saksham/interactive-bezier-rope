# interactive-bezier-rope

# Interactive Cubic Bézier Rope

This project demonstrates a real-time interactive simulation of a **cubic Bézier curve** that behaves like a flexible rope.  
The curve dynamically responds to user input and visualizes its tangents, showcasing core concepts in **mathematics, graphics programming, and basic physics**.

---

## 🎯 Objective

To implement a cubic Bézier curve from scratch that:
- Responds smoothly to user input
- Uses spring–damping physics for natural motion
- Visualizes tangent vectors along the curve
- Runs in real time at ~60 FPS

No external libraries or built-in Bézier utilities are used.

---

## 📐 Bézier Curve Mathematics

A cubic Bézier curve is defined using four control points:

- **P₀, P₃** → Fixed endpoints  
- **P₁, P₂** → Dynamic control points  

The curve equation is:

B(t) = (1 − t)³P₀
+ 3(1 − t)²tP₁
+ 3(1 − t)t²P₂
+ t³P₃


The curve is rendered by sampling values of `t` from `0` to `1` at small intervals and connecting the resulting points.

---

## 📈 Tangent Computation

Tangent vectors are computed using the derivative of the cubic Bézier curve:


B'(t) = 3(1 − t)²(P₁ − P₀)
+ 6(1 − t)t(P₂ − P₁)
+ 3t²(P₃ − P₂)

  
These vectors are normalized and drawn at several points along the curve to visualize its direction and curvature.

---

## 🧲 Spring–Damping Physics Model

To simulate rope-like motion, the dynamic control points follow a spring model:

acceleration = -k × (position − target) − damping × velocity


Where:
- `k` is the spring stiffness
- `damping` controls oscillation
- Velocity and position are updated each animation frame

This produces smooth, elastic motion rather than abrupt movement.

---

## 🖱️ Interaction

- Mouse movement defines target positions for the dynamic control points
- Control points smoothly follow the target using spring physics
- The Bézier curve updates in real time

---

## 🖥️ Rendering

The visualization includes:
- The cubic Bézier curve
- Control points displayed as circles
- Tangent vectors drawn along the curve

Rendering is handled using **HTML5 Canvas** and `requestAnimationFrame` to maintain smooth animation.

---

## 🚀 How to Run

1. Download or clone the repository
2. Open `index.html` in any modern web browser
3. Move the mouse to interact with the curve

No additional setup or dependencies are required.

---

## 📁 Project Structure

project-folder/
│
├── index.html
└── README.md


---

## 📌 Key Notes

- All Bézier math and physics are implemented manually
- No animation, physics, or graphics libraries are used
- Designed to demonstrate core concepts in math, graphics, and real-time interaction

---

## 🎥 Demo

A short screen recording demonstrates:
- Interactive input
- Spring-based motion
- Tangent visualization

---

## 👤 Author

Implemented as part of a graphics and interaction programming assignment.
