# Complete Guide to HTML5 and CSS3 Features

## Table of Contents
1. [HTML5 Features](#html5-features)
2. [CSS3 Features](#css3-features)
3. [Best Practices](#best-practices)
4. [Resources](#resources)

---

## HTML5 Features

### 1. Semantic Elements

Semantic HTML provides meaning to web content, improving accessibility and SEO.

#### **`<header>`**
```html
<header>
  <h1>Website Title</h1>
  <p>Welcome to my website</p>
</header>
```
- Defines the header of a page or section
- Typically contains logos, navigation, or introductory content

#### **`<nav>`**
```html
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```
- Represents navigation links
- Helps screen readers identify navigation areas

#### **`<main>`**
```html
<main>
  <article>
    <h2>Article Title</h2>
    <p>Article content goes here...</p>
  </article>
</main>
```
- Specifies the main content of the document
- Only one `<main>` per page
- Improves document structure

#### **`<article>`**
```html
<article>
  <h2>Blog Post Title</h2>
  <p class="meta">Posted on June 22, 2026</p>
  <p>This is a self-contained piece of content...</p>
</article>
```
- Self-contained, independent content
- Can be reused, distributed, or syndicated
- Examples: blog posts, news articles, comments

#### **`<section>`**
```html
<section>
  <h2>Services</h2>
  <p>We offer professional services...</p>
</section>
```
- Thematic grouping of content
- Different from `<article>` (not necessarily independent)
- Use for chapters, tabbed content, etc.

#### **`<aside>`**
```html
<aside>
  <h3>Related Links</h3>
  <ul>
    <li><a href="#">Link 1</a></li>
    <li><a href="#">Link 2</a></li>
  </ul>
</aside>
```
- Sidebar or supplementary content
- Content indirectly related to main content
- Examples: sidebars, call-out boxes

#### **`<footer>`**
```html
<footer>
  <p>&copy; 2026 My Website. All rights reserved.</p>
  <ul>
    <li><a href="#privacy">Privacy Policy</a></li>
    <li><a href="#terms">Terms of Service</a></li>
  </ul>
</footer>
```
- Defines footer of page or section
- Contains copyright, contact info, related links

#### **`<figure>` and `<figcaption>`**
```html
<figure>
  <img src="chart.png" alt="Sales Chart">
  <figcaption>Fig. 1: Monthly Sales Data</figcaption>
</figure>
```
- `<figure>`: Container for illustrations, diagrams, photos
- `<figcaption>`: Caption for the figure

---

### 2. Multimedia Elements

#### **`<video>`**
```html
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  Your browser does not support the video tag.
</video>
```
- Attributes:
  - `controls`: Show play/pause buttons
  - `autoplay`: Start playing automatically
  - `loop`: Restart video when finished
  - `muted`: Mute audio
  - `width`, `height`: Dimensions

#### **`<audio>`**
```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  Your browser does not support the audio element.
</audio>
```
- Attributes same as video: `controls`, `autoplay`, `loop`, `muted`
- Provide multiple formats for compatibility

#### **`<canvas>`**
```html
<canvas id="myCanvas" width="200" height="200"></canvas>

<script>
  const canvas = document.getElementById('myCanvas');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = 'red';
  ctx.fillRect(10, 10, 150, 150);
</script>
```
- Container for graphics drawn with JavaScript
- Used for charts, animations, games
- 2D and 3D (WebGL) rendering support

#### **`<svg>`**
```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" fill="yellow" />
  <rect x="10" y="10" width="30" height="30" fill="blue" />
</svg>
```
- Scalable Vector Graphics
- Resolution-independent
- Can be styled with CSS and animated

---

### 3. Form Enhancements

#### **New Input Types**

```html
<form>
  <!-- Email input with validation -->
  <input type="email" placeholder="Enter your email" required>
  
  <!-- Number input -->
  <input type="number" min="1" max="100" step="5">
  
  <!-- Date picker -->
  <input type="date">
  
  <!-- Time picker -->
  <input type="time">
  
  <!-- Date and time -->
  <input type="datetime-local">
  
  <!-- Month selector -->
  <input type="month">
  
  <!-- Week selector -->
  <input type="week">
  
  <!-- Color picker -->
  <input type="color" value="#ff0000">
  
  <!-- Range slider -->
  <input type="range" min="0" max="100">
  
  <!-- Telephone -->
  <input type="tel" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">
  
  <!-- URL -->
  <input type="url" placeholder="https://example.com">
  
  <!-- Search -->
  <input type="search" placeholder="Search...">
</form>
```

#### **`<datalist>`**
```html
<input list="browsers">
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Safari">
  <option value="Edge">
</datalist>
```
- Provides predefined options
- Dropdown suggestions for input field

#### **`<progress>`**
```html
<progress value="70" max="100"></progress>
```
- Shows progress of a task
- `value`: Current value
- `max`: Maximum value (default 1)

#### **`<meter>`**
```html
<meter value="6" min="0" max="10" low="3" high="7" optimum="8"></meter>
```
- Represents a measurement
- `low`: Low range
- `high`: High range
- `optimum`: Optimal value

#### **Form Validation Attributes**
```html
<form>
  <!-- Required field -->
  <input type="text" required>
  
  <!-- Min/Max values -->
  <input type="number" min="10" max="50">
  
  <!-- Pattern matching (regex) -->
  <input type="text" pattern="[A-Z]{3}[0-9]{4}">
  
  <!-- Length constraints -->
  <input type="text" minlength="5" maxlength="20">
  
  <!-- Step increments -->
  <input type="number" step="0.5">
  
  <!-- Multiple selections -->
  <input type="file" multiple>
  
  <button type="submit">Submit</button>
</form>
```

---

### 4. HTML5 Storage APIs

#### **Local Storage**
```javascript
// Store data (persists until manually deleted)
localStorage.setItem('username', 'John');
localStorage.setItem('theme', 'dark');

// Retrieve data
let username = localStorage.getItem('username');

// Remove item
localStorage.removeItem('username');

// Clear all
localStorage.clear();

// Get item count
console.log(localStorage.length);

// Iterate through all items
for (let i = 0; i < localStorage.length; i++) {
  let key = localStorage.key(i);
  console.log(key + ': ' + localStorage.getItem(key));
}
```

#### **Session Storage**
```javascript
// Store data (persists only for the session)
sessionStorage.setItem('tempData', 'value');

// Retrieve data
let data = sessionStorage.getItem('tempData');

// Same methods as localStorage
sessionStorage.removeItem('tempData');
sessionStorage.clear();
```

#### **Differences**
| Feature | Local Storage | Session Storage |
|---------|--------------|-----------------|
| Persistence | Until manually cleared | Until tab/browser closes |
| Scope | Same origin | Same tab/window |
| Size | ~5-10MB | ~5-10MB |

---

### 5. Geolocation API

```javascript
if (navigator.geolocation) {
  navigator.geolocation.getCurrentPosition(
    function(position) {
      let lat = position.coords.latitude;
      let lon = position.coords.longitude;
      let accuracy = position.coords.accuracy;
      console.log(`Lat: ${lat}, Lon: ${lon}, Accuracy: ${accuracy}m`);
    },
    function(error) {
      console.log('Error: ' + error.message);
    }
  );
}

// Watch user's position
let watchId = navigator.geolocation.watchPosition(
  function(position) {
    console.log('Updated position:', position.coords);
  }
);

// Stop watching
navigator.geolocation.clearWatch(watchId);
```

---

### 6. Web Workers

**main.js**
```javascript
// Create worker
let worker = new Worker('worker.js');

// Send data to worker
worker.postMessage({ number: 10 });

// Receive data from worker
worker.onmessage = function(event) {
  console.log('Result:', event.data);
};
```

**worker.js**
```javascript
// Receive data
self.onmessage = function(event) {
  let result = event.data.number * 2;
  self.postMessage(result);
};
```

---

### 7. Drag and Drop API

```html
<!DOCTYPE html>
<html>
<head>
<style>
  .dragable { 
    width: 100px; 
    height: 100px; 
    background: blue; 
    cursor: move;
  }
  .dropzone {
    width: 200px;
    height: 200px;
    background: lightgray;
    border: 2px dashed gray;
  }
</style>
</head>
<body>

<div class="dragable" draggable="true" id="drag1">Drag me</div>
<div class="dropzone" id="drop1">Drop here</div>

<script>
  let dragElement = document.getElementById('drag1');
  let dropZone = document.getElementById('drop1');

  dragElement.ondragstart = function(event) {
    event.dataTransfer.setData('text/html', this.innerHTML);
  };

  dropZone.ondragover = function(event) {
    event.preventDefault();
  };

  dropZone.ondrop = function(event) {
    event.preventDefault();
    let data = event.dataTransfer.getData('text/html');
    this.innerHTML = data;
  };
</script>

</body>
</html>
```

---

### 8. Microdata

```html
<div itemscope itemtype="http://schema.org/Person">
  <span itemprop="name">John Doe</span>
  <span itemprop="telephone">(123) 456-7890</span>
  <a href="http://example.com" itemprop="url">Website</a>
</div>
```
- Embeds semantic data
- Used by search engines and other parsers
- Schema.org provides vocabulary

---

## CSS3 Features

### 1. Selectors

#### **Attribute Selectors**
```css
/* Exact match */
input[type="text"] {
  border: 1px solid blue;
}

/* Attribute starts with */
a[href^="https"] {
  color: green;
}

/* Attribute ends with */
a[href$=".pdf"] {
  background: red;
}

/* Attribute contains */
a[href*="example"] {
  color: purple;
}
```

#### **Pseudo-classes**
```css
/* First/Last child */
li:first-child { color: red; }
li:last-child { color: blue; }

/* Nth child */
li:nth-child(2n) { background: lightgray; }
li:nth-child(odd) { background: white; }

/* Interaction */
a:hover { text-decoration: underline; }
a:active { color: red; }
a:visited { color: purple; }

/* Focus states */
input:focus { outline: 2px solid blue; }
```

#### **Pseudo-elements**
```css
/* Before and After */
p::before {
  content: "→ ";
  color: red;
}

p::after {
  content: " ←";
  color: blue;
}

/* Selection */
p::selection {
  background: yellow;
  color: black;
}
```

---

### 2. Flexbox

Flexbox provides one-dimensional layout (row or column).

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 20px;
}

.item {
  flex: 1;
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 100px;
}
```

---

### 3. CSS Grid

Two-dimensional layout with rows and columns.

```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: auto 200px auto;
  gap: 20px;
}

.grid-item {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

---

### 4. Transforms

```css
/* 2D Transforms */
.transform {
  transform: translate(50px, 100px);
  transform: scale(1.5);
  transform: rotate(45deg);
  transform: skew(20deg, 30deg);
}

/* 3D Transforms */
.transform-3d {
  transform: translate3d(50px, 100px, 50px);
  transform: rotateX(45deg);
  transform: perspective(500px);
}
```

---

### 5. Transitions

```css
button {
  background: blue;
  transition: background 0.3s ease;
}

button:hover {
  background: red;
}
```

---

### 6. Animations

```css
@keyframes slideIn {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

.animated {
  animation: slideIn 1s ease-in-out;
  animation-delay: 0.5s;
  animation-iteration-count: infinite;
}
```

---

### 7. Visual Effects

#### **Box Shadows**
```css
.shadow {
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3);
}
```

#### **Gradients**
```css
.gradient-linear {
  background: linear-gradient(to right, red, blue);
}

.gradient-radial {
  background: radial-gradient(circle, red, blue);
}
```

#### **Filters**
```css
.filters {
  filter: blur(5px);
  filter: brightness(150%);
  filter: contrast(200%);
  filter: grayscale(100%);
}
```

---

### 8. Media Queries

```css
/* Mobile first approach */
.container {
  width: 100%;
}

@media (min-width: 768px) {
  .container {
    width: 750px;
  }
}

@media (min-width: 1024px) {
  .container {
    width: 960px;
  }
}
```

---

### 9. CSS Variables

```css
:root {
  --primary-color: #3498db;
  --spacing: 20px;
  --border-radius: 5px;
}

.element {
  background: var(--primary-color);
  padding: var(--spacing);
  border-radius: var(--border-radius);
}
```

---

### 10. Multiple Columns

```css
.multi-column {
  column-count: 3;
  column-width: 200px;
  column-gap: 30px;
  column-rule: 2px solid gray;
}
```

---

### 11. Clip Path

```css
.circle {
  clip-path: circle(50%);
}

.triangle {
  clip-path: polygon(50% 0%, 100% 100%, 0% 100%);
}
```

---

### 12. Text Effects

```css
/* Text overflow */
.truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

/* Text decoration */
.decorated {
  text-decoration: underline;
  text-decoration-color: red;
  text-decoration-style: wavy;
}
```

---

## Best Practices

### HTML5 Best Practices

1. **Use Semantic HTML** - Improves accessibility and SEO
2. **Validation** - Always validate HTML at [W3C Validator](https://validator.w3.org/)
3. **Accessibility (a11y)** - Include alt attributes, proper heading hierarchy
4. **Mobile First** - Design for mobile first, then enhance
5. **Performance** - Minimize HTTP requests, optimize images

### CSS3 Best Practices

1. **Mobile First Approach** - Base styles for mobile, enhance for larger screens
2. **Use CSS Variables** - Makes maintenance easier
3. **Organize Code** - Group related properties, use comments
4. **Performance** - Minimize animations, avoid deeply nested selectors
5. **Browser Compatibility** - Test in multiple browsers, use vendor prefixes
6. **Accessibility** - Ensure color contrast, respect `prefers-reduced-motion`

---

## Resources

- [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3C Standards](https://www.w3.org/)
- [CSS-Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/)

---

This guide covers the essential HTML5 and CSS3 features with practical examples. Experiment with these features to master modern web development!
