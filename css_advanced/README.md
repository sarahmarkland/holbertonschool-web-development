Readme for CSS Advanced

# General
## What is CSS
Cascading Style Sheet or CSS is a stylesheet language that dictates how your website elements should look like. You can control the design, layout, font, and color of your website content by embedding a CSS file into your HTML document.

Let’s take a look at how CSS works by breaking down the syntax:  
`selector {declaration}`  

The declaration can be broken down into:  
`selector {property: value;}`  

Let’s say you want the font size of your heading one (h1) to be 20 pixels. Your syntax should look like this:  
`h1 {font-size: 20px;}`  

## How to add style to an element
`selector {`  
`    property: value;`  
`}`  
selector: This is the HTML element you want to style. It could be a tag name (e.g., div, p, h1), a class (e.g., .my-class), an ID (e.g., #my-id), or other types of selectors.

property: This is the CSS property you want to apply to the element. CSS properties define various aspects of the element's appearance or behavior (e.g., color, font-size, background-color, margin, etc.).

value: This is the value you want to set for the CSS property.
## What is a class
A class is a way to apply styles to one or more HTML elements.  

## What is a selector
In CSS (Cascading Style Sheets), a selector is a pattern that specifies which HTML elements in a web page should be affected by a set of CSS rules. Selectors are a fundamental part of CSS because they determine which elements get styled and how they get styled. Here are some common types of CSS selectors:

**Type Selector:**
Matches all HTML elements of a specific type (e.g., paragraph, div, header). 
 
```css
p {
    /* CSS rules for all <p> elements */
}
```

**Class Selector:**
Matches elements with a specific class attribute value. Classes are defined using the period (.) notation.
```css
.my-class {
    /* CSS rules for elements with class="my-class" */
}
```
**ID Selector:**
Matches a single element with a specific id attribute value. IDs are defined using the hash (#) notation.
```css
#my-id {
    /* CSS rules for an element with id="my-id" */
}
```
Descendant Selector:

Matches elements that are descendants of another element.
```css
.parent-class .child-class {
    /* CSS rules for elements with class="child-class" that are descendants of elements with class="parent-class" */
}
```
**Child Selector:**
Matches elements that are direct children of another element.
```css
.parent-class > .child-class {
    /* CSS rules for elements with class="child-class" that are direct children of elements with class="parent-class" */
}
```
**Attribute Selector:**
Matches elements with a specific attribute and, optionally, a specific attribute value.
```css
input[type="text"] {
    /* CSS rules for <input> elements with type="text" */
}
```
**Pseudo-class Selector:**
Matches elements based on a state or condition, such as :hover, :active, :first-child, and many more.
```css
a:hover {
    /* CSS rules for <a> elements when hovered over */
}
```
**Universal Selector:**
Matches all elements on the page.
```css
* {
    /* CSS rules for all elements */
}
```
**Grouping Selector:**
Allows you to group multiple selectors together and apply the same styles to all of them.
```css
h1, h2, h3 {
    /* CSS rules for <h1>, <h2>, and <h3> elements */
}
```
Selectors are used to target specific elements in your HTML markup and apply styles to them, giving you fine-grained control over the appearance and layout of your web pages. You can also combine and nest selectors to create complex rules and achieve more specific targeting of elements.

## How to compute CSS Specificity Value
**Specificity is a value or weight that determines which CSS rules should be applied to an element when there are conflicting or competing rules.** It's a way to resolve conflicts when multiple CSS rules target the same element or property. Specificity helps the browser decide which styles should take precedence.

Specificity is calculated based on the following criteria, in order of importance:

**Inline Styles:** Styles defined directly in the HTML using the style attribute. These have the highest specificity.

Example:

```html
<p style="color: red;">This text is red.</p>
```
**ID Selectors:** Selectors that target elements by their id attribute.

Example:

```css
#my-element {
    color: blue;
}
```
**Class Selectors, Attribute Selectors, and Pseudo-Classes:** Selectors that target elements by their class names, attribute values, or pseudo-classes like :hover.

Example:

```css
.my-class {
    color: green;
}
```
**Type Selectors and Pseudo-Elements:** Selectors that target elements by their HTML tag name (e.g., div, p) or pseudo-elements like ::before and ::after.

Example:

```css
p {
    color: orange;
}
```
The specificity value is represented as a four-part number, with each part corresponding to one of the criteria above. The parts are counted from left to right, and a higher number indicates higher specificity. For example, the specificity value "0, 1, 3, 2" means:

- 0 Inline Styles
- 1 ID Selectors
- 3 Class Selectors, Attribute Selectors, and Pseudo-Classes
- 2 Type Selectors and Pseudo-Elements  

When two or more rules conflict and target the same element, the rule with the highest specificity value takes precedence. If specificity values are equal, the rule that appears later in the stylesheet is applied *(this is known as the "cascading" part of Cascading Style Sheets)*.

It's important to understand specificity because it helps you predict which styles will be applied when you have complex CSS rules, and it allows you to write more maintainable and predictable stylesheets. In general, *it's a good practice to keep your specificity as low as possible* to make your CSS easier to manage and troubleshoot.
## What are Box properties in CSS
In CSS (Cascading Style Sheets), box properties refer to a set of CSS properties that *control the layout and dimensions of HTML elements as if they were contained within rectangular boxes*. These properties are crucial for designing the visual structure and arrangement of elements on a web page. Here are some important CSS box properties:

Width and Height (width and height):

These properties determine the dimensions of an element's content box. You can set the width and height in various units (e.g., pixels, percentages, ems) to control the element's size.
```css
.box {
    width: 200px;
    height: 100px;
}
```
Padding (padding):

Padding is the space between an element's content and its border. You can set padding for all sides or individually for top, right, bottom, and left using properties like padding-top, padding-right, padding-bottom, and padding-left.
```css
.box {
    padding: 20px; /* Applies padding to all sides */
}
```
Border (border):

The border property is used to set the border around an element. It includes properties like border-width, border-style, and border-color to specify the border's width, style, and color.
```css
.box {
    border: 2px solid #333; /* 2-pixel solid border with color #333 */
}
```
Margin (margin):

Margin is the space outside an element, affecting its positioning and layout in relation to other elements. Like padding, you can set margin for all sides or individually.
```css
.box {
    margin: 10px; /* Applies margin to all sides */
}
```
Box Sizing (box-sizing):

This property determines how an element's total width and height are calculated. The default value is content-box, which calculates dimensions excluding padding and border. You can set it to border-box to include padding and border in the dimensions.
```css
.box {
    box-sizing: border-box; /* Includes padding and border in width/height calculations */
}
```
Overflow (overflow):

This property controls what happens when the content inside an element overflows its dimensions. Common values include visible (default, content overflows), hidden (content is clipped), scroll (adds scrollbars), and auto (adds scrollbars when necessary).
```css
.box {
    overflow: scroll; /* Adds scrollbars when content overflows */
}
```
## How does the browser load a webpage
