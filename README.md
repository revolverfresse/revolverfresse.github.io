Here’s the README.md in English:

---

# Complex Function Visualizer

This project visualizes complex functions using two HTML5 canvas elements. It leverages the `complex.min.js` library for complex number calculations and generates interactive visualizations based on random values.

## Features

- **Primary Visualization (cv1)**:  
  Displays a color-coded representation of the iterations of a complex function across a defined grid.
- **Path Tracing (cv2)**:  
  Visualizes the iterative path of a complex starting value, determined by mouse position.
- **Real-Time Interactivity**:  
  Mouse movements dynamically alter the visualizations.

## Technologies

- HTML5 Canvas
- JavaScript (ES6+)
- Complex number library: `complex.min.js`

## Installation

1. **Prerequisites**:
   - A modern browser with support for JavaScript and Canvas.

2. **Project Files**:
   Save the files into a directory. The main file is `index.html`.

3. **Run**:
   Open `index.html` in your browser.

## File Structure

- **index.html**: Contains the HTML and embedded JavaScript for the project.
- **complex.min.js**: Library for complex number calculations. (External dependency)

## Project Structure

```
Complex Function Visualizer/
├── index.html       # Main project file
├── complex.min.js   # Complex number library
```

## Logic Explanation

1. **Random Value Generation**:
   A `Float32Array` stores random values used for perturbations in the calculations.

2. **Complex Function `f(c)`**:
   ```javascript
   function f(c) {
       r = 0;
       return c.pow(c.div(c.add(nr(), nr())))
                .mul(c.div(c.add(nr(), nr())))
                .add(new Complex(nr(), nr()).div(c.add(nr(), nr())));
   }
   ```
   This function applies multiple transformations to the complex number `c` and uses random values for modulation.

3. **Mouse Interaction**:
   - Mouse coordinates are used to determine the starting value for the function in the second canvas.
   - Canvas elements update dynamically on `mousemove`.

4. **Rendering Logic**:
   - Iterative computation of the function.
   - Color-coded iteration results.
   - Real-time rendering with a frame interval of approximately 100 ms.

## Usage

1. **Primary Canvas (cv1)**:
   - Move the mouse over the first canvas to see crosshairs aligned with the current mouse position.
   - Colors represent the iteration results of the function.

2. **Path Canvas (cv2)**:
   - Displays the iterative path of the function, starting at the position determined by the mouse coordinates.

## Customization

- **Change the Function**:  
  Replace the logic in `f(c)` to visualize different complex functions.
- **Canvas Dimensions**:  
  Adjust the width and height of the canvas elements in the HTML tags.
- **Iterations and Random Values**:  
  Modify the number of iterations or the random value generation logic.

## Preview

```html
<canvas id="cv1" width=100 height=100></canvas>
<canvas id="cv2" width=100 height=100></canvas>
```

## License

This project is open source. Feel free to use and modify the code as needed.

---

Let me know if there’s anything else to add or modify!
