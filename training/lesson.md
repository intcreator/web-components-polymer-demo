# Web Components and Polymer

## Intro

What sites use Polymer?

- YouTube
- Google Earth
- Polymer Project
- Webcomponents.org
- [see more](https://github.com/Polymer/polymer/wiki/Who's-using-Polymer%3F)

## Setup

1. Install Bower (you can probably use NPM too if you like)
```
$ npm install -g bower
```
2. Install Polymer CLI and create a Polymer app ([directions](https://www.polymer-project.org/2.0/start/install-2-0))
3. Add additional element dependencies and hack stuff

## Web Components

Web components are native in Chrome and [somewhat supported in other browsers](http://caniuse.com/#search=web%20components).  You can use polyfills for [full support back to IE 11](https://github.com/webcomponents/webcomponentsjs#browser-support).

In Chrome, Polymer dependencies usually run around 1-10kb.  You will need to import the Polymer library, web component polyfills if needed, and any elements used.

### HTML Imports

A way to easily import HTML.  Usually we import JS, CSS, images, video, audio etc. easily but not HTML.

HTML imports allow custom elements build in HTML to be easily imported to HTML pages or other elements.

- HTML imports are automatically de-duped.
- Can be asynchronous
- Synchronous imports block rendering but not parsing

HTML imports look like this:

```html
<link rel="import" href="path/to/resource.html">
```

### Custom Elements

A native implementation for reusable elements.  Custom elements look like this:

```html
<custom-element prop="my-prop"></custom-element>
```

### Shadow DOM

The following are scoped to the element:

- CSS
- Access to nodes with `querySelector`

You can treat each element as if it were its own HTML page when using IDs and classes (no stepping on toes).

You can still import global styles on a per-element basis.

#### Mixins

What if you still want to style elements externally?  Use a mixin.

### HTML Templates

HTML templates are blocks of HTML that are not shown until cloned.

HTML templates are the basis of Polymer elements.  A template is created and then defined in `customElements`.

HTML templates are supported in most browsers natively.

HTML templates look like this:

```html
<template>
  <style>
    /* code */
  </style>

  <div>
    <!-- code -->
  </div>
</template>
```

## Using Polymer

### Routing

Polymer includes the `<app-route>` element which implements modular (per-element) routing.

This means you can have one element that routes high level pages like

- home
- dashboard
- about
- support

And a different element (such as dashboard) can route lower level pages like

- summary
- insights
- settings

These elements can have content in addition to routing, because the `<app-route>` element handles most of the actual routing work.

### Data binding

Polymer takes care of updating properties with bindings.  Bindings can be one way (`[[myProp]]`, parent to child) or two way (`{{myProp}}`, parent to child and child to parent).

### Pre built elements

Polymer is open source.  Many people contribute to Google's official Polymer elements and make their own Polymer compatible elements.

The most common resource to find elements is [webcomponents.org](https://www.webcomponents.org/).

## Conclusion

Hope you enjoyed learning about web components and Polymer!
