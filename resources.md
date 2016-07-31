---
layout: default
title: Resources
---

## Examples

* Heydon Pickering's [practical ARIA examples](http://heydonworks.com/practical_aria_examples/)
* Font Awesome 4.6 Released: [Making accessibility more accessible](https://articles.fortawesome.com/font-awesome-4-6-released-d7213342698a#.j8om7wij4)
* [Code Library (Beta) from Deque University](https://dequeuniversity.com/library/)
* [Simply Accessible examples](http://examples.simplyaccessible.com/)

## Checklist

* [Vox accessibility guidelines](http://accessibility.voxmedia.com/)

### Primary

* [Validate](http://validator.w3.org/) your HTML.
* Use HTML5 elements like `section`, `article`, `header`, `footer`, and `nav`.* Make sure every image has `alt` text.
* Use the `picture` element and `srcset` to provide the image most suitable for the user's device. You can use [Picturefill](http://scottjehl.github.io/picturefill/) to enable support for `picture` in browsers that don't support it yet.
* Think about performance: what are you loading that people won't see?
* Ensure that your HTML document follows correct outline guidelines. See [Document Outlines](http://html5doctor.com/outlines/) for an excellent introduction.

### Secondary

* Use HTML5 input types like `search`, `email`, and `date`.
* Don't use inline CSS (using the `style` tag or `style` attribute on HTML elements): use external stylesheets (using the `link` tag). The exception is for [critical CSS](https://developers.google.com/speed/docs/insights/PrioritizeVisibleContent#RemoveUnusedCSS): initially sending a small amount of CSS in the head of the document so that page rendering starts as early as possible.
* Don't use inline JS (using a `script` tag or directly on an HTML element): include external JS files (using the `src` attribute on a `script` element).
* Place `script` elements at the bottom of the page, or load them asynchronously by adding the `async` attribute to the `script` tag (this means that the loading of the JavaScript files won't block loading of the page).
* Colour and contrast. Ensure sufficient contrast to make site readable for everyone.
* Colour blindness test with [Colorblind Web Page Filter](http://colorfilter.wickline.org/)

## Tools

* [pa11y](http://pa11y.org/)
* [a11y](https://addyosmani.com/a11y/)
* [tenon](https://tenon.io/)
* [axe](http://www.deque.com/products/axe/)
* [The A11y Machine](https://github.com/liip/TheA11yMachine)
* [BBC Accessibility Standards Checker](https://github.com/bbc/bbc-a11y)
* [Google Chrome Accessibility Developer Tools](https://github.com/GoogleChrome/accessibility-developer-tools)
* [Google Chrome Accessibility Developer Tools browser extension](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en)
* [Firefox Accessibility Evaluation Toolbar](https://addons.mozilla.org/en-US/firefox/addon/accessibility-evaluation-toolb/) - (not working in FF46+ but fix is in the works)
* [tota11y](http://khan.github.io/tota11y/), an accessibility visualization toolkit
* Web Aim's [Web Accessibility Evaluation Tool](http://wave.webaim.org/)
* Big list on [Paciello Group](https://www.paciellogroup.com/blog/2014/10/accessibility-testing-tools-updated/)
* [Lea Verou's colour contrast ratio checker](http://leaverou.github.io/contrast-ratio/)
* [HTML 5 Outliner](https://gsnedders.html5.org/outliner/)
* [Mozilla Developer Network ARIA documentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)
* [HTML5 Accessibility support status](http://stevefaulkner.github.io/HTML5accessibility/)
* [W3C ARIA 1.0 Implementation Report](https://www.w3.org/WAI/ARIA/1.0/CR/implementation-report) - useful to see how patchy support for role mapping is.
