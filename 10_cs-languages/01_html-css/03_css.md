# Css Cheatsheet

## Table of Contents
1. [Comments](#Comments)
1. [Lists](#Lists)
1. [Images](#Images)
1. [Video & Audio](#Video-&-Audio)

## Comments
```css
/* This is a single-line css comment */
/* This is
a multi-line
comment */
```

## Lists
```html
<!-- navigation menu with 4 lists (unordered lists "ul") -->
<ul>
    <li>About me</li>
    <li>Courses</li>
    <li>Subscribe</li>
    <li>Contact me</li>
</ul>
```

```css
ul {
    /* changes bullets to square */
    list-style-type: square; 

    /* remove all bullet points */
    list-style-type: none;
}
```

## Images
```html
<img src="images/coffee.jpg" alt="A coffee mug on a table">
```
- use `object-fit` property to keep img not distorted.
- `object-fit` is useful for rectangular images transformed into squared images.
- review the different options for `object-fit`.
```css
img {
    width: 200px;
    height: 200px;
    object-fit: cover; 
}
```

## Video & Audio
```html
<!-- VIDEO -->
<!-- best practice to include fall back text "Your browser doesn't support videos" -->
<video controls autoplay loop src="videos/ocean.mp4">Your browser doesn't support videos.</video>

<!-- AUDIO -->
<!-- same attributes as the video -->
<audio src=""></audio>
```
```css
video {
    /* browser will automatically calculate the height based on the aspect ration of the video */
    width: 400px; 
}
```