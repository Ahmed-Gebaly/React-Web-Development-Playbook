# HTML (HyperText Markup Language) Notes

HTML is the **standard markup language** for creating web pages.  
> **Note:** HTML is *not* a programming language.

---

## 📄 Basic Structure of an HTML Document

```html
<!-- Declaration specifies HTML5 -->
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
  </head>
  <body>
    <!-- Visible content goes here -->
  </body>
</html>
```

---

## 🌳 DOM (Document Object Model)

- Represents the HTML document as a **tree-like structure**.
- Each HTML element is a **node** in the tree.
- Allows programming languages (like JavaScript) to interact with and modify the page.

![alt text](image.png)

---

## 🏷️ HTML Tag Types

- **Closed Tags**: Have both opening and closing tags  
  Example: `<p> ... </p>`
  - *Semantic Tags*: e.g., `<header>`, `<footer>`, `<nav>`, `<article>`, `<section>`
  - *Fragment Tags*: `<div>` and `<span>` (used for grouping and styling)
    - **`<div>`**: A block-level container used to group other elements for styling (with CSS) or scripting (with JavaScript). It has no semantic meaning by itself.
      - Example:
        ```html
        <div class="container">
          <p>This is inside a div.</p>
        </div>
        ```
    - **`<span>`**: An inline container for text, used for styling or scripting small parts of content.

- **Empty (Self-closing) Tags**: Do not have closing tags  
  Example: `<img />`, `<br />`, `<hr />`

---

## 🗂️ Semantic HTML Elements

Semantic elements clearly describe their meaning in a human- and machine-readable way.  
They help with SEO and accessibility.

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Element</th>
    <th>Description</th>
    <th>Example Usage</th>
  </tr>
  <tr>
    <td>&lt;header&gt;</td>
    <td>Introductory content or navigation links</td>
    <td>&lt;header&gt;&lt;h1&gt;Site Title&lt;/h1&gt;&lt;/header&gt;</td>
  </tr>
  <tr>
    <td>&lt;nav&gt;</td>
    <td>Navigation bar/links</td>
    <td>&lt;nav&gt;&lt;a href="/"&gt;Home&lt;/a&gt;&lt;/nav&gt;</td>
  </tr>
  <tr>
    <td>&lt;main&gt;</td>
    <td>Main content of the document</td>
    <td>&lt;main&gt;&lt;h2&gt;Article&lt;/h2&gt;&lt;p&gt;...&lt;/p&gt;&lt;/main&gt;</td>
  </tr>
  <tr>
    <td>&lt;section&gt;</td>
    <td>Thematic grouping of content</td>
    <td>&lt;section&gt;&lt;h2&gt;News&lt;/h2&gt;&lt;p&gt;...&lt;/p&gt;&lt;/section&gt;</td>
  </tr>
  <tr>
    <td>&lt;article&gt;</td>
    <td>Self-contained, independent content</td>
    <td>&lt;article&gt;&lt;h2&gt;Post&lt;/h2&gt;&lt;p&gt;...&lt;/p&gt;&lt;/article&gt;</td>
  </tr>
  <tr>
    <td>&lt;aside&gt;</td>
    <td>Content aside from the main content</td>
    <td>&lt;aside&gt;Sidebar info&lt;/aside&gt;</td>
  </tr>
  <tr>
    <td>&lt;footer&gt;</td>
    <td>Footer for a section or page</td>
    <td>&lt;footer&gt;Copyright 2024&lt;/footer&gt;</td>
  </tr>
  <tr>
    <td>&lt;figure&gt;</td>
    <td>Self-contained content, like images</td>
    <td>&lt;figure&gt;&lt;img src="..." alt=""&gt;&lt;figcaption&gt;Caption&lt;/figcaption&gt;&lt;/figure&gt;</td>
  </tr>
  <tr>
    <td>&lt;figcaption&gt;</td>
    <td>Caption for a &lt;figure&gt;</td>
    <td>&lt;figcaption&gt;Caption&lt;/figcaption&gt;</td>
  </tr>
  <tr>
    <td>&lt;address&gt;</td>
    <td>Contact information</td>
    <td>&lt;address&gt;123 Main St, City&lt;/address&gt;</td>
  </tr>
  <tr>
    <td>&lt;time&gt;</td>
    <td>Date/time value</td>
    <td>&lt;time datetime="2024-06-01"&gt;June 1, 2024&lt;/time&gt;</td>
  </tr>
</table>

---

## Difference Between `<div>` and `<section>`

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th></th>
    <th>&lt;div&gt;</th>
    <th>&lt;section&gt;</th>
  </tr>
  <tr>
    <td>Description</td>
    <td>Generic block-level container for grouping</td>
    <td>Thematic grouping of related content</td>
  </tr>
  <tr>
    <td>Semantic</td>
    <td>No</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Typical Usage</td>
    <td>Layout, styling, scripting</td>
    <td>Logical, meaningful page sections (with heading)</td>
  </tr>
  <tr>
    <td>Accessibility</td>
    <td>No semantic meaning for assistive tech</td>
    <td>Recognized as a document section</td>
  </tr>
  <tr>
    <td>SEO</td>
    <td>No impact</td>
    <td>Improves structure and SEO</td>
  </tr>
  <tr>
    <td>Example</td>
    <td>&lt;div class="box"&gt;...&lt;/div&gt;</td>
    <td>&lt;section&gt;&lt;h2&gt;Title&lt;/h2&gt;...&lt;/section&gt;</td>
  </tr>
</table>

**Notes:**
- Use `<section>` for meaningful, standalone sections of content, typically with a heading (e.g., `<h2>`).
- Use `<div>` for generic grouping when no semantic meaning is needed, such as for CSS layout or JavaScript hooks.

---

## 🧱 HTML Elements

- Elements are the building blocks of web pages.

---

## 🧩 Element Architecture

```html
<p class="text" id="intro">Hello World</p>
```

- **Element**: Everything together (`<p class="text" id="intro">Hello World</p>`)
- **Tag name**: `p`
- **Opening tag**: `<p class="text" id="intro">`
- **Attributes**: `class`, `id`
- **Attribute values**: `"text"`, `"intro"`  
- **Content**: `Hello World`
- **Closing tag**: `</p>`

General syntax:
```html
<tag attribute="value">Content</tag>
```

---

## 🏷️ HTML Attributes

HTML attributes provide additional information about HTML elements.  
**Types of attributes:**
- **Global attributes:** Can be used on any HTML element (e.g., `id`, `class`, `style`, `title`)
- **Element-specific attributes:** Only valid for certain elements (e.g., `href` for `<a>`, `src` for `<img>`, `alt` for `<img>`, `type` for `<input>`)

Attributes are always written in the opening tag, as `name="value"` pairs.

**Example:**
```html
<a href="https://www.example.com" target="_blank" title="Go to Example">Visit Example.com</a>
```

---

## 🏷️ Common HTML Attributes

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Attribute</th>
    <th>Most Used With</th>
    <th>Description / What It Does</th>
  </tr>
  <tr>
    <td>id</td>
    <td>All elements (commonly: div, p, h1-h6, span, a, input)</td>
    <td>Unique identifier for an element; used for CSS, JS, or anchor links.</td>
  </tr>
  <tr>
    <td>class</td>
    <td>All elements (commonly: div, span, p, a, li, input)</td>
    <td>Assigns one or more class names for styling or scripting groups of elements.</td>
  </tr>
  <tr>
    <td>style</td>
    <td>All elements</td>
    <td>Applies inline CSS styles directly to the element.</td>
  </tr>
  <tr>
    <td>title</td>
    <td>All elements (commonly: a, abbr, img, button)</td>
    <td>Shows a tooltip with extra info on mouse hover.</td>
  </tr>
  <tr>
    <td>href</td>
    <td>a, link, area, base</td>
    <td>Specifies the URL or destination for a link.</td>
  </tr>
  <tr>
    <td>src</td>
    <td>img, script, iframe, audio, video, source</td>
    <td>Specifies the file/resource to load (image, media, etc.).</td>
  </tr>
  <tr>
    <td>alt</td>
    <td>img, area, input</td>
    <td>Alternative text for images; shown if image can't load and for accessibility.</td>
  </tr>
  <tr>
    <td>target</td>
    <td>a, form, base</td>
    <td>Where to open the linked document (e.g., new tab).</td>
  </tr>
  <tr>
    <td>disabled</td>
    <td>input, button, select, textarea, option, fieldset</td>
    <td>Disables the element; user cannot interact with it.</td>
  </tr>
  <tr>
    <td>checked</td>
    <td>input (type="checkbox" or "radio")</td>
    <td>Sets checkbox/radio as selected by default.</td>
  </tr>
  <tr>
    <td>readonly</td>
    <td>input, textarea</td>
    <td>Makes the field read-only; user cannot change value.</td>
  </tr>
  <tr>
    <td>placeholder</td>
    <td>input, textarea</td>
    <td>Shows a short hint inside the field before input.</td>
  </tr>
  <tr>
    <td>value</td>
    <td>input, option, button, textarea</td>
    <td>Initial value or label of the element.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>input, select, textarea, form, button</td>
    <td>Name for form data submission/reference.</td>
  </tr>
  <tr>
    <td>type</td>
    <td>input, button</td>
    <td>Defines the input/button type (text, password, submit, etc.).</td>
  </tr>
</table>

---

## 🏷️ Common HTML Head Elements

Below is a table of the most common elements used inside the `<head>` section of an HTML document:

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Element</th>
    <th>Description</th>
    <th>Tag Type</th>
    <th>Example</th>
    <th>Common Attributes</th>
  </tr>
  <tr>
    <td>&lt;title&gt;</td>
    <td>Specifies the title of the document (shown in browser tab)</td>
    <td>Closed</td>
    <td><code>&lt;title&gt;My Page&lt;/title&gt;</code></td>
    <td>—</td>
  </tr>
  <tr>
    <td>&lt;meta&gt;</td>
    <td>Metadata about the document (charset, viewport, description, etc.)</td>
    <td>Empty</td>
    <td><code>&lt;meta charset="UTF-8"&gt;<br>&lt;meta name="description" content="My site"&gt;</code></td>
    <td>charset, name, content, http-equiv</td>
  </tr>
  <tr>
    <td>&lt;link&gt;</td>
    <td>Links external resources (CSS, favicon, etc.)</td>
    <td>Empty</td>
    <td><code>&lt;link rel="stylesheet" href="style.css"&gt;</code></td>
    <td>rel, href, type</td>
  </tr>
  <tr>
    <td>&lt;style&gt;</td>
    <td>Internal CSS styles</td>
    <td>Closed</td>
    <td><code>&lt;style&gt;body { color: red; }&lt;/style&gt;</code></td>
    <td>type, media</td>
  </tr>
  <tr>
    <td>&lt;base&gt;</td>
    <td>Specifies the base URL for all relative URLs in the document</td>
    <td>Empty</td>
    <td><code>&lt;base href="https://example.com/"&gt;</code></td>
    <td>href, target</td>
  </tr>
  <tr>
    <td>&lt;script&gt;</td>
    <td>Embeds or references JavaScript code</td>
    <td>Closed</td>
    <td><code>&lt;script src="main.js"&gt;&lt;/script&gt;</code></td>
    <td>src, type, async, defer</td>
  </tr>
</table>

---

## 📊 Common HTML Typography Elements 

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Element</th>
    <th>Description</th>
    <th>Tag Type</th>
    <th>Display</th>
    <th>Example</th>
    <th>Common Attributes</th>
  </tr>
  <tr>
    <td>&lt;h1&gt;</td>
    <td>Main heading, most important</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;h1&gt;Title&lt;/h1&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;h2&gt;</td>
    <td>Subheading, second level</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;h2&gt;Subtitle&lt;/h2&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;h3&gt;</td>
    <td>Subheading, third level</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;h3&gt;Section&lt;/h3&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;h4&gt;</td>
    <td>Subheading, fourth level</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;h4&gt;Subsection&lt;/h4&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;h5&gt;</td>
    <td>Subheading, fifth level</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;h5&gt;Note&lt;/h5&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;h6&gt;</td>
    <td>Subheading, least important</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;h6&gt;Minor&lt;/h6&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;p&gt;</td>
    <td>Paragraph of text</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;p&gt;Hello World&lt;/p&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;pre&gt;</td>
    <td>Preformatted text</td>
    <td>Closed</td>
    <td>Block</td>
    <td>&lt;pre&gt;   Text&lt;/pre&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;span&gt;</td>
    <td>Inline container for text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;span&gt;Text&lt;/span&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;strong&gt;</td>
    <td>Important text (bold)</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;strong&gt;Important&lt;/strong&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;small&gt;</td>
    <td>Smaller text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;small&gt;Note&lt;/small&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;em&gt;</td>
    <td>Emphasized text (italic)</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;em&gt;Emphasis&lt;/em&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;ins&gt;</td>
    <td>Inserted text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;ins&gt;New&lt;/ins&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;mark&gt;</td>
    <td>Highlighted text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;mark&gt;Highlight&lt;/mark&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;del&gt;</td>
    <td>Deleted text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;del&gt;Old&lt;/del&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;br&gt;</td>
    <td>Line break</td>
    <td>Empty</td>
    <td>Inline</td>
    <td>&lt;br&gt;</td>
    <td></td>
  </tr>
  <tr>
    <td>&lt;hr&gt;</td>
    <td>Thematic break (horizontal rule)</td>
    <td>Empty</td>
    <td>Block</td>
    <td>&lt;hr&gt;</td>
    <td></td>
  </tr>
  <tr>
    <td>&lt;sub&gt;</td>
    <td>Subscript text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;sub&gt;sub&lt;/sub&gt;</td>
    <td>id, class, style, title</td>
  </tr>
  <tr>
    <td>&lt;sup&gt;</td>
    <td>Superscript text</td>
    <td>Closed</td>
    <td>Inline</td>
    <td>&lt;sup&gt;sup&lt;/sup&gt;</td>
    <td>id, class, style, title</td>
  </tr>
</table>

---

> **Note:** In nested typography, block elements (like `<p>`, `<div>`, `<h1>`) can contain inline elements (like `<span>`, `<strong>`, `<em>`), but inline elements cannot contain block elements.

 **Example:**  
✅ Allowed:  
> ```html
> <p>This is <strong>bold</strong> and <em>italic</em> text.</p>
> ```
 ❌ Not allowed:  
> ```html
> <span><p>This is not allowed</p></span>
> ```

---

## 📋 Common HTML List Elements

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Element</th>
    <th>Description</th>
    <th>Display Type</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>&lt;ul&gt;</td>
    <td>Unordered list (bulleted)</td>
    <td>Block</td>
    <td><code>&lt;ul&gt;&lt;li&gt;Item&lt;/li&gt;&lt;/ul&gt;</code></td>
  </tr>
  <tr>
    <td>&lt;ol&gt;</td>
    <td>Ordered list (numbered or lettered)</td>
    <td>Block</td>
    <td><code>&lt;ol&gt;&lt;li&gt;Item&lt;/li&gt;&lt;/ol&gt;</code></td>
  </tr>
  <tr>
    <td>&lt;li&gt;</td>
    <td>List item (child of &lt;ul&gt; or &lt;ol&gt;)</td>
    <td>Block</td>
    <td><code>&lt;li&gt;Item&lt;/li&gt;</code></td>
  </tr>
  <tr>
    <td>&lt;dl&gt;</td>
    <td>Definition list (terms and descriptions)</td>
    <td>Block</td>
    <td><code>&lt;dl&gt;&lt;dt&gt;Term&lt;/dt&gt;&lt;dd&gt;Definition&lt;/dd&gt;&lt;/dl&gt;</code></td>
  </tr>
  <tr>
    <td>&lt;dt&gt;</td>
    <td>Definition term (child of &lt;dl&gt;)</td>
    <td>Block</td>
    <td><code>&lt;dt&gt;Term&lt;/dt&gt;</code></td>
  </tr>
  <tr>
    <td>&lt;dd&gt;</td>
    <td>Definition description (child of &lt;dl&gt;)</td>
    <td>Block</td>
    <td><code>&lt;dd&gt;Description&lt;/dd&gt;</code></td>
  </tr>
</table>

Note: By default, ordered list and unordered list elements have padding applied from the page direction, but definition list doesn't.

Difference between `li` and `dt`:

- `<li>` is used for list items in ordered (`<ol>`) and unordered (`<ul>`) lists.
- `<dt>` is used for terms in a definition list (`<dl>`), paired with `<dd>` for the description.
- **Note:** `<li>` elements can be nested (lists inside lists), but `<dt>` elements cannot be nested inside each other.  
  If you try to nest a `<dl>` inside a `<dt>`, it is not valid HTML and browsers will not render it as a nested definition list.

**Example: Nested `<ul>` (allowed)**
```html
<ul>
  <li>Item 1
    <ul>
      <li>Subitem 1.1</li>
    </ul>
  </li>
</ul>
```

**Example: Nested `<dl>` inside `<dt>` (not allowed)**
```html
<dl>
  <dt>Term 1
    <!-- ❌ This nested <dl> is not valid HTML -->
    <dl>
      <dt>Subterm</dt>
      <dd>Subdefinition</dd>
    </dl>
  </dt>
  <dd>Definition 1</dd>
</dl>
```

---

attachments

---

links

---

## 🔤 HTML Special Characters

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Entity</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>&amp;nbsp;</td>
    <td>Non-breaking space</td>
    <td><code>A&nbsp;B</code></td>
  </tr>
  <tr>
    <td>&amp;lt;</td>
    <td>Less-than sign</td>
    <td><code>&lt;</code></td>
  </tr>
  <tr>
    <td>&amp;gt;</td>
    <td>Greater-than sign</td>
    <td><code>&gt;</code></td>
  </tr>
  <tr>
    <td>&amp;amp;</td>
    <td>Ampersand</td>
    <td><code>&amp;</code></td>
  </tr>
  <tr>
    <td>&amp;quot;</td>
    <td>Double quote</td>
    <td><code>&quot;</code></td>
  </tr>
  <tr>
    <td>&amp;apos;</td>
    <td>Single quote</td>
    <td><code>&apos;</code></td>
  </tr>
  <tr>
    <td>&amp;copy;</td>
    <td>Copyright symbol</td>
    <td><code>&copy;</code></td>
  </tr>
  <tr>
    <td>&amp;reg;</td>
    <td>Registered trademark</td>
    <td><code>&reg;</code></td>
  </tr>
  <tr>
    <td>&amp;euro;</td>
    <td>Euro sign</td>
    <td><code>&euro;</code></td>
  </tr>
  <tr>
    <td>&amp;cent;</td>
    <td>Cent sign</td>
    <td><code>&cent;</code></td>
  </tr>
  <tr>
    <td>&amp;pound;</td>
    <td>Pound sign</td>
    <td><code>&pound;</code></td>
  </tr>
</table>

---

tables

---

forms

🔹 <form>
Attribute	Purpose
action	Where form data is sent
method	GET or POST
🔹 <input>
Attribute	Description
type	Input type (text, email, number, etc.)
name	Key sent to server
id	Connects label
value	Default/submitted value
placeholder	Hint text
required	Must be filled
disabled	Cannot be edited
readonly	Read-only
checked	Default checked
min / max	Numeric limits
step	Increment value
pattern	Regex validation
autocomplete	Browser suggestions
autofocus	Auto focus
multiple	Allow multiple values
accept	File types
list	Connect to datalist
🔹 <textarea>
Attribute	Purpose
rows	Height
cols	Width
placeholder	Hint text
maxlength	Max characters
readonly	Read only
disabled	Disabled


selected

forms inbut have name and id the name repeosnet used in backend DB and data in url and id for suoing in javascript and css and html 

link id with thebale makeyou when you press on the name it move to you the input 

in radio must use name must be the same for link only one value to db

if i set value it will snet to db when be check but if i didn't set a value in radio or check box .. the value would sent to db would be the 

radio butom, checkbox, dropdoen liets and datalist list and reset and submit must have a value 
---

## 📚 Examples

### Example: Simple HTML Page

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First HTML Page</title>
  </head>
  <body>
    <header>
      <h1>Welcome!</h1>
      <nav>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>
    <main>
      <section id="about">
        <h2>About Me</h2>
        <p>This is my first web page.</p>
      </section>
      <section id="contact">
        <h2>Contact</h2>
        <p>Email: <a href="mailto:someone@example.com">someone@example.com</a></p>
      </section>
      <figure>
        <img src="https://via.placeholder.com/150" alt="Placeholder image">
        <figcaption>Sample image</figcaption>
      </figure>
    </main>
    <footer>
      &copy; 2025 My Website
    </footer>
  </body>
</html>
```

---

## 🌐 Localization

In HTML, localization refers to adapting a website’s content and behavior to different languages, regions, and cultures so users feel the site is made for them.

**Example:**
```html
<html lang="ar" dir="rtl">
  <head>
    <meta charset="UTF-8">
    <title>مثال</title>
  </head>
  <body>
    <p>مرحبا بك!</p>
  </body>
</html>
```
- Use the `lang` and `dir` attributes for language and text direction.

---

## 🔍 SEO (Search Engine Optimization)

- Techniques to improve the visibility of web pages in search engines.
- Good HTML structure and semantic tags help with SEO.

---