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
