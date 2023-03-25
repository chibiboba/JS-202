# Introduction

## What to Focus On

This lesson focuses on images and how Web pages use them. Nearly every page on the Web has at least one, and most have more; they help organizations and individuals present photographic-storytelling, logos, background designs, humorous "memes," and more. In this lesson, we'll learn about the different image types and talk about the roles they play in HTML documents.

Use the following guidelines to focus your study and practice as you move through this lesson:

### Image Types

- Understand the primary differences between jpg, png, and gif images.
- Explain when to use which image type.

### HTML and CSS for Images

- Add foreground and background images to a web page.
- Use figures and captions.
- Use images as links.

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# Image Types

## JPG

- The jpg format (pronounced "jay-peg") is the most common image format for images used in web documents.

When to use JPG

- They are suitable for photographs, drawings, diagrams and more. 
- Almost all graphics programs can create jpgs, and most digital cameras today can produce them straight out of the camera, which lets you upload photos straight to the web.
- Use JPG for reducing image size (compression) but still retaining decent image quality. 
  - Manually adjust the amount of compression and lossiness to balance compression and image quality(in loss of detail or visible artifacts). 

When not to use JPG

- In general, jpgs don't work well as CSS background images. Photographs are too intricate visually for use as a background, and most suitable non-photographic graphics show visible results of compression even at the highest quality.
- There are JPEG artifacts even when a JPG image is not edited, but most people don't notice this. 
- JPG format does not allow for transparency.

Lossy compression

- Jpgs provide an exceptional balance of image quality and compression. **Compression** encodes the file in a way that reduces its size.

- Jpgs use a **lossy** form of compression; they lose information in exchange for a file size reduction. In some cases, you can compress an image down to 10% of its original size or less. However, lossiness sacrifices quality in return for compression.

Losing detail with each edit 

- If you edit a jpg (even without compressing), the resulting file has less detail than the original. If you update the file again, the result loses more detail. If you repeat this process often enough, you can end up with an image that you no longer recognize. 
- Even if you never edit a jpg file, you can see some **JPEG artifacts** on close examination. However, most people don't notice these on well-handled jpgs, so they work well with most photographs.

Set the amount of compression and lossiness

- You can set the amount of compression and associated lossiness when you save a jpg file. 
- Low lossiness levels lead to better image quality but larger files; likewise, high lossiness yields lower image quality but smaller files. 
- As a rule of thumb, you should aim to reduce the size of the Jpg as much as possible without losing noticeable detail or introducing visible artifacts, which requires experimentation for every image.

## PNG

When to use PNG

- The png format is often the best choice for backgrounds and non-photographic images.
- Pngs are ideal for images that need all their detail, transparency, or that must support more than 16.7 million colors.

When not to use PNG

- PNG size is medium-large, too big for photographs. 

Non-lossy compression

- Like jpgs, pngs use compression to reduce the size of the file, but png compression is non-lossy. **Non-lossy** means that information and details are not lost during compression. 
- However, the lack of lossiness means larger file sizes; considerably in some cases.
- PNG format does not offer as much compression as JPG format, so PNG images are typically much larger than a similar JPG image.

Single color and alpha transparency

- Pngs also provide both single-color and alpha transparency, which lets you see the background behind an image while still viewing the image's main subject. This feature is useful with logos, icons, and line drawings. 
- Single-color transparency allows part of an image to be entirely clear by reserving a single color - any pixel that matches that color in the png reveals the content (typically a background color) behind the image. 
- Alpha transparency adds an alpha channel to images, which allows up to 65,536 different levels of transparency tinted by color.

## GIF

When to use Gifs

- Gifs are suitable for small images used as user interface icons in an application. 
- They have a limited color range (256 colors), on of which can be transparent. 
- This allows for minuscule file sizes, which makes them perfect for images where size, detail, and a broad color palette aren't significant.

When not to use Gifs

- Gifs have a limited color range (256 colors). They also lack detail and are not good for larger sizing.

## Image Type Comparison Table

You don't have to memorize this table.

| **Feature**          | **JPG**       | **PNG**              | **GIF**                |
| :------------------- | :------------ | :------------------- | :--------------------- |
| Compression          | Lossy         | Non-lossy            | None/Lossy/Non-lossy   |
| Photographs?         | Yes           | Yes, but too big     | No                     |
| Line Drawings?       | No            | Yes                  | Depends on drawing     |
| Gradients?           | No            | Yes                  | No                     |
| Typical File Size    | Small         | Medium-Large         | Tiny                   |
| Quality              | Poor to Good  | Best                 | Good but limited color |
| Color Palette        | 16.7 million  | 256 TC (note 1)      | 256                    |
| Color Depth          | 24 bits       | 8-48 bits            | 8 bits                 |
| 1-Color Transparency | No            | Yes                  | Yes                    |
| alpha Transparency   | No            | Yes                  | No                     |
| Resolution Maximum   | 65536 x 65536 | 2 GP x 2 GP (note 2) | 65536 x 65536          |
| Total Pixels Max     | 4 GP          | 256 EP (note 3)      | 4 GP                   |

Note 1) 256 **teracolors**, an astonishing 280 million **million** colors.
Note 2) **GP** refers to **gigapixels**
Note 3) 256 **exapixels**, an incredibly large number: 3 followed by 23 zeros.

# Adding Images to Web Pages

## The Img Element

- `<img>` is a self-closing tag that tells the browser to load and display a **foreground image** from a separate resource. It has four attributes of particular interest.

- Here's a typical image tag:

  ```html
  <img src="lucrezia.jpg" alt="Da Vinci's Smarter Sister, Lucrezia"
       width="800" height="600">
  ```


#### The `src` attribute

- The `src` attribute is required.

- The `src` attribute tells the browser where to find the image. 
  - It uses the same URL format as links in the `<a>` tag and can be relative, root-relative, or absolute.
  - **Relative paths** are specified relative to the current directory or location of the file being referenced. For example if the current directory is  `/home/user/documents` use "../pictures/image.jpg" to specify the file's location. 
  - **Root-relative** paths are specified relative to the root directory of the file system. In Unix-based systems, the root directory is denoted by a forward slash (/). "/home/user/pictures/image.jpg".
  - **Absolute paths** specify the complete path to a file or directory from the root of the file system. "/home/user/documents/pictures/image.jpg"

#### The `alt` attribute

- The `alt` attribute is optional but you should almost always use it. Existing W3C standards require the `alt` attribute in *almost* all cases. 

- The `alt` attribute describes the content of the image as an aid for users who cannot see it or that have images disabled. 

- Most browsers display the `alt` text when an image is unavailable or when images have been disabled. 

Why you shouldn't omit `alt` 

- Screen readers, specialized browsers that read web pages aloud for people with vision problems, use the `alt` attribute to tell the user about image content. Without `alt`, the user has no idea what the image shows. 
- Readers with vision problems may not even know it is present: some reader software treats images with no `alt` text as non-essential, so they skip over them while reading the screen.
- Search engines use `alt` to index images, which makes it relevant for search engine optimization (SEO).

Empty `alt` or omit `alt` 

- If you omit the `alt` attribute, your browser can still render the image. 
  - Existing standards require the `alt` attribute *in most cases* to provide text that the browser can display when the image is unavailable. 
  - Your HTML won't validate on the W3C validator unless you use the `alt` attribute. 
- If your image isn't significant enough to require an `alt` attribute, you can specify an empty value with `alt=""`. 
  - (There are some specific exceptions to this rule, but you should ignore them for this course.)

#### `width` and `height` attributes

- The `width` and `height` attributes are also optional. 
- They provide the width and height of the image in pixels. The CSS `width` and `height` properties override the HTML attributes in the rendered version of the page.
- When to use `height` and `weight` attributes
  - These attributes are only recommended in specific cases. For example:
  - If you plan to almost always display images with a specific width and height, then you should use the attributes to specify those values. That lets your browser optimize the rendering speed by allocating room for your image before it finishes downloading.
- Use the `height` and `width` CSS *properties* exclusively. 
  - In many cases you won't know the specific width and height in advance, especially if the image's size is dependent on the output device. 
  - For instance, mobile devices often render images at a smaller size than in a desktop browser. In such cases, providing the `height` and `width` attributes may lead to worse overall performance. 

## Figure and Figcaption

Problem: How to semantically add a caption?

- If we want a caption for an image, we can add a paragraph element below it. However, there's no way to show the relationship between the `img` and `p` elements. 
- We could group them in something like a `div`, but `div` has no semantic meaning and fails to establish a meaningful connection.

`figure` has semantic meaning

- You should use the `<figure>` element to wrap images that you refer to in the text.
  - The `figure` element fills this gap in semantic meaning; it designates an item as a representation of information discussed in the content. 
  - The tag customarily encloses some media, such as an image, video, or audio file, that illustrates the surrounding content. 

- Use `<figcaption>` to caption an image, which is short for "figure caption." 
  - For example:

```html
<figure>
  <img src="masthead.jpg" alt="Sunset over the forest">
  <figcaption>The sun sets over the dense forest</figcaption>
</figure>
```

`figure` and `figcaption` not always needed

- If you don't reference the media in the text and you don't need a caption, then you don't need a `figure` tag. 
- Likewise, if you don't need a caption, you don't need a `<figcaption>` tag. Logos, fancy bullets, background images, and the like are mere decoration, not content. They don't need a `figure` or a `figcaption` element.

## Images as Links

- You can use any non-interactive HTML element as a link, including images. (The non-interactive requirement excludes form controls and other links). 
- Make images as links to give users the ability to see them full-sized by clicking on them
- To make an image clickable and have it link to another page, place the `img` tag inside an `a` tag:

```html
<a href="url-of-link" target="_blank">
  <img src="url-of-image" alt="alt-text">
</a>
```

- `url-of-link` is the destination for the link. 
- `url-of-image` is the location of the image. 
- The URLs are typically different, but they don't have to be. If they're the same, the link acts as a way to see the image all by itself. 
- Often, this single image is larger than the original. Some browsers let you click the stand-alone picture to toggle between viewing it "actual size" or "fit-to-screen."

## Background Images

- Background images appear behind the content for the element that requested the background and its descendants.
- You can  add background images to a page or element by applying the CSS `background` or `background-image` property.  
- The `<image>` data type can be represented with any of the following:
  - An image denoted by the [`url()`](https://developer.mozilla.org/en-US/docs/Web/CSS/url) data type
  - `<gradient>` data type
  - A part of the webpage, defined by the [`element()`](https://developer.mozilla.org/en-US/docs/Web/CSS/element) function
  - An image, image fragment or solid patch of color, defined by the [`image()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image/image) function
  - A blending of two or more images defined by the [`cross-fade()`](https://developer.mozilla.org/en-US/docs/Web/CSS/cross-fade) function.
  - A selection of images chosen based on resolution defined by the [`image-set()`](https://developer.mozilla.org/en-US/docs/Web/CSS/image/image-set) function.
- Most background images apply to an entire page, so we use the `body` selector to specify them. However, you can apply backgrounds to any selector, such as a tag, class, or id selector. For instance:

```html
<section>
  Sint duis dolor consectetur ad nostrud sint. Occaecat reprehenderit officia ex
  duis velit veniam magna labore.
</section>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Work</a></li>
    <li><a href="#">Play</a></li>
  </ul>
</nav>
```

```css
html {
  font-size: 32px;
}

body {
  background-image:
    url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/gradient-			background.png");
}

section {
  display: inline-block;
  width: 500px;
}

nav {
  background-image:
    url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/blurry.png");
  display: inline-block;
  height: 200px;
  width: 250px;
}
```



![Background image](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/adding-images-to-web-pages-01.png)



There are several other background properties you can provide with a background image, including the size of the image, the positioning, and repeat counts. Here, we demonstrate setting the size of the background image to 25% of the container width.

```css
body {
  background-size: 25%;
}
```



![Sized background image](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/adding-images-to-web-pages-02.png)

# Practice Problems: Images and Figures

These practice problems use [this image](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg) which you can download to your system or use directly from its current location, `https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg`.

1. Write HTML to display the image. Don't use a `<figure>` or `<figcaption>` right now.

   Solution

   ```html
<img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
        alt="Two Cats: Butterscotch and Pudding">
   ```
   
   Did you remember to specify the `alt` attribute?

2. Use CSS to set the width of the image to 250 pixels.

   ```css
img {
     width: 250px;
   }
   ```
   
   Since we specified a width but no height, the height adjusted automatically to maintain the same aspect ratio.

3. Update the CSS width from the previous problem with a height of 350 pixels.

   Solution

   ```css
img {
     height: 350px;
   }
   ```
   
   Since we specified a height but no width, the width adjusted automatically to maintain the same [aspect ratio](https://en.wikipedia.org/wiki/Aspect_ratio_(image)).

4. Set the width of the image to 400 pixels, but keep the height at 350px.

   Solution

   ```css
img {
     height: 350px;
     width: 400px;
   }
   ```
   
   You should see that the photo is now horizontally stretched since we've taken control of both the height and width. We control the horizontal; we control the vertical. You are about to experience the awe and mystery which reaches from the inner mind to – Launch School.

5. Remove the CSS for the `img` element, and wrap the `<img>` in a `<figure>` tag with a yellow background.

   Solution

   Copy Code

   ```html
   <figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
          alt="Two Cats: Butterscotch and Pudding">
   </figure>
   ```

   ```css
/*
   img {
     height: 350px;
     width: 400px;
   }
   */
   
   figure {
     background-color: yellow;
   }
   ```
   
   You should see that the background color stretches most of the way across the window since `<figure>` is a `block` element.

6. Add a caption below the image.

   Solution

   ```html
   <figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
          alt="Two Cats: Butterscotch and Pudding">
     <figcaption>
       Butterscotch and Pudding held still long enough for me to capture this
       picture of both of them.
     </figcaption>
   </figure>
   ```
   
7. Move the caption above the image.

   Solution

   ```html
   <figure>
     <figcaption>
       Butterscotch and Pudding held still long enough for me to capture this
       picture of both of them.
     </figcaption>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
          alt="Two Cats: Butterscotch and Pudding">
   </figure>
   ```

# Guided Project: A Simple Photo Gallery

With what you've learned so far, you should now be able to construct a simple photo gallery. We'll get you started by creating a simple gallery of 5 images of varying sizes. We'll display the images one per line, with each image left-justified, and with a caption beneath each.

For this project, you can use any images you want. For the best results, try to choose a variety of different image widths, including at least one that is too big to fit horizontally in your usual browser window.

If you want, you can use these images instead:

- https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/1.jpg
- https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/2.jpg
- https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/3.jpg
- https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/4.jpg
- https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/5.jpg

Here's the body of our HTML:

Copy Code

```html
<main>
  <figure>
    <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/1.jpg"
         alt="Transit Shadows">
    <figcaption>Transit Shadows</figcaption>
  </figure>

  <figure>
    <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/2.jpg"
         alt="Missy Chaplin">
    <figcaption>Missy Chaplin</figcaption>
  </figure>

  <figure>
    <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/3.jpg"
         alt="Blue Angels in Formation">
    <figcaption>Blue Angels in Formation</figcaption>
  </figure>

  <figure>
    <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/4.jpg"
         alt="Orange Rose">
    <figcaption>Orange Rose</figcaption>
  </figure>

  <figure>
    <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/5.jpg"
         alt="Kentucky Darleks">
    <figcaption>Kentucky Darleks</figcaption>
  </figure>
</main>
```

We'll zero out the margins and padding for all these elements to ensure that the appearance remains similar in different browsers:

Copy Code

```css
body, main, figure, figcaption, img {
  margin: 0;
  padding: 0;
}
```

We call this type of margin/padding zeroing a reset; we'll discuss it in more detail later. For now, all you need to know is that it provides some assurance that different browsers won't display different results.

We're using the `main` element as a master "container" element for the entire photo gallery. It provides some semantic meaning for the document as it identifies the primary content area.

Now, let's walk through some additional styling to finish the gallery. Our goal is to end up with the five pictures arranged in a 3 row by 2 column grid, with the final grid element empty. All images should have the same width and should fit horizontally within the browser window. We'll let you do most of the work.

1. After loading the page, you may notice that the images are vertically too near each other, and they're flush with the top and left edges of the window. Adjust the spacing between the `figure` elements and the distance between the left and right edges of the browser window to `50px` to give the images some breathing room.

   Solution

   Copy Code

   ```css
   figure {
     margin: 50px;
     outline: 1px solid red;
   }
   ```

   In a previous lesson, we discussed the rule of thumb that one should use margins instead of padding to adjust the space between adjacent elements. Since we're dealing with spacing here, we elected to use margins. It's possible to use padding instead, as we'll see later, but we'll stick to the rule of thumb for now.

   We used the `outline` property to temporarily draw rectangles around each figure to help you see how the elements line up. Outlines are like borders, but they lie outside them. More importantly, they don't interact with the box model, so they don't change the page layout. This feature makes them useful during development and debugging.

   Look at the outline around the figure that contains the widest image. Depending on your browser window's width, the image may extend beyond the right side of the outline. This odd effect occurs for two reasons:

   - The displayed width of an image that doesn't have the `width` property or the deprecated `width` attribute is the original width of the image. That can be wider than the container in which the image resides.
   - In this case, the container element is a `figure` element. The default width for `figure` is `100%`, which, in this case, represents 100% of the browser window (minus the margins). If the image width exceeds the width of the `figure`, the image will extend beyond the right side of the outline.

2. Reduce your browser window's width, if necessary, until at least one image exceeds the window width. Next, adjust the CSS to make them all fit inside the window. Don't forget that there is a margin around each figure, which should be evident when you display the page.

   Once you're done, check what happens as you expand and shrink the browser window; no matter what adjustments you make, all images should fit in the window.

   Solution

   Copy Code

   ```css
   img {
     max-width: 100%;
   }
   ```

   By reducing the maximum size, all of the images now fit entirely inside their figure outlines.

3. Every image should use the entire width of the `figure` elements. Modify your CSS to implement this requirement.

   Solution

   Copy Code

   ```css
   img {
     /* max-width: 100%; delete this line */
     width: 100%;
   }
   ```

4. Reduce the width of each `figure` to 1/2 the width of the browser window:

   Solution

   ```css
   figure {
     width: 50%;
   }
   ```
   
5. At this point, the figures are narrow enough that we should be able to squeeze 2 of them in every row on the page. However, since `figure`s are `block` elements, they always take up an entire row. Instead, you must convert the `figure` elements to `inline-block`. Please do so.

   Solution

   ```css
figure {
     display: inline-block;
   }
   ```
   
   Even though we converted the box model to `inline-block`, the images still don't fit side by side. There's a problem - actually, two problems. Can you see what's wrong? Try to determine what you need to do before continuing. We'll return to this issue after an unrelated question.

6. There's a small cosmetic issue unrelated to squeezing two images per row. Let's center the captions beneath each image:

   Solution

   ```css
   figcaption {
     text-align: center;
   }
   ```
   
7. Returning to the problem of squeezing two images per row, the main issue we have is that we have margins to the left and right of each `figure`. Recall that we used margins here to satisfy our rule of thumb about choosing margins or padding. However, those margins take up space in the browser window, so we can't squeeze two 50%-width elements side by side. Instead, we need to set the left and right margins on the `figure` elements to `0`, and redistribute that space in some other way. Give this a try now.

   Hint

   You probably won't be able to get the images to fit yet with this adjustment, so don't get too wrapped up trying to figure out why your code doesn't work.

   Solution

   ```css
figure {
     box-sizing: border-box;
     margin: 50px 0;
     padding: 0 50px;
   }
   ```
   
   We need to set the top and bottom margins to 50px and set the left and right padding values to 50px as well. Lastly, we need to set the box-sizing model to `border-box` to ensure the width includes the padding.

8. The other part of the problem of squeezing two images per row is that there is a small amount of whitespace between every pair of `inline-block` elements. It's not much whitespace, but it's enough to prevent two 50% elements from fitting side by side. Go ahead and make the necessary adjustments to get rid of the whitespace.

   Hint for Solution #1

   You've seen this issue before, back in the previous lesson. You may want to review [this article](https://css-tricks.com/fighting-the-space-between-inline-block-elements/) if you don't remember how to eliminate the whitespace.

   Solution #1

   ```html
   <figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/1.jpg"
          alt="Transit Shadows">
     <figcaption>Transit Shadows</figcaption>
   </figure><figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/2.jpg"
          alt="Missy Chaplin">
     <figcaption>Missy Chaplin</figcaption>
   </figure><figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/3.jpg"
          alt="Blue Angels in Formation">
     <figcaption>Blue Angels in Formation</figcaption>
   </figure><figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/4.jpg"
          alt="Orange Rose">
     <figcaption>Orange Rose</figcaption>
   </figure><figure>
     <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/5.jpg"
          alt="Kentucky Darleks">
     <figcaption>Kentucky Darleks</figcaption>
   </figure>
   ```
   
   In one of our earlier encounters with this issue, we inserted comments between each of the elements. We use a slightly different technique here: we place the opening tag of each `figure` adjacent to the closing tag of the previous `figure`. It has the same effect.

   Hint for Solution #2

   Another way to get rid of the space between `figure` elements is to reduce the font size of that space to 0.

   Solution #2

   ```css
   main {
     font-size: 0;
   }
   
   figcaption {
     font-size: 1rem;
   }
   ```
   
   By reducing the font size for the `main` element to 0 (we don't have any other text in this element), the space character shrinks into nothingness. However, we must remember to restore the font before we display anything, such as the caption.
   
9. The images are a bit on the small side. Let's give the user the ability to see them full-sized by clicking on them. When clicked, the browser should load the image directly into a new tab or window. To accomplish this, convert your images into links.

   Solution

   Copy Code

   ```html
   <figure>
     <a href="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/1.jpg"
        target="_blank">
       <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/1.jpg"
            alt="Transit Shadows">
     </a>
     <figcaption>Transit Shadows</figcaption>
   </figure><figure>
     <a href="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/2.jpg"
        target="_blank">
       <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/2.jpg"
            alt="Missy Chaplin">
     </a>
     <figcaption>Missy Chaplin</figcaption>
   </figure><figure>
     <a href="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/3.jpg"
         target="_blank">
       <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/3.jpg"
       alt="Blue Angels in Formation">
     </a>
     <figcaption>Blue Angels in Formation</figcaption>
   </figure><figure>
     <a href="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/4.jpg"
         target="_blank">
       <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/4.jpg"
       alt="Orange Rose">
     </a>
     <figcaption>Orange Rose</figcaption>
   </figure><figure>
     <a href="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/5.jpg"
        target="_blank">
       <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/photo-gallery/5.jpg"
       alt="Kentucky Darleks">
     </a>
     <figcaption>Kentucky Darleks</figcaption>
   </figure>
   ```

10. You can now get rid of the outline you attached to the `figure` elements, and assign a pleasant background to the gallery. You can use the background image we used earlier in this lesson (`https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/gradient-background.png`) or one of your own.

    Solution

    Copy Code

    ```css
    body {
      background-image: url(https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/gradient-background.png);
      background-size: cover;
    }
    
    figure {
      /* outline: 1px solid red; delete this line */
    }
    ```

    Adjust the browser window, making it as big as possible and as small as possible, and a variety of sizes in between, to see how it responds.

    See if you can determine why we used `background-size: cover;`.

That should do the trick; you now have a simple image gallery that uses most of what we've learned about HTML and CSS thus far.

[Completed Project](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_3/first_photo_gallery/gallery.html)

The completed project shows an incorrect caption on the photo of the aircraft formation; that is the Blue Angels, not the Thunderbirds.

Use the "View Source" feature in your browser to see the final HTML and CSS.

# How to adjust image 

- Aspect ratio automatic adjustment

  - If you specify a fixed dimension for one side and don't specify for another side, then the other side will adjust automatically to maintain the same aspect ratio. 

- Interaction with mixing units

  - Using fixed dimension for one side and a relative variable dimension for another side will cause the image to stretch weirdly when browser is resized. 

  - For example, a fixed height and a width of 100% will cause the image to stretch horizontally but remain fixed vertically. 

    ```css
    img {
      display: block;
      height: 533px;
      margin: 0 auto;
      max-width: 800px;
      width: 100%;
    }
    ```

- **zeroing a reset**

  - Zero out the margins and paddings for all elements to ensure that the appearance remains similar in different browsers.

  ```css
  body, main, figure, figcaption, img {
    margin: 0;
    padding: 0;
  }
  ```

- Use`outline` to outline the border of an element. 

  - `outline` is a line outside the element's border. It doesn't interact with the box mode and doesn't take up space, so it doesn't change the page layout.
  - This makes `outline` useful during development and debugging.

- An image may extend beyond the right side of the outline. (from photo gallery project)

  - If an image doesn't have the `width` property or deprecated `width` attribute, then the web browser will use original width of the image as the default displayed width. That means the image may be wider than the container its placed in, resulting in the image being hidden or overflowing outside the container.
  - In this case, the container element is a `figure` element. The default width for `figure` is `100%`, which in this case represents 100% of the browser window (minus the margins). If the width exceeds the width of the `figure`, the image will extend beyond the right side of the outline.

- Size of containers & child element

  - The `body` master container is usually 100% of the browser window (minus the margins).
  - `main` is the master container which inherits from `body`. 
  - Whatever inherits from `main` may be more wide than `main`, so adjust the `max-width` to 100%. 
  - If you want the child element to fit fully in container, adjust `width` to 100%. 

- How to make two block elements fit side by side in browser.

  - Convert block element to `inline-block`
  - Change width of element to percentage like 50%. 
  - Change box-sizing to `border-box`. 
  - Make left and right margin 0. 
  - If you want left and right margin then use `padding` instead because `padding` is included in the content for `border-box`. 
  - Remove Whitespace: Adjust code to remove whitespace by placing closing tag next to next `inline-block`element's opening tag.

  ```css
  figure {
  	display: inline-block;
    box-sizing: border-box;
    margin: 50px 0;
    padding: 0 50px;
    outline: 1px solid red;
   	width: 50%;
  }
  ```

- Use `text-align:center` to center an element's `inline` content within the width the `block` element.

- Add `background-image` and stretch the picture using `background-size: cover`

- Use the "View Source" feature in your browser to see the final HTML and CSS.

# Summary

For such an important topic, this lesson was curiously brief. However, while you didn't learn everything there is to know about images, you learned enough to do almost everything you need to know. It's possible that you will never need to learn more than we present here unless Web technology sees a significant change in how it deals with images.

In this lesson, we discussed using images on Web pages, and, in particular, the three main types of images found on the Web (jpg, png, and gif). We learned how to use them as both foreground and background images, and we saw how CSS interacts with them. We also learned a crucial lesson; nearly anything can be a link on a web page. Specifically, we learned how to use images as links.

If you want to know more, here are some suggested topics for further research:

- The technical aspects of images: color depth, image size, compression, etc.
- Background images: positioning and sizing, gradients

Since web content changes so often, we'll leave you to use Google to find suitable web pages for reading. Suggestion: start with MDN.

In the next lesson, we'll take a look at two more vital web page components: lists and tables.