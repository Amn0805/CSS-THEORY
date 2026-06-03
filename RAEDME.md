# CSS Theory

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

## Example: Class Reusability vs ID Uniqueness

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

The CSS Box Model consists of **four layers**:

1. Content
2. Padding
3. Border
4. Margin

The Four Layers (from innermost to outermost)
| Layer   | What It Is                                          | Key Properties                         | Description                                                                            |
| ------- | --------------------------------------------------- | -------------------------------------- | -------------------------------------------------------------------------------------- |
| Content | The actual content (text, images, media)            | width, height                          | The innermost area containing the real content like text or images  |
| Padding | Space around the content (inside border)            | padding, padding-top/right/bottom/left | Transparent space that clears an area around the content           |
| Border  | Line around the padding and content                 | border, border-width, border-style     | A border that goes around the padding and content               |
| Margin  | Space outside the border (separates from neighbors) | margin, margin-top/right/bottom/left   | Transparent area that separates the element from other elements   |

### Visual Structure

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

Main Ways to Define Colors in CSS
| Method       | Syntax Example                  | How It Works                                                                                      |
| ------------ | ------------------------------- | -------------------------------------------------------------------------------------------------                                           |
| Named colors | color: red;                       | Uses 147 predefined keywords like red, blue, green,                                    |
| Hexadecimal  | color: #ff4444; or #f44;        | Hex values #RRGGBB (or 3-digit shorthand #RGB), where each pair is 00–FF for red/green/|
| RGB          | color: rgb(255, 68, 68);        | Integer values 0–255 for red, green, blue intensities                                  |
| RGBA         | color: rgba(255, 68, 68, 0.6);  | RGB plus alpha (0–1 or 0%–100%) for transparency                                       |
| HSL          | color: hsl(0, 100%, 63%);       | Hue (0–360°), Saturation (%), Lightness (%) — more intuitive for adjusting colors      |
| HSLA         | color: hsla(0, 100%, 63%, 0.6); | HSL plus alpha channel for transparency                                                |

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
