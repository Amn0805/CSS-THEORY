# CSS Theoretical Question & Answers

## Q1. What is CSS and How Do You Add It to an HTML Page?

### What is CSS?

**CSS** stands for **Cascading Style Sheets**.

CSS is used to control the layout and appearance of HTML elements on a web page. Without CSS, HTML pages would display as plain and unstyled content with no colors, fonts, spacing, or layout control.

### Purpose of CSS

CSS solves the problem of separating **content (HTML)** from **design (styling)**. It allows developers to:

* Control colors, fonts, sizes, and spacing
* Create layouts and responsive designs
* Maintain consistent styling across multiple pages
* Improve website appearance and user experience

---

## Three Ways to Add CSS to an HTML Document 

```text
                           Ways
                             │
      ┌──────────────────────┼──────────────────────┐
      │                      │                      │
      ▼                      ▼                      ▼
 External CSS         Internal CSS           Inline CSS
      │                      │                      │
 styles.css           <style> tag             style=""
```

---

| Method           | Description                                                                 | Example                                     |
| ---------------- | --------------------------------------------------------------------------- | ------------------------------------------- |
| **External CSS** | CSS is written in a separate `.css` file and linked to the HTML document.   | `<link rel="stylesheet" href="styles.css">` |
| **Internal CSS** | CSS is written inside a `<style>` tag within the `<head>` section.          | `<style> h1 { color: blue; } </style>`      |
| **Inline CSS**   | CSS is written directly inside an HTML element using the `style` attribute. | `<p style="color: red;">Text</p>`           |

---

## Code Examples of Each Method

### 1. External CSS

#### index.html

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Hello</h1>
</body>
</html>
```

#### styles.css

```css
h1 {
    color: navy;
}
```

---

### 2. Internal CSS

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        h1 {
            color: blue;
        }
    </style>
</head>
<body>
    <h1>Hello</h1>
</body>
</html>
```

---

### 3. Inline CSS

```html
<!DOCTYPE html>
<html>
<body>
    <h1 style="color: red;">Hello</h1>
</body>
</html>
```

---

## Which Method Is Recommended and Why?

**External CSS** is the recommended method for real-world projects because it keeps styling separate from HTML content, making the code cleaner, easier to manage, and more reusable.

### Why External CSS Is Preferred Over Inline CSS

| Feature               | External CSS                                   | Inline CSS                                 |
| --------------------- | ---------------------------------------------- | ------------------------------------------ |
| **Maintainability**   | One file can update the entire website.        | Every element must be edited individually. |
| **Reusability**       | Same stylesheet can be used on multiple pages. | Styles apply to only one element.          |
| **Code Organization** | Keeps HTML and CSS separate.                   | Mixes styling with HTML content.           |
| **Performance**       | CSS files can be cached by the browser.        | No caching; increases HTML size.           |
| **Best Practice**     | Industry standard for professional projects.   | Suitable only for quick or unique styling. |

---

## Conclusion

External CSS is the best approach because it follows modern web development practices. It improves maintainability, reusability, performance, and keeps the code organized by separating content from presentation.

---
# Q2. Explain CSS Selectors with Examples

## What are CSS Selectors?

CSS selectors are used to target HTML elements and apply styles to them. They help developers select specific elements on a webpage and control how those elements look and behave.

---


## The 7 Selector Types with Examples 
```text
                        CSS Selectors
                               │
        ┌──────────────────────┴──────────────────────┐
        │                                             │
 Basic Selectors                          Relationship Selectors
        │                                             │
 ┌──────┼──────┬──────┬──────┐              ┌─────────┴─────────┐
 │      │      │      │      │              │                   │
 ▼      ▼      ▼      ▼      ▼              ▼                   ▼
Element Class   ID   Group Universal   Descendant          Child
  p    .intro #header h1,h2,p    *       div p           div > p
  ```

---

| Selector Type           | Syntax       | Description                                   | Example                         |
| ----------------------- | ------------ | --------------------------------------------- | ------------------------------- |
| **Element Selector**    | `element`    | Selects all elements of a specific tag name   | `p { color: blue; }`            |
| **Class Selector**      | `.classname` | Selects all elements with the specified class | `.intro { color: red; }`        |
| **ID Selector**         | `#idname`    | Selects the unique element with that ID       | `#header { background: gray; }` |
| **Group Selector**      | `sel1, sel2` | Applies the same styles to multiple selectors | `h1, h2, p { margin: 10px; }`   |
| **Descendant Selector** | `space`      | Selects nested elements at any level          | `div p { color: green; }`       |
| **Child Selector**      | `>`          | Selects only direct child elements            | `div > p { color: orange; }`    |
| **Universal Selector**  | `*`          | Selects all elements on the page              | `* { box-sizing: border-box; }` |

---

## Complete Code Example Using All 7 Selectors

### 1. Element Selector

#### CSS

```css
p {
    color: blue;
    font-size: 16px;
}
```

#### HTML

```html
<p>This is the first paragraph.</p>
<p>This is the second paragraph.</p>
```

**Result:**
All `<p>` elements will have blue text and a font size of 16px.

---

### 2. Class Selector

#### CSS

```css
.intro {
    color: red;
    font-weight: bold;
}
```

#### HTML

```html
<p class="intro">Welcome to my website.</p>
<h2 class="intro">About Us</h2>
```

**Result:**
Both elements with the class `intro` will appear in red and bold text.

---

### 3. ID Selector

#### CSS

```css
#header {
    background-color: gray;
    color: white;
    padding: 20px;
}
```

#### HTML

```html
<div id="header">
    <h1>My Website</h1>
</div>
```

**Result:**
The header section will have a gray background with white text.

---

### 4. Group Selector

#### CSS

```css
h1, h2, h3 {
    text-align: center;
    margin: 10px;
}
```

#### HTML

```html
<h1>Main Heading</h1>
<h2>Sub Heading</h2>
<h3>Small Heading</h3>
```

**Result:**
All headings will be centered with a margin of 10px.

---

### 5. Descendant Selector

#### CSS

```css
div p {
    color: green;
}
```

#### HTML

```html
<div>
    <section>
        <p>This paragraph is inside a div.</p>
    </section>
</div>

<p>This paragraph is outside the div.</p>
```

**Result:**
Only the paragraph inside the `div` will become green.

---

### 6. Child Selector

#### CSS

```css
div > p {
    color: orange;
    font-weight: bold;
}
```

#### HTML

```html
<div>
    <p>Direct child paragraph.</p>

    <section>
        <p>Nested paragraph.</p>
    </section>
</div>
```

**Result:**
Only the first paragraph will become orange and bold because it is a direct child of the `div`.

---

### 7. Universal Selector

#### CSS

```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

#### HTML

```html
<h1>Website Title</h1>
<p>Some paragraph text.</p>
<button>Click Me</button>
```

**Result:**
All elements will have zero margin and padding, and use `border-box` sizing.

---

## Class vs ID

| Class                            | ID                           |
| -------------------------------- | ---------------------------- |
| Can be used on multiple elements | Should be unique on the page |
| Uses `.` symbol                  | Uses `#` symbol              |
| Lower specificity                | Higher specificity           |
| Best for reusable styles         | Best for unique elements     |

---

## Key Differences

| Question                                                | Answer                                                              |
| ------------------------------------------------------- | ------------------------------------------------------------------- |
| **Which selector has higher specificity?**              | The **ID selector** has higher specificity than the class selector. |
| **Can you use the same class on multiple elements?**    | Yes. Classes are reusable and can be applied to many elements.      |
| **Can you use the same ID on multiple elements?**       | No. Each ID should be unique within a webpage.                      |
| **How do you target a direct child vs any descendant?** | Use `>` for a direct child and a space (` `) for any descendant.    |

---

## Example:

### HTML

```html
<!-- Class used on multiple elements -->
<p class="intro">First Paragraph</p>
<p class="intro">Second Paragraph</p>

<!-- Unique ID -->
<div id="header">Website Header</div>

<!-- Incorrect Usage: Duplicate IDs -->
<div id="header">Header 1</div>
<div id="header">Header 2</div> <!-- Invalid -->
```

## Conclusion

CSS selectors are essential for targeting HTML elements and applying styles efficiently. Understanding element, class, ID, group, descendant, child, and universal selectors helps developers write cleaner, more maintainable, and reusable CSS code.

---

# Q3. What is the CSS Box Model? Explain Each Layer

## What is the CSS Box Model?

The **CSS Box Model** is a fundamental concept that treats every HTML element as a rectangular box with four layers. 
It defines how elements are sized, spaced, and laid out on a web page.

## Layers of the CSS Box Model

The CSS Box Model consists of **four layers**

```text
+-------------------------+
|         Margin          |
|  +-------------------+  |
|  |      Border       |  |
|  |  +-------------+  |  |
|  |  |   Padding   |  |  |
|  |  | +---------+ |  |  |
|  |  | | Content | |  |  |
|  |  | +---------+ |  |  |
|  |  +-------------+  |  |
|  +-------------------+  |
+-------------------------+
```

---

1. Content
2. Padding
3. Border
4. Margin

## The Four Layers of CSS Box Model (From Innermost to Outermost)

| Layer   | What It Is | Key Properties | Description |
|----------|------------|----------------|-------------|
| **Content** | The actual content (text, images, media) | `width`, `height` | The innermost area that contains real content like text, images, or videos. |
| **Padding** | Space around the content (inside border) | `padding`, `padding-top/right/bottom/left` | Transparent space that creates distance between content and border. |
| **Border** | Line around the padding and content | `border`, `border-width`, `border-style` | A visible line that wraps around padding and content. |
| **Margin** | Space outside the border (separates elements) | `margin`, `margin-top/right/bottom/left` | Transparent space that separates one element from another. |


## Examples: 

### 1. Content
#### CSS

```css
.box {
    width: 300px;
    height: 150px;
}
```

#### HTML

```html
<div class="box">
    This is the content area.
</div>
```

**Explanation:**
The width and height properties define the size of the content area.

---

### 2. Padding

#### CSS

```css
.box {
    padding: 20px;
}
```

#### HTML

```html
<div class="box">
    Content with padding
</div>
```

**Explanation:**
The content will have 20px of space between itself and the border.

---

### 3. Border

#### CSS

```css
.box {
    border: 3px solid black;
}
```

#### HTML

```html
<div class="box">
    Content with border
</div>
```

**Explanation:**
A black border with a thickness of 3px will surround the element.

---

### 4. Margin

#### CSS

```css
.box {
    margin: 30px;
}
```

#### HTML

```html
<div class="box">
    Content with margin
</div>
```

**Explanation:**
There will be 30px of space outside the element, separating it from nearby elements.

---

## Complete Example of the Box Model

### CSS

```css
.box {
  width: 200px;           /* Content width */
  padding: 20px;          /* Space inside, around content */
  border: 5px solid black; /* Border around padding */
  margin: 30px;           /* Space outside, separates from other elements */
  background-color: lightblue; /* Applies to content + padding + border */
}
```

### HTML

```html
<div class="box">
    This box demonstrates all layers of the CSS Box Model.
</div>
```

## How Total Size is Calculated

By default, the total size of an element is calculated as:

```text
Total Width =
Width + Left Padding + Right Padding +
Left Border + Right Border

Total Height =
Height + Top Padding + Bottom Padding +
Top Border + Bottom Border
```

### Example

```css
.box {
    width: 200px;
    padding: 20px;
    border: 5px solid black;
}
```

**Total Width =**

```text
200 + 20 + 20 + 5 + 5 = 250px
```

---


## Conclusion

The CSS Box Model is the foundation of web page layout. Every HTML element consists of **content, padding, border, and margin**. Understanding these layers helps developers control spacing, sizing, and positioning of elements effectively.

---

# Q4. Explain CSS Colors. What Are the Different Ways to Define a Color?

## What are CSS Colors?

CSS colors are used to change the appearance of elements on a web page. They can be applied to text, backgrounds, borders, shadows, and many other properties.

---

## Why Are CSS Colors Important?

CSS colors help developers:

* Make websites visually attractive
* Highlight important content
* Improve readability
* Create consistent branding
* Enhance user experience

---
## Main Ways to Define Colors in CSS

```text
                              Ways
                                │
        ┌───────────────┬────────┬────────┬───────────────┐
        │               │        │        │               │
        ▼               ▼        ▼        ▼               ▼
   Named Colors     HEX Colors   RGB     RGBA           HSL/HSLA
```

---

| Method | Syntax Example | How It Works |
|---------|---------------|-------------|
| **Named Colors** | `color: red;` | Uses predefined color names such as `red`, `blue`, `green`, and many others. |
| **Hexadecimal (HEX)** | `color: #ff4444;` <br> `color: #f44;` | Uses hexadecimal values in the format `#RRGGBB` or the shorthand `#RGB`, where each pair controls the intensity of red, green, and blue. |
| **RGB** | `color: rgb(255, 68, 68);` | Uses numeric values from `0–255` to define the intensity of red, green, and blue colors. |
| **RGBA** | `color: rgba(255, 68, 68, 0.6);` | Similar to RGB, but includes an alpha value (`0–1`) to control transparency. |
| **HSL** | `color: hsl(0, 100%, 63%);` | Uses Hue (`0–360°`), Saturation (`%`), and Lightness (`%`) to define colors in a more human-friendly way. |
| **HSLA** | `color: hsla(0, 100%, 63%, 0.6);` | Similar to HSL, but includes an alpha value to add transparency. |                                          |

## Examples: 

### 1. Color Names

#### CSS

```css
h1 {
    color: blue;
}

p {
    color: red;
}
```

#### HTML

```html
<h1>Welcome</h1>
<p>This is a paragraph.</p>
```

**Result:**
The heading appears blue and the paragraph appears red.

---

### 2. HEX Colors

#### CSS

```css
h1 {
    color: #0000FF;
}

p {
    color: #FF0000;
}
```

#### HTML

```html
<h1>Welcome</h1>
<p>This is a paragraph.</p>
```

**Explanation:**

* `#0000FF` = Blue
* `#FF0000` = Red

---

### 3. RGB Colors

#### CSS

```css
h1 {
    color: rgb(0, 0, 255);
}

p {
    color: rgb(255, 0, 0);
}
```

#### HTML

```html
<h1>Welcome</h1>
<p>This is a paragraph.</p>
```

**Explanation:**

* `rgb(255, 0, 0)` = Red
* `rgb(0, 255, 0)` = Green
* `rgb(0, 0, 255)` = Blue

---

### 4. RGBA Colors

#### CSS

```css
.box {
    background-color: rgba(0, 0, 255, 0.5);
}
```

#### HTML

```html
<div class="box">
    Semi-transparent blue background
</div>
```

**Result:**
The background appears blue with 50% transparency.

---

### 5. HSL Colors

#### CSS

```css
h1 {
    color: hsl(240, 100%, 50%);
}
```

#### HTML

```html
<h1>Welcome</h1>
```

**Explanation:**

* Hue = 240 (Blue)
* Saturation = 100%
* Lightness = 50%

---

### 6. HSLA Colors

#### CSS

```css
.box {
    background-color: hsla(240, 100%, 50%, 0.5);
}
```

#### HTML

```html
<div class="box">
    Transparent Blue Box
</div>
```

**Result:**
The box has a semi-transparent blue background.

---

## Applying Colors to Different Properties

### Text Color

```css
p {
    color: green;
}
```

### Background Color

```css
div {
    background-color: lightblue;
}
```

### Border Color

```css
button {
    border: 2px solid red;
}
```

---

## Complete Example

### CSS

```css
body {
    background-color: #f4f4f4;
}

h1 {
    color: blue;
}

p {
    color: rgb(255, 0, 0);
}

.box {
    background-color: rgba(0, 128, 255, 0.5);
    border: 2px solid black;
    padding: 20px;
}
```

### HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Colors Example</title>
</head>
<body>

    <h1>CSS Colors</h1>

    <p>This paragraph uses RGB color.</p>

    <div class="box">
        This box uses RGBA color.
    </div>

</body>
</html>
```

---

## Conclusion

CSS colors allow developers to style text, backgrounds, borders, and other elements. Colors can be defined using color names, HEX values, RGB, RGBA, HSL, and HSLA formats. Choosing the right color format helps create attractive, readable, and professional web designs.

 # Q5. What are CSS Units? Explain px, %, rem, em, vh, and vw.

## What are CSS Units?

CSS units are used to define the size of elements, text, spacing, margins, padding, widths, heights, and other measurements on a webpage.

---

## Why Are CSS Units Important?

CSS units help developers:

* Set element dimensions
* Control font sizes
* Create responsive layouts
* Maintain consistency across devices
* Improve user experience

---

## CSS Units Categories

They fall into two categories:

```text
                     Categories
                         │
        ┌────────────────┴────────────────┐
        │                                 │
 Absolute Units                    Relative Units
        │                                 │
      px                         %, em, rem,
                                 vh, vw
```

---

**Absolute Units:** The absolute length units are fixed and a length expressed in any of these will appear as exactly that size.

**Relative Units:** Flexible units that adjust according to the parent element, root element, or viewport size, making them useful for responsive web design.

## Here's a simple explanation of each unit:

| Unit                 | What it means                | Simple explanation                                                                                                          |
| -------------------- | ---------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **px (pixels)**        | Fixed size                   | 1 px = 1 tiny dot on your screen. 20px always means 20 dots, no matter what    |
| **% (percent)**          | Relative to parent           | 50% means "half the size of the parent box." If parent is 200px wide, 50% = 100px |
| **rem**                  | Relative to root font-size   | 1rem = the font size of the <html> tag (usually 16px). So 2rem = 32px. Same everywhere on the page  |
| **em**                  | Relative to parent font-size | 1em = the font size of the parent element. If parent font is 18px, 2em = 36px. |
| **vh (viewport height)** | Relative to screen height    | 1vh = 1% of your browser window height. 100vh = full screen height |
| **vw (viewport width)**  | Relative to screen width     | 1vw = 1% of your browser window width. 50vw = half the screen width  |

## When to use each:

- **px:** Fixed-size elements such as borders, icons, and precise layouts.
- **%:** Widths and margins that should scale with parent containers.
- **rem:** Font sizes and spacing (recommended for consistency and accessibility).
- **em:** Components that should scale based on the parent element.
- **vh/vw:** Full-screen sections and responsive layouts tied to viewport size.

## Examples: 

### 1. px (Pixels)

#### CSS

```css
h1 {
    font-size: 32px;
}
```

#### HTML

```html
<h1>Welcome</h1>
```

**Explanation:**
The heading will always have a font size of 32 pixels regardless of its parent element.
---

### 2. % (Percentage)

#### CSS

```css
.container {
    width: 80%;
}
```

#### HTML

```html
<div class="container">
    Content
</div>
```

**Explanation:**
The container will occupy 80% of its parent element's width.

---

### 3. em

#### CSS

```css
.parent {
    font-size: 20px;
}

.child {
    font-size: 2em;
}
```

#### HTML

```html
<div class="parent">
    <p class="child">Hello World</p>
</div>
```

**Explanation:**
The parent font size is 20px.

```text
2em = 2 × 20px = 40px
```

The child text will be 40px.

---

### 4. rem

#### CSS

```css
html {
    font-size: 16px;
}

h1 {
    font-size: 2rem;
}
```

#### HTML

```html
<h1>Welcome</h1>
```

**Explanation:**

```text
2rem = 2 × 16px = 32px
```

The heading size becomes 32px.

---

### 5. vh (Viewport Height)

#### CSS

```css
.hero {
    height: 100vh;
}
```

#### HTML

```html
<div class="hero">
    Full Screen Section
</div>
```

**Explanation:**
The element will occupy 100% of the browser's visible height.

---

### 6. vw (Viewport Width)

#### CSS

```css
.banner {
    width: 100vw;
}
```

#### HTML

```html
<div class="banner">
    Full Width Banner
</div>
```

**Explanation:**
The banner will occupy 100% of the browser's width.

---

# Complete Example

### CSS

```css
html {
    font-size: 16px;
}

.container {
    width: 80%;
    padding: 20px;
}

h1 {
    font-size: 2rem;
}

p {
    font-size: 1.2em;
}

.hero {
    height: 100vh;
    width: 100vw;
    background-color: lightblue;
}
```

### HTML

```html
<div class="hero">
    <div class="container">
        <h1>CSS Units Example</h1>
        <p>This paragraph demonstrates different CSS units.</p>
    </div>
</div>
```

---

# Conclusion
CSS units determine the size and spacing of elements on a webpage.

- **px** provides fixed sizing.
- **%** creates flexible layouts based on parent elements.
- **em** scales relative to the parent font size.
- **rem** scales relative to the root font size.
- **vh** and **vw** scale relative to the viewport size.

Understanding these units helps developers create responsive and user-friendly web designs that work well on different screen sizes and devices.

---

# Q6. What is CSS Specificity and How Does the Cascade Work?

When we write multiple CSS rules that target the same element, the browser needs to decide which style to apply.  
CSS uses two important concepts to make this decision:

```text
                     Concepts
                         │
        ┌────────────────┴────────────────┐
        │                                 │
     Cascade                         Specificity
```

---

**Cascade:** Determines which rule wins based on source and order.

**Specificity:** Determines which selector is more important.

---

## What is the CSS Cascade?

The Cascade is the algorithm CSS uses to figure out which style wins when multiple rules could apply to the same element. The name "Cascading Style Sheets" comes from this concept.

### Important Factors:

The Cascade considers 3 main factors (in order of priority):

```text
                          Factors
                             │
      ┌──────────────────────┼──────────────────────┐
      │                      │                      │
      ▼                      ▼                      ▼
 Importance            Specificity           Source Order
 & Origin 
```

---

1. Origin & Importance (!important)  
2. Specificity  
3. Source order (the rule written last wins)

---

| Factor                 | What it means                                                                                        |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| 1. Origin & Importance | Where the CSS comes from (browser default, user, or your stylesheet) and whether !important is used  |
| 2. Specificity         | How "specific" or targeted the selector is (ID vs class vs element)                                  |
| 3. Source Order        | If everything else is equal, the rule that appears last in the CSS file wins                         |

---

## 1. Origin & Importance :

What is "Origin" in CSS?

Origin = Where your CSS comes from (who wrote it).

### Types:

There are 3 types of origin:

```text
                          Types
                             │
      ┌──────────────────────┼──────────────────────┐
      │                      │                      │
      ▼                      ▼                      ▼
 Browser default          Author                    User
```

---

1. Browser default.  
2. Author.  
3. User.  

---

| Origin          | Who writes it       | Example                                     |
| --------------- | ------------------- | ------------------------------------------- |
| Browser default | The browser itself  | Every browser gives <p> some default margin |
| Author (you)    | You (the developer) | Your CSS file: p { color: red; }            |
| User            | The website visitor | User's custom browser settings              |

---

Priority:

```text
Your CSS (Author) → Wins over Browser defaults
```

---

Example:

```CSS
/* Browser default (low priority) */
p { margin: 1em; }

/* Your CSS (higher priority) */
p { margin: 0; }  /* This wins! */
```

Result: Paragraph has no margin because your CSS overrides the browser's default.

---

### What is Important?

!important = A special flag you can add to make that style always win, no matter what.

Without !important:

```CSS
p { color: red; }
#header p { color: blue; }  /* This wins because it's more specific */
```

---

With !important:

```CSS
p { color: red !important; }
#header p { color: blue; }  /* This loses! */
```

---

Result: Text is red because !important overrides normal specificity.

---

### Origin & Importance (Highest Priority)

| Priority | Origin                                              |
| -------- | --------------------------------------------------- |
| 1️⃣      | User !important styles                              |
| 2️⃣      | Author !important styles (your CSS with !important) |
| 3️⃣      | Author normal styles (your regular CSS)             |
| 4️⃣      | User normal styles                                  |
| 5️⃣      | Browser default styles (lowest)                     |

---

### Why You Should Avoid !important

| Problem          | Explanation                                             |
| ---------------- | ------------------------------------------------------- |
| Hard to debug    | You can't override it without another !important       |
| Breaks CSS logic | Normal specificity rules don't work anymore            |
| Makes code messy | Other developers can't predict what will happen        |

---

## 2. Specificity:

Specificity is like a scoring system that browsers use to decide which style rule wins when multiple rules target the same element.  

Impotance:  
Each selector gets a score in the format: (a, b, c, d)

| Value | What it counts                      | Example                       | Points       |
| ----- | ----------------------------------- | ----------------------------- | ------------ |
| a     | Inline styles                       | style="color: red"           | (1, 0, 0, 0) |
| b     | ID selectors                        | #header                       | (0, 1, 0, 0) |
| c     | Classes, attributes, pseudo-classes | .class, [type="text"], :hover | (0, 0, 1, 0) |
| d     | Element tags, pseudo-elements       | div, p, ::before              | (0, 0, 0, 1) |

Higher score from left to right wins.

---

Hierarchy of selector strength (lowest to highest):

```text
Element (div) < Class (.class) < ID (#id) < Inline style < !important
```

---

### Examples:

---

### 1. Element vs Class:

#### HTML

```html
<p class="text">Hello</p>
```

---

#### CSS

```CSS
p {
  color: blue;
}

.text {
  color: green;
}
```

---

Result:  
The text will be green.  
Why?  
A class selector has higher specificity than an element selector.

---

### 2. Class Vs ID :

#### HTML

```html
<p id="message" class="text">
  Hello
</p>
```

---

#### CSS

```CSS
.text {
  color: green;
}

#message {
  color: red;
}
```

---

Result:  
The text will be red.  
Why?  
ID selectors have higher specificity than class selectors.

---

### 3. Inline CSS:

#### HTML

```html
<p id="message" style="color: purple;">
  Hello
</p>
```

#### CSS

```CSS
#message {
  color: red;
}
```

---

Result:  
The text will be purple.  
Why?  
Inline CSS has higher priority than ID selectors.

---

## 3. Source Order(If Everything Else is Equal):

If specificity is the same, the rule that appears last wins.  
This includes:  
      External CSS vs Internal CSS: Both have equal specificity. The one loaded last in the HTML file wins.

```html
<head>
 <link rel="stylesheet" href="style.css">   <!-- External -->
 <style>
   p { color: blue; }                       <!-- Internal -->
 </style>
</head>
```

---

```CSS
/* style.css */
p { color: red; }
```

Result: Text is blue because Internal CSS is loaded last.

---

Same CSS file: The rule written later overrides the earlier one.

```CSS
p { color: red; }    /* First — ignored */
p { color: blue; }   /* Last — WINS */
```

---

Inheritance (Third Factor):  
Some properties (like font-family, color) automatically pass from parent to child. Others (like border, padding) do not inherit.

---

## Conclusion:

When conflicting styles exist, the browser decides in this order:

```Text
1. Check Origin & Importance
   ├─ !important styles win over normal styles
   └─ Author styles win over user/browser defaults

2. Check Specificity (if origin is same)
   ├─ Inline style (1,0,0,0) wins
   ├─ ID selector (0,1,0,0) wins
   ├─ Class (0,0,1,0) wins
   └─ Element (0,0,0,1) wins

3. Check Source Order (if specificity is tied)
   ├─ CSS loaded last in HTML wins
   ├─ Internal vs External: same specificity, order matters
   └─ Later rule in same file wins over earlier rule

4. Check Inheritance (if no direct style)
   └─ Inherited properties from parent apply
```

# Explain CSS Flexbox. How does it differ from Block Layout?

**Flexbox** (Flexible Box Layout) is a CSS layout model that makes it easier to arrange, align, and distribute elements inside a container. It is designed to create responsive layouts without using complex positioning techniques or floats.

Before Flexbox, developers mainly relied on the traditional **block layout**, which often required additional CSS rules to achieve complex layouts. Flexbox simplifies this process by providing powerful alignment and spacing features.

---

## What is Flexbox?

CSS Flexbox (Flexible Box Layout) is a one-dimensional layout model that arranges items in a row or column, making it easy to create responsive and dynamic layouts without using floats or positioning.

---

## How Flexbox Works

A flexbox layout always has two parts:

```text
                       Parts
                         │
        ┌────────────────┴────────────────┐
        │                                 │
 Flex-Container                       Flex-Items
```

---

| Part | What it is | How to create it |
|--------|------------|------------------|
| Flex Container | The parent element | `display: flex;` on the parent |
| Flex Items | Direct children of the container | Automatically become flex items |

---

## Basic Example

### HTML

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

### CSS

```css
.container {
  display: flex;  /* Turns container into flex container */
}
```

Now all `.item` divs are flex items and will be arranged in a row by default.

---

# Key Concept: Main Axis and Cross Axis

Understanding these two axes is the foundation of Flexbox — you cannot master Flexbox without them.

## The Two Axis

```text
                       Axis
                         │
        ┌────────────────┴────────────────┐
        │                                 │
    Main-Axis                            Cross-Axis
```

---

| Axis | What it does | Controlled by |
|--------|-------------|---------------|
| Main Axis | Where items are placed (direction of flow) | `flex-direction` |
| Cross Axis | Perpendicular to main axis (alignment across) | Automatically perpendicular to main axis |

---

The axes change when you change `flex-direction`:

```text
When flex-direction: row (default):
├─ Main axis: Horizontal (left → right)
└─ Cross axis: Vertical (top → bottom)

When flex-direction: column:
├─ Main axis: Vertical (top → bottom)
└─ Cross axis: Horizontal (left → right)
```

---

# Key Flexbox Properties

## Properties on the Container (Parent)

```text
                              Properties(Container)
                                │
        ┌───────────────┬───────────────┬───────────────┬───────────────┐
        │               │               │               │               │
        ▼               ▼               ▼               ▼               ▼
   flex-direction  justify-content   align-items     flex-wrap         gap
```

---

| Property | What it does | Common values |
|-----------|-------------|--------------|
| flex-direction | Sets the main axis direction | `row`, `row-reverse`, `column`, `column-reverse` |
| justify-content | Aligns items along the main axis | `flex-start`, `center`, `space-between`, `space-around`, `flex-end` |
| align-items | Aligns items across the cross axis | `stretch`, `center`, `flex-start`, `flex-end`, `baseline` |
| flex-wrap | Whether items wrap to new lines | `nowrap`, `wrap`, `wrap-reverse` |
| gap | Space between items | `10px`, `20px`, etc. |

---

# Code Examples

## 1. flex-direction

### HTML

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  flex-direction: column;
}
```

### Output

```text
1
2
3
```

---

## 2. justify-content

### HTML

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

### Output

```text
[1]           [2]           [3]
```

---

## 3. align-items

### HTML

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  align-items: center;
}
```

---

## 4. flex-wrap

### HTML

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

### Output

```text
[1][2][3]
[4][5][6]
```

---

## 5. gap

### HTML

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  gap: 20px;
}
```

---

# Properties on the Items (Children)

```text
                    Properties(Children)
                             │
      ┌──────────────────────┼──────────────────────┐
      │                      │                      │
      ▼                      ▼                      ▼
    flex                   order                align-self
```

---

| Property | What it does |
|-----------|-------------|
| flex | Shorthand for `flex-grow`, `flex-shrink`, `flex-basis` |
| order | Reorders items without changing HTML |
| align-self | Overrides container's `align-items` for one item |

---

# Code Examples

## 1. flex

### HTML

```html
<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
</div>
```

### CSS

```css
.container {
  display: flex;
}

.item1 {
  flex-grow: 2;
}

.item2 {
  flex-grow: 1;
}
```

### Output

The first box gets twice as much available space as the second.

---

## 2. order

### HTML

```html
<div class="container">
  <div class="box box1">Box 1</div>
  <div class="box box2">Box 2</div>
  <div class="box box3">Box 3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  gap: 10px;
}

.box {
  padding: 20px;
  border: 1px solid black;
}

.box1 {
  order: 2;
}

.box2 {
  order: 1;
}

.box3 {
  order: 3;
}
```

### Output

```text
Box 2   Box 1   Box 3
```

---

## 3. align-self

### HTML

```html
<div class="container">
  <div class="box">Box 1</div>
  <div class="box special">Box 2</div>
  <div class="box">Box 3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
  height: 200px;
  border: 2px solid black;
  align-items: flex-start;
}

.box {
  padding: 20px;
  border: 1px solid blue;
}

.special {
  align-self: flex-end;
}
```

### Output

```text
Box 1    Box 3
            Box 2
```

---

# Flexbox vs Block Layout — Key Differences

| Feature | Block Layout | Flexbox |
|----------|-------------|----------|
| Direction | Stacks vertically (top to bottom) | Row or column (flexible) |
| Starts on new line | Yes — always creates line break | No — items sit side by side |
| Width | Takes full width of parent | Takes only needed width (unless set) |
| Height/Width | Respected | Respected |
| Alignment | Limited (text-align for horizontal only) | Full control via main & cross axis |
| Spacing | Margins only | gap property + flexible spacing |
| Responsive | Limited capabilities | Extensive — adapts smoothly to screen sizes |
| Reordering | Must change HTML | Use order property |
| Space distribution | Manual with margins | Automatic with flex-grow, flex-shrink |

---

# Visual Differences

## Block Layout (Default)

### HTML

```html
<div>Item 1</div>
<div>Item 2</div>
<div>Item 3</div>
```

Result: Each item takes full width and stacks vertically.

```text
┌─────────────────┐
│    Item 1       │
└─────────────────┘
┌─────────────────┐
│    Item 2       │
└─────────────────┘
┌─────────────────┐
│    Item 3       │
└─────────────────┘
```

---

## Flexbox Layout

### HTML

```html
<div class="container">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

### CSS

```css
.container {
  display: flex;
}
```

Result: Items sit side by side in a row.

```text
┌───────────────────────────────────────┐
│ Item 1  │  Item 2  │  Item 3          │
└───────────────────────────────────────┘
```

---

# Benefits of Flexbox

| Benefit | Explanation |
|----------|------------|
| Responsive Design | Creates layouts that adapt to any screen size |
| Easy Alignment | Effortless horizontal and vertical alignment via axes |
| Dynamic Sizing | Items automatically adjust size based on available space |
| Reordering | Change visual order without changing HTML structure |
| No Floats/Positioning | Modern approach without old hacks |
| Space Distribution | Automatically distributes space between items |

---

# Conclusion

| Aspect | Block Layout | Flexbox |
|---------|-------------|----------|
| Purpose | Document flow (vertical stacking) | Layout control (row/column) |
| Dimension | Two-dimensional (natural flow) | One-dimensional (row or column) |
| Best for | Text content, paragraphs | Components, navigation, cards, responsive layouts |
| Alignment | Limited | Full control via main & cross axis |