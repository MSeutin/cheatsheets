# Html Cheatsheet

## Table of Contents
1. [Structure](#Structure)
1. [Html Head](#Html-Head)
1. [Text](#Text)
1. [Entities](#Entities)
1. [Hyperlinks](#Hyperlinks)
1. [Images](#Images)
1. [Video & Audio](#Video-&-Audio)
1. [Lists](#Lists)
1. [Tables](#Tables)
1. [Containters](#Containers)
1. [Semantic Elements](#Semantic-Elements)
1. [Forms](#Forms)

## Structure
#### Type of Document
```html
<!DOCTYPE html> <!-- document will be html 5 -->
<html lang="en"> <!-- best practice to include language -->
    <head>
        <title>My First Web Page</title>
    </head>
    <body>
    </body>
</html>
```

## Html Head
```html
<head>
    <meta charset="UTF-8"> <!-- ASCII only works with the english language, UTF-8 can represent all languages -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- so that our viewport looks good on all devices -->
    <meta name="keywords" content="HTML, CSS"> <!-- search engine optimization -->
    <meta name="description" content="..."> <!-- gives everyone info about our webpage -->
    <title>Document</title>
</head>
```

## Text
- Remember that style elements such as <em>, <strong>.., are for search engines but styling needs to be done in CSS.
- Example (css rules) :
```css
em { 
    color: red;
    font-style: normal;
}
```
```html
<!-- Elements Covered -->
<h1>Heading 1</h1> <!-- every page should have a single <h1> element -->
<h2>Heading 2</h2> <!-- do not use <h1>,..<h6> for sizes but for HIERARCHY for search engines (styling n size in css) -->
<h3>Heading 3</h3> <!-- do not skip headings after <h1> do a <h2> and not a <h3> for example -->
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
<em>default italics (but style in css)</em> <!-- only use <em> and <strong> so that we can refer to it in css -->
<strong>default bold (but style in css)</strong>
<body>
    <p>I love to teach you <em>HTML!</em></p> <!-- the <em> element emphasizes content by making it italic for most browsers -->
    <p>I love to teach you <strong>HTML!</strong></p> <!-- the <strong> element represents strong importance by making it bold for most browsers -->
</body>
```

## Entities
- Some characters are reserved words in HTML so we use entities so that we do not confuse the browsers.
- All Entities start with and ampersand ( & ), and end with a semi-colon ( ; ).
- Example of Entities :
```html
&lt; <!-- less than sign ( < ) -->
&gt; <!-- greater than sign ( > ) -->
&copy; <!-- copyright element -->
&nbsp; <!-- non breaking space -->
<!-- look at an online reference for list of Entities, no need to memorize them -->
```

## Hyperlinks
```html
<a href="company/about.html">About Me</a> <!-- regular link -->
<a href="company/about.html"><img src="images/mosh.jpg" alt="image of michael"></a> <!-- image link -->
<a href="images/michael.jpg" download>Download my Photo</a> <!-- link to my photo w a download for user -->
<a href="https://google.com">Google</a> <!-- use the http or https protocol for external links/sites -->
<a href="https://google.com" target="_blank">Google</a> <!-- open Google in a new tab -->
<a href="mailto:frenchmike@gmail.com">Email Me</a> <!-- link to an email w mailto: [opens local mail client n populate w given email address -->

<!-- ON PAGE LINKS -->
<a href="#section-css">CSS</a> <!-- JUMP TO THAT CSS SAME PAGE SECTION >
<h2 id="section-css">CSS</h2> <!-- defining a fragment or a place on this page -->
<p>CSS section with a lot of writing ...</p>

<!-- JUMPT TO TOP OF PAGE -->
<a href="#">Jump to Top</a> <!-- use an empty hash sign to jump to top of the page -->
```

## Images
- Use `alt` for search engines, or when img can not be loaded, or for the visually impaired.
- For sizing, please see `img` in my css section (other file).
```html
<img src="images/coffee.jpg" alt="A coffee mug on a table">
```

## Video & Audio
- `controls` is a boolean attribute (true / false).
- `controls` adds the play/pause ... buttons.
- `autoplay` is another boolean attribute that will start the vid automatically.
- `loop` is another useful boolean attribute.
- see my `css` sheet for more settings.
```html
<!-- VIDEO -->
<!-- best practice to include fall back text "Your browser doesn't support videos" -->
<video controls autoplay loop src="videos/ocean.mp4">Your browser doesn't support videos</video>

<!-- AUDIO -->
<!-- same attributes as the video -->
<audio src=""></audio>
```

## Lists
- `ul` is often use for navigation menues (unordered lists).
- we style it in `css`

```html
<!-- navigation menu with 4 lists (unordered lists "ul") -->
<ul>
    <li>About me</li>
    <li>Courses</li>
        <ul>
        li*3 <!-- how to generate items faster using zen coding -->
        </ul>
    <li>Subscribe</li>
    <li>Contact me</li>
</ul>

<!-- create ordered lists with "ol" -->
<!-- zen shortcut to create the below structure -->
<!-- ol>li*3 -->
<ol>
    <li>Preheat the oven.</li>
    <li>Place the ingredients on the crust.</li>
    <li>Put the pizza in the oven for 20 minutes.</li>
</ol>

<!-- description lists -->
<!-- useful for metadata, glossaries -->
<dl>
    <dt>HTML</dt>
    <dd>Hypertext Markup Language</dd>
    <dt>CSS</dt>
    <dd>Cascadign Stylesheets</dd>
</dl>
```

## Tables
#### Example 
<table border = "1">
    <tr>
        <th>Name</th>
        <th>Salary</th>
    </tr>
    <tr>
        <td>Ramesh Raman</td>
        <td>5000</td>
    </tr>
    <tr>
        <td>Shabbir Hussein</td>
        <td>7000</td>
    </tr>
</table>

#### Table Elements
```html
<table> <!-- wrapper element for all tables -->
<thead> <!-- defines column headers -->
<tbody> <!-- defines body -->
<tfoot> <!-- defines footer -->
<tr> <!-- sets up a row -->
<th> <!-- cell w bold centered text -->
<td> <!-- cell -->
```

#### Table Attributes
```html
<border> <!-- specify border around table & cells -->
<align> <!-- set the alignment of table horizontally -->
<colspan> <!-- number of columns a td element should span -->
<rowspan> <!-- number of rows a td elment should span -->
<!-- Examples -->
<table border="1"> ... </table>
<table align="center"> ... </table>
<td colspan="2"> Text will span horizontally </td> <!-- cell will span 2 columns -->
<td rowspan="2"> Text will span vertically </td> <!-- cell sill span 2 rows -->
```

## Containers
`div` : block level element, usually used with class to isolate the element.
`span`: in-line level element.  Will not extend to the other side of the screen.

## Semantic Elements

Prefered over generic `div` and `span`.  Will help you stay organized & serach engines find the appropritate sections.
List of Semantic Elements
- `<article>` : Independent, self-contained content such as
    - Forum Post
    - Comments ...
- `<figure>` : container for images.
- `<figcaption>`; caption for the `<figure>` element.
- `<mark>` : highlight or mark content.
- `<time>` : for date & time.

List of Semantic Elements (for page structure)

```html
<header>
    <nav>
    </nav>
</header>
<main>
    <section>
        <article></article>
        <article></article>
    </section>
</main>
<footer>
</footer>
```

## Forms
