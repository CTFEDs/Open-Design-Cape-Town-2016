autoscale: true
footer: GAAD 2016
slidenumbers: true
build-lists: true

# WAI-ARIA

## a whistle-stop tour

---

## What is WAI-ARIA?

The WAI bit is the Web **Accessibility Initiative**[^1] at the W3C.

[^1]: See [Web Accessibility Initiative](https://www.w3.org/WAI/)

^ WAI develops guidelines widely regarded as the international standard for Web accessibility, support materials to help understand and implement Web accessibility and resources, through international collaboration.

---

## What is WAI-ARIA?

The WAI bit is the **Web Accessibility Initiative**[^1] at the W3C.

The ARIA bit stands for **Accessible Rich Internet Applications**, first published on 20 March, 2014

[^1]: See [Web Accessibility Initiative](https://www.w3.org/WAI/)

^ ARIA provides a means to make web applications and widgets more accessible to a diverse range of users, including those who use assistive technologies such as screen readers or magnifiers.

^ Roles, properties, states

^ WAI-ARIA is backwards compatible, i.e. it can be applied to any version of HTML

---

# Roles

- ARIA provides a rich role taxonomy that enables you to classify otherwise meaningless tags such as `<div>`, `<span>`, etc.
- Roles are added to HTML tags like any other attribute

^ Roles tell the browser to tell assistive technologies that an HTML element fulfills a particular role and describe widgets that aren't otherwise available in HTML. eg. sliders, menu bars, tabs, and dialogs

---

# Role categories[^2]

- Abstract Roles
- Widget Roles
- Document Structure Roles
- Landmark Roles

[^2]: See [Role categories](https://www.w3.org/TR/wai-aria/roles#abstract_roles) on the W3C website

^ Abstract roles are used to support the WAI-ARIA role taxonomy for the purpose of defining general role concepts.
  Widget roles act as standalone user interface widgets or as part of larger, composite widgets.
  Document Structure roles describe structures that organize content in a page.
  Landmark roles are regions of the page intended as navigational landmarks.

---

# States and Properties

ARIA states and properties offer the user further information on how to interact with a particular widget.

^ This is all about revealing the relationships and states of our application to users on keyboards and screen readers. They define the state of certain native or WAI-ARIA elements such as if something is collapsed or expanded, a form element is required, something has a popup menu attached to it or the like. These are often dynamic and may change their values throughout the lifecycle of a web application, and are usually manipulated via JavaScript.

---

# Using ARIA roles

---

# Using ARIA roles

`<div class="fancy-button" role="button">Click me</div>`

---

# Using ARIA roles

~~`<div class="fancy-button" role="button">Click me</div>`~~

^ Just because you can doesn't mean you should.

---

# Using ARIA roles

~~`<div class="fancy-button" role="button">Click me</div>`~~

`<button class="fancy-button" role="button">Click me</button>`

^ A div with a role of "button" does not suddenly have keyboard focusability, an automatic click handler when Space or Enter are pressed, or any other properties associated with a button tag. The browser itself does not know that a div with role of "button" is a button, only its accessibility API does.

---

# Using ARIA roles

~~`<div class="fancy-button" role="button">Click me</div>`~~

~~`<button class="fancy-button" role="button">Click me</button>`~~

^ Where roles have HTML equivalents it is best not to use them.

---

# Using ARIA roles

~~`<div class="fancy-button" role="button">Click me</div>`~~

~~`<button class="fancy-button" role="button">Click me</button>`~~

`<button class="fancy-button">Click me</button>`

^ Because a button has an inherent accessibility role, and attendant properties and states, we do not need to assign its ARIA equivalent.

^ Note: not all HTML elements are inherently accessible. Not all browsers map inherent accessibility roles (IE, EDGE, Safari particularly poor). As in all things, BALANCE.

---

# Using ARIA properties and states

---

# Using ARIA properties

```HTML
<ol>
  <li id="link-one">
    <a href="#panel-one">Chapter 1</a>
  </li>
  <li id="link-two">
    <a href="#panel-two">Chapter 2</a>
  </li>
</ol>
<div id="panel-one">
  Chapter 1 content goes here
</div>
<div id="panel-two">
  Chapter 2 content goes here
</div>
```

^ This is a tabs widget. How would you know, looking only at the markup? A screen reader will have no idea. Also, with tabs one or more panels will be hidden causing even more difficulties for assistive technologies.

---

# Using ARIA properties

```HTML
<ol role="tablist">
  <li id="link-one" role="tab">
    <a href="#panel-one">Chapter 1</a>
  </li>
  <li id="link-two" role="tab">
    <a href="#panel-two">Chapter 2</a>
  </li>
</ol>
<div id="panel-one" role="tabpanel" aria-labelledby="link-one">
  Chapter 1 content goes here
</div>
<div id="panel-two" role="tabpanel" aria-labelledby="link-two">
  Chapter 2 content goes here
</div>
```

^ Here we are adding the missing semantics needed by assistive technologies by describing this widget in more detail, and by adding special attributes to the markup.

---

# Using ARIA states[^3]

- attributes for declaring the current state of a UI widget.
- Some examples:
    - **aria-checked:** indicates the state of a checkbox or radio button
    - **aria-disabled:** indicates that an element is visible, but not editable or otherwise operable

[^3]: See [Supported states and properties](https://www.w3.org/TR/wai-aria/states_and_properties) for a full list

^ We can use ARIA states to indicate the state of UI widget elements and use CSS attribute selectors to alter the visual appearance based on the state changes (rather than using script to change a class name on the element).

---

# Using ARIA states

```HTML
<ol role="tablist">
  <li id="link-one" role="tab" aria-checked="true">
    <a href="#panel-one">Chapter 1</a>
  </li>
  <li id="link-two" role="tab"  aria-checked="false">
    <a href="#panel-two">Chapter 2</a>
  </li>
</ol>
<div id="panel-one" role="tabpanel" aria-labelledby="link-one" aria-hidden="false">
  Chapter 1 content goes here
</div>
<div id="panel-two" role="tabpanel" aria-labelledby="link-two" aria-hidden="true">
  Chapter 2 content goes here
</div>
```

---

# Styling ARIA states

```CSS
li[aria-checked="true"] {
  background-color: rgb(200, 100, 100);
  color: white;
  font-weight: 400;
  text-align: center
  ...
}
```

^ Attribute selectors allow us to style sates in CSS.

---

# Styling ARIA states

```CSS
div[aria-hidden="true"] {
  display: none;
  visibility: hidden;
}
```
^ Make changes to states via js.

---

# Questions?