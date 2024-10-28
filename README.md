# DAY_027 | Infinite Scroll Slider Carousel with GSAP Animation

## Project Overview

For **DAY_027** of my daily code challenge series, I built an **infinite scroll slider carousel** using **HTML**, **CSS**, **JavaScript**, and **GSAP**. This carousel features smooth, continuous slide transitions, dynamic SVG animations, and a magnetic mousemove effect on a button, creating an immersive, interactive experience. The project showcases advanced animation techniques with GSAP and creative JavaScript interactivity.

---

### Inspiration from Award-Winning Interactive Design

The infinite scroll carousel was inspired by the **Awwwards Element** from the **Dezea Digital** site, known for its smooth, engaging visual effects and sophisticated scroll interactions.

Explore their work here: [Dezea Digital](https://dezea.digital/)

---

## Preview

![DAY_027_1](./assets/DAY_027_1.gif)

## Inspiration
![Dezea Digital site](./assets/DAY_027_2.gif)

---

## Key Features

- **Infinite Scroll with GSAP**: The carousel transitions seamlessly through each slide, cycling back to the start after the last slide for an endless scroll effect.
- **Dynamic SVG Animations**: The project includes a rotating SVG path animation, adding depth to the design.
- **Magnetic Mousemove Button**: A button with a magnetic effect tracks the mouse position, adding an engaging interactive element.
- **Smooth Transition Effects**: Each slide transition is smooth and visually captivating, thanks to GSAP animations on scale, position, and opacity.

---

## JavaScript and Animation Details

### JavaScript Libraries Used

1. **GSAP (GreenSock Animation Platform)**:
   - Handles animations for smooth transitions, scale adjustments, and interactive elements.
2. **script.js**:
   - Manages carousel controls, infinite scrolling logic, SVG animation, and mouse-following magnetic effects.

### Infinite Scroll and Carousel Controls

The carousel allows users to scroll endlessly in either direction, looping back to the start after reaching the last slide. JavaScript manages the continuous scroll by updating the slide index and dynamically loading each slide.

#### Key Code for Infinite Scroll

```javascript
function showNextSlide() {
    const currentSlide = document.querySelector(`#slide-${currentSlideIndex}`);
    currentSlideIndex = currentSlideIndex < totalSlides ? currentSlideIndex + 1 : 1;

    let nextSlide = document.querySelector(`#slide-${currentSlideIndex}`);
    if (!nextSlide) {
        nextSlide = createSlide(currentSlideIndex);
        sliderContainer.appendChild(nextSlide);
    }

    animateSlideTransition(currentSlide, nextSlide, "down");
}
```

### Magnetic Mousemove Button

The mouse-tracking button effect uses GSAP to animate the button’s position relative to the cursor, creating a "magnetic" attraction that follows the user’s movements.

#### Code for Magnetic Effect

```javascript
let xTo = gsap.quickTo(linkWrapper, "x", { duration: 0.4, ease: "power3" }),
    yTo = gsap.quickTo(linkWrapper, "y", { duration: 0.4, ease: "power3" });

link.addEventListener("mousemove", (e) => {
    const rect = link.getBoundingClientRect();
    const relX = e.clientX - rect.left - rect.width / 2;
    const relY = e.clientY - rect.top - rect.height / 2;

    xTo(relX * 0.5);
    yTo(relY * 0.5);
});
```

### SVG Animation

The SVG animation is designed to rotate and follow a defined path, enhancing the carousel’s dynamic aesthetic. It’s achieved through GSAP’s powerful animation capabilities, making the effect smooth and visually appealing.

---

## How to Run

1. **Clone the repository**:

   ```bash
   git clone https://github.com/thounny/DAY_027.git
   ```

2. **Navigate to the project directory**:

   ```bash
   cd DAY_027
   ```

3. **Open the `index.html` file** in your browser, or use a local development server like **Live Server** in VSCode.

---

## Project Structure

```bash
DAY_027/
│
├── assets/
├── fonts/
├── images/
├── index.html
├── script.js
├── styles.css
```

---

## Technologies Used

- **HTML5**: Provides the structural elements for the slider.
- **CSS3**: Handles styling, responsive layout adjustments, and custom animations.
- **JavaScript (ES6)**: Manages scroll controls, infinite loop logic, and interactive effects.
- **GSAP (GreenSock Animation Platform)**: Powers the animations, including scaling, opacity, SVG transitions, and magnetic button effects.

---

## Author

![Logo](./assets/index_dwn.gif)

**Thounny Keo**  
Creative Developer & Designer  
Frontend Development Student | Year Up United

---

![miku](./assets/miku.gif)