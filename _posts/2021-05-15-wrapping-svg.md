---
layout: post
title: What's better to wrap a SVG - Object, or Img?
---

Recently I was faced with the situation where I had to use SVG icons in my web app. What did I do next? Wrapped the SVG in `<Img>` tag and went with it. It worked obviously, but it had its own shortcomings. This is what I'm going to discuss today.

Let's get started with discussing the cons of wrapping a svg in a `<Img>` tag:

- Limited CSS based styling.
- In-line styling is required for some of them to work.
- External Stylesheets have no effect on them except for few basic modifications.

## What should I use then?

Let's take a look at the syntax for both of of them:

- Image Tag <br />
  `<img src="./sample.svg" alt="Sample SVG" />`
- Object Tag <br />
  `<object data="sample.svg" type="image/svg+xml"> <img src="fallback.jpg" /> </object> `

> If you just need the SVG use the `img` tag, otherwise for an interactive SVG use `object` tag.

## Why I used `img` inside the `object` tag?

It's called a fallback image incase there's an issue loading the SVG. The fallback png or jpg is used to replace it. Sounds amazing right. That's one of the cool benefit of using a object tag.

## My Conclusion

If I were to use a SVG in a everyday scenario, I would use object tag over other available tags like `img`, `embed`, or `iframe`.
