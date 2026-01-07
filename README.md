# asnadc.com
**Single-file personal landing page** implementing raw WebGL raymarching and vanilla JavaScript architecture, available at **[asnadc.com](https://asnadc.com)**

## Concept
This project prioritizes raw web standards over the volatile ecosystems of frontend frameworks, creating an immersive experience with just a few kilobytes of code, completely free from heavy dependencies or complex build tools.

## Technical Stack
* Architecture: Single-File Component (HTML5/CSS3/JS);
* Graphics: WebGL 1.0 API + GLSL Fragment Shader (selected for maximum cross-device compatibility);
* External Dependencies: None;
* Assets: Base64 encoded inline SVG (Favicon).

## Implementation Details

### Visuals (GLSL Fragment Shader)
The visual core is a custom program written in GLSL (OpenGL Shading Language) executed directly on the GPU. Instead of standard polygon rasterization, the Fragment Shader determines the color of every single pixel via Raymarching.
* Distance Function: Generates fractal geometry using iterative space folding, absolute positioning, and clamping;
* Rendering: Per-pixel ray casting calculating surface distance and depth;
* Post-Processing: Distance-based fog mixing for depth perception.

### Performance & Optimization
* Bot Detection Logic: Regex-based analysis of navigator.userAgent;
    * Action: Disables WebGL context initialization for crawlers,
    * Result: Static fallback background, instant TTI, and maximized SEO scoring.
* Resource Management: Listens to visibilitychange events;
    * Action: Immediate cancellation of requestAnimationFrame loop when the tab is inactive,
    * Result: Zero CPU/GPU usage in background.
* Context Config: Disables antialias and depth buffers to minimize GPU memory footprint.

### Styling & Layout
* CSS Variables: Centralized theme management;
* Layout: Flexbox for vertical/horizontal centering; z-index layering for canvas/overlay separation;
* Animations: Hardware-accelerated CSS transitions for entry effects and hover states.

## Usage
No build pipeline, package manager, or bundler required.

* Open index.html in any browser;
* That's it.

## License
Distributed under the MIT License, see [LICENSE](LICENSE) for more information.
