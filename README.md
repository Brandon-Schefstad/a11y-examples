# HTML Best Practices
Screen readers analyze a site's HTML for specific landmarks and tags, then use that information to create a usable interface with text-to-speech support. Most screen reading software allows the user to collect all properly marked links, headings, and form items. This lets the user scan the page as a sighted person would or use quick-jump menus to navigate. 

Screen readers rely on well-architected HTML code to correctly interpret a website. Without this consideration even the most sleek websites can become frustrating, and even harmful experiences. 

When considering screen reader accessibility to your site, there are a few key rules to follow.

## Semantic HTML 
https://www.w3schools.com/html/html5_semantic_elements.aspLinks to an external site. 

Semantic HTML is simply the use of pre-defined, meaningful tags in your markup. This allows for screenreader technology to cleverly analyze a webpage and provide extra functionality. Some may be straightforward such as `<main>`, `<nav>`, and `<section>`. Importantly, `<div>` is not considered a semantically rich tag, and should not be used where other tags may apply. 

When used correctly, screenreaders are able to scan a webpage much like a sighted person. 

Practicing: When building a new page, sketch out the general layout and determine which semantic tags best fit the goal of any particular element. 


## Heading Hierarchy
This goes in tandem with semantic HTML. Heading hierarchy is extremely important to the structure of a website. Some screen readers can collect and list the headings of a document and organize them into a quick menu to navigate through the page. 

Headings (h1-h6) should abide by the following:

Follow logical order (don't skip from h1 to h4)
Should not be used simply for styling
Should be used instead of <span> or <p> with heading styling
Code example before and after. 

Incorrect: Using class names for styling

<span class=`h1`> Our Important Title </span>
<p class=`h4`>Hello and welcome to our super cool website.</p>

Correct: Using heading tags instead.

<h1> Our Important Title </h1>
<h2> Hello and welcome to our super cool website.</h2>

## Focus Order
Focus is determined by mouse clicks or using the tab key. You can cycle through all focusable items by pressing the Tab key repeatedly. Some HTML tag receive focus by default (<a>, <button>, <input>, etc.).

In your web apps focus order should be logical - top-down, left-right, staying within modals and container elements. 

If you have something you would like focusable but is not a standard tag, you can add the 'tabindex' attributeLinks to an external site. to the tag like so:

<h1 tabindex=0> Our Important Title </h1>

A tabindex of 0 will add the element to the focus order of the page. It will appear after the focusable element that comes right before it. 

A tabindex of -1 will allow you to assign focus via javascript, but will not include the element in the focus order of the page. 

A tabindex of 1 will add the element to the end of the focus order (and tabindex of 2 will come after that). It is recommended that you do NOT do this as it breaks the logical flow of the page. If you find yourself reaching for positive tabindex, rethink the logical structure of your page. 

## Descriptive Images
Images are one of the easiest elements to rectify for accessibility. All non-decorative images must have alternative text (shortened to 'alt text' going forward). The alt text provides equivalent information for screen-reader users. 

Take for example this image: 

image.png

Alt text should capture the essential information within the image. For example: `Close up of graduating students, from behind.` would be perfect for this image. Avoid using `image/picture of` or the file name within alt text. 

https://www.w3.org/WAI/tutorials/images/functional/Links to an external site. 

## Descriptive Links
Links should describe their purpose or destination. 

Incorrect: Click Here to see our menu. 

<span><a href=`oursite/menu`> Click Here</a></span>

This read as - `Link 'Click Here'` which does not communicate the link's purpose or destination. 

Correct: View our menu.

<a href=`oursite/menu`> View our menu </a>

This read as - `Link 'View our menu'` when navigating through available links on the page. 

Correct: If you want to get a better idea of what you want, you can view our menu here.

<span>If you want to get a better idea of what you want, you can <a href=`oursite/menu`> view our menu here</a></span>

This read as - `If you want to get a better idea of what you want, you can Link 'view our menu here'`.

If your link is embedded within an image, consider separating them from each other or using the alt text of the image to communicate the link's purpose/destination. 