# Responsive Design Initiative

Our **Responsive Design Initiative** ensures that ioBroker works smoothly across all devices, regardless of screen size. To help developers achieve this, we’ve compiled a guide for configuring responsive layouts in the **jsonConfig** and **Materialize** adapters. This document highlights the key points to consider when making adapters mobile-friendly.

---

**How To:** [Check for responsive design compability](https://github.com/iobroker-community-adapters/responsive-design-initiative/blob/main/developer_guide_optimizing_responsive_design.md)

## jsonConfig Adapter

For **jsonConfig** adapter, it’s important to consider all screen resolutions in the inputs. The following resolution breakpoints should be used:

* **xl** - Extra large screens (width > 1536px), width as 1/12 of the screen
* **lg** - Large screens (1200px <= width < 1536px), width as 1/12 of the screen
* **md** - Medium screens (900px <= width < 1200px), width as 1/12 of the screen
* **sm** - Small screens (600px <= width < 900px), width as 1/12 of the screen
* **xs** - Tiny screens (width < 600px), width as 1/12 of the screen

### We recommend the following values for the standard layout

#### Input
````JSON
"xs": 12,
"sm": 12,
"md": 6,
"lg": 4,
"xl": 4
````

#### Table and Header
````JSON
"xs": 12,
"sm": 12,
"md": 12,
"lg": 12,
"xl": 12
````

### Table Styling:
To ensure that the table bar is legible, add the following entry below "type": "tabs":

````JSON
"tabsStyle": {
  "width": "calc(100% - 100px)"
},
````

---

## Materialize Adapter

For adapters in the **Materialize** design, important classes for the correct resolution should also be used for mobile devices.

### List of classes for different resolutions:

* lx - For large screens (1200px <= width < 1536px), width as 1/12 of the screen
* mx - For medium screens (900px <= width < 1200px), width as 1/12 of the screen
* sx - For small screens (600px <= width < 900px), width as 1/12 of the screen

The recommended values for a `<div>` are as follows:

````HTML
<div class="col s12 m6 l4">
````

The classes `s`,`m` and `l` must be configured in each `<div>`.

### Custom CSS for the mobile resolution

If custom CSS is used, make sure to define specific styles for mobile resolutions. Use the following media queries:

````CSS
/* Style for small Screens */
@media screen and (max-width: 768px) {
  /* Your styles here */
}
````

````CSS
/* Style for very small Screens */
@media screen and (max-width: 600px) {
  /* Your styles here */
}
````
### Integration of CSS and JS Files
It is also important that the following JS and CSS files are included in `index_m.html` or `tab_m.html`

````HTML
<!-- Load ioBroker scripts and styles -->
<link rel="stylesheet" type="text/css" href="../../lib/css/fancytree/ui.fancytree.min.css" />
<link rel="stylesheet" type="text/css" href="../../css/adapter.css" />
<link rel="stylesheet" type="text/css" href="../../lib/css/materialize.css">

<script type="text/javascript" src="../../lib/js/jquery-3.2.1.min.js"></script>
<script type="text/javascript" src="../../socket.io/socket.io.js"></script>

<script type="text/javascript" src="../../lib/js/materialize.js"></script>
<script type="text/javascript" src="../../lib/js/jquery-ui.min.js"></script>
<script type="text/javascript" src="../../lib/js/jquery.fancytree-all.min.js"></script>

<script type="text/javascript" src="../../js/translate.js"></script>
<script type="text/javascript" src="../../js/adapter-settings.js"></script>
<script type="text/javascript" src="words.js"></script>
````

`adapter-settings.js` and `adapter.css` are very important for a responsive design. These files are provided and maintained by the admin.

