# shared-styles
A set of LESS styles with useful defaults for Bootstrap variables, and some CSS utility classes.

## What is this?

This is a collection of stylesheets for use on any site where [Bootstrap](http://getbootstrap.com/) is heavily used. 

## How do I do X?

Several use cases are documented inline. Functionality is built on top of [Bootstrap](http://getbootstrap.com/), [LESS](http://lesscss.org/), and [Bower](http://bower.io/).

# Alignment

**Mixins to align the text in several common text-only tags. Most useful when overriding alignment on an element whose ancestors already have an explicit alignment set.**

Three mixins are provided:

Mixin Name | Usage
---------- | -----
`.align()` | Align all heading elements, list items, and paragraphs.
`.align-head()` | Align all heading elements.
`.align-head-major()` | Align the three most important heading elements (`<h1>`, `<h2>`, `<h3>`).

## Alignment - Example

LESS:

    .align-head(center);
    
## Alignment - Usage

Each mixin takes the following parameter:

Parameter Name | Value
-------------- | -----
`@alignment` | Any valid CSS alignment value. Note, the value should *not* be surrounded with quotes.

# Skins

**A mixin to set common colors of a group of elements at their parent. Re-use to create a consistent look and feel across your page.**

The `.make-skin()` mixin is designed to be used within a CSS selector. The selector identifies a containing element, such as a column, panel, or box.

## Skins - Example

LESS:

    #my-element-id {
      .make-skin(@dark-brown, @gray-dark, @gray);
    }
    
## Skins - Usage

Parameter Name | Value
-------------- | -----
`@bkg-color` | A CSS color (hex, rgb, rgba). The background color for the entire containing element.
`@head-color` | A CSS color (hex, rgb, rgba). The color of any heading text (e.g. text within `<h1>`, `<h3>`).
`@body-color` | A CSS color (hex, rgb, rgba). The color of any body text (e.g. text within `<p>`, `<li>`).

    .make-skin(@bkg-color, @head-color, @body-color);
    
# Box

**Add additional padding and a color scheme to any set of related elements. Create your own themes, or use one of the 6 provided. Box variants provide additional flexibility to solve special formatting problems.**

    <div class="box">
      <h1>Some heading</h1>
      <p>Content</p>
    </div>

## Box - Color Scheme

Define a color scheme for a `.box` with the provided mixin. 

The mixin will set the color of any text elements inside, including 

* headings
* paragraphs
* ordered/unordered/description lists
* horizontal rules
* and Font-Awesome icons.

**Example**

    .make-box-skin(box-summer, #fff, @gray-darker);
    
**Usage**

Parameter Name  | Value
--------------- | -----
`@skin-name` | A CSS class name to identify the skin. It does *not* require a leading `.` (dot), or require quotes around the name. Best practice is to make your name match `box-[x]`.
`@color` | A CSS color (hex, rgb, rgba). The color of any text within a box.
`@bg-color` | A CSS color (hex, rgb, rgba). The background color of a box.

Use the skin like you would any Bootstrap theme class.

    <div class="box box-summer">
      <h1>Some heading</h1>
      ...
    </div>

*If you create a box without any theme classes applied, it will default to black text on a white background.*

## Box - Variants

**box-centered**

Centered boxes center-align all of their text content. 

    <div class="box box-centered box-summer">
      <h1>Some heading</h1>
      ...
    </div>

# Full Width Images and Videos

**Force any image or video to take up the entire horizontal space of its parent element. The image or video is not distorted.**

## Full Width Images and Videos - Variants

**img-contain**

The image will stretch to the entire width. Combine with other Bootstrap classes such as `.pull-right` when used within bigger structures.

```html
<img class="img-contain" src="img/placeholder.svg" />
```

**video-contain**

The video will stretch to the entire width. Combine with other Bootstrap classes such as `.pull-right` when used within bigger structures.

```html
<video class="video-contain" src="vid/placeholder.mp4" poster="img/placeholder-wide.svg" preload="metadata" controls/>
```

*If a image or video is a direct child of the body, it will stretch to be the full width of the page. Use with care.*

# Scrolling List Groups

**Make any [Bootstrap list group](http://getbootstrap.com/components/#list-group) scroll to accommodate lists that are too long.**

```html
<div class="list-group list-group-scroll-long">
  <div class="list-group-item">
    <h1>Element</h1>
    <p class="list-group-item-text">...</p>
  </div>
  <a class="list-group-item" target="_blank" href="#">
    <p class="list-group-item-text">...</p>
  </a>
</div>
```

*Note! Currently, a scroll bar is always visible on these elements, even if the number of items is less than the max for that list group.*

**list-group-scroll-short**

List group will accommodate approximately 3 elements before scrolling the items within.

```html
<div class="list-group list-group-scroll-short">
  ...
</div>
```

**list-group-scroll-long**

List group will accommodate approximately 7 elements before scrolling the items within.

```html
<div class="list-group list-group-scroll-long">
  ...
</div>
```

