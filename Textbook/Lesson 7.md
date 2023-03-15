# Introduction

This final lesson discusses the process of converting a design to a finished web page. We also cover CSS resets and watch a video that may help you improve your HTML and CSS by using semantic markup and roles.

## What to Focus On

The most important part of this lesson is how to use a PSD or PNG design file as the basis for converting a design to an actual web page. For our purposes at Launch School, it doesn't matter if you use a PSD or PNG file. PSD files require Adobe Photoshop or a strongly compatible alternative program; they give you a lot of power and flexibility in copying a design. However, you can also use PNG files with a technique called "blink comparison" to copy the design.

# CSS Resets

Before we get into the meat of this lesson, let's learn a bit about CSS resets. We've seen them once or twice before, albeit briefly.

Now that you've worked on a bunch of web pages yourself, you've seen that the browser provides some styles for every web page. If you create an HTML file with text wrapped in various elements, the browser will assign default styles as needed to make the page a bit more readable than a blob of text. These default styles are great when you have no CSS; they help ensure that the page looks presentable. When you use CSS to style your documents, though, you probably don't want the browser to interfere with that process. Since different browsers have different default styling, your page may degrade -- or worse, break entirely -- when someone uses it in a browser that you didn't test.

A reset is a bit of CSS that "resets" your CSS to a known state in a variety of different browsers. Thus, your favorite browser renders your web page in the same way that other browsers do. Resets do this by removing or overriding most browser styling defaults; for instance, they set a default font, zero out margins and padding, and eliminate browser-specific styling on input controls. These actions give you a fresh start from which to work and leave you free to add the styles you need without worrying about unexpected results in other browsers.

One crucial area where resets play a significant role are with margins and padding, which often have arbitrary values that vary between browsers. The defaults sometimes use both padding and margins which can lead to problems when deciding which you should use for a given element. As a result, most resets set the margins and padding for most elements to `0` which helps simplify adding your own.

Resets are indispensable. Without them, you end up playing that not-so-fun Whac-A-Mole game that we met in Lesson 2's Introduction. The "game" is now cross-browser, though: you have a page that looks great in Chrome, but less than stellar in Firefox. You fix the look in Firefox, but now Chrome looks strange. After several iterations, you get the page looking nearly identical in both browsers, and that's when you try it in one of Microsoft's browsers. No one will blame you if you abruptly decide to take a vacation. Using a CSS reset doesn't guarantee that you won't experience cross-browser issues, but it does help minimize them.

While there are plenty of resets available, most developers choose one of these popular files:

- [Eric Meyer's reset](http://meyerweb.com/eric/tools/css/reset/)
- [Normalize.css](http://necolas.github.io/normalize.css/)
- [Tantek Celik's whitespace reset](http://cssreset.com/scripts/undohtml-css-tantek-celik/).

The resets vary in aggressiveness, and it's probable that you'll end up with a reset that you like, except for one or two problems. People often customize the reset they use, as we do at Launch School: we use a custom version of Tantek Celik's reset. It's a simple one:

Copy Code

```css
/*
----------------------------------------
Tantek Celik's Whitespace Reset
     Author:    Tantek Celik, Shane Riley
    Version:    (CC) 2010 Some Rights Reserved - http://creativecommons.org/licenses/by/2.0
Description:  Resets default styling of browsers to a common base
----------------------------------------
*/

ul, ol { list-style: none; }
h1, h2, h3, h4, h5, h6, pre, code { font-size: 1em; }
ul, ol, li, h1, h2, h3, h4, h5, h6, pre, form, body, html, p, blockquote,
fieldset, input, dl, dt, dd, figure, figcaption {
  margin: 0;
  padding: 0;
}
a img, :link img, :visited img, fieldset { border: none; }
address { font-style: normal; }
header, section, article, nav, footer, hgroup, details, summary, figure, main {
  display: block;
}
mark {
  color: inherit;
  background-color: transparent;
}
abbr { border: none; }
summary::-webkit-details-marker { display: none; }
```

As you can see, there's not much to it. This reset:

- removes the bullets on ordered and unordered lists.
- sets all headings and a few other items to use the same font size.
- sets the padding and margins on most `block` elements to 0.
- removes the border that surrounds images inside links on older browsers.
- removes the border on `fieldset`.
- converts `address` elements to look like regular text.
- sets newer HTML elements to `display: block`, in case the user has an old browser that defaults to `inline`.
- removes garish colors from the `mark` element.
- removes the bottom border from `abbr` elements.
- removes the toggle marker from the `summary` element.

You may never use some of the elements in this reset, but if you do, you'll know they won't look different in other browsers.

# Working With Design Files

## Photoshop and Design Files

When you first start writing HTML and CSS for a real-world project, a designer will probably give you a **design file** (it's possible that you may be the designer): a mockup of the finished project pages. The design file is almost always a Photoshop document, a PSD file, which is a multi-layered image that contains layers for each part of the design: images, shapes, text, etc. You're expected to use the design file to create your image and background assets as well as obtain information regarding padding, margins, font-size, and color. Knowing your way around Photoshop well enough to extract this information will help you get work as a front-end developer.

We'd love to teach you how to use these Photoshop design files, but there's a problem: you need to know how to use Photoshop reasonably well to pry apart a design file and extract all the information you need, and that requires time and practice. Adobe, the developers of Photoshop, used to offer a 30-day trial that was sufficient to learn the program well enough to be useful; the current 7-day trial period is not enough time.

Furthermore, we're not churning out front-end developers at Launch School. We're training engineers. As such, employers are less interested in whether you know how to use Photoshop. It's a plus, but not a job requirement in most cases.

That said, we do have some videos that we include in this assignment and the next that shows the instructor using Photoshop and a design file. We will also provide you the design file in some of the upcoming projects; if you have access to Photoshop, we urge you to try using it in these projects.

If you plan to use Photoshop yourself, you need to know how to:

- Use the layers palette to view the different layers in an image. You can turn layers on and off using the eyeball icon.
- Use the toolbar (the thin vertical or horizontal palette) that provides access to most of Photoshop's tools.
- Extract assets from their layers.
- Use the Move tool to move layers around.
- Use the Marquee tool to extract and measure images and shapes.
- Export images.
- Use the Text tool to determine font characteristics.
- Use the Eyedropper tool to measure colors.

Adobe has a massive library of resources for learning to use all the different features of Photoshop. If you're not familiar with the program already, feel free to search their site when you need information.

There are alternatives to Photoshop that can read and process PSD files, but we haven't yet determined whether any of these programs do everything needed to examine design files usefully. Most are not free. Some programs provide the ability to read layered PSD files, but they may lack the functionality you need to extract information from those layers.

Here are a few alternatives that may do the job.

- [Photopea](https://www.photopea.com/) is a free online alternative to Photoshop that some of our students recommend. The support for Launch School project files appears to be excellent; we've had no reports of problems working on the projects in this course.
- [Affinity Photo](https://affinity.serif.com/en-us/photo/) Serif claims that Affinity can access PSD file layers, but with some limitations. The chief lack appears to be support for "smart objects," which you may need with some design files. A 10 day trial period may be available.
- [Photoshop Elements](https://www.adobe.com/) Adobe claims that Photoshop Elements can access PSD files, but with some limitations. It doesn't go into detail, though. A 30 trial period may be available.
- [GIMP](https://www.gimp.org/) As with Affinity Photo, GIMP can read PSD files with some limits, but it is also free. Note that we know that GIMP doesn't work with the Company Site project later in this lesson, but it seems to work well with the other projects provided that you use "Open as Layers" to open the files.
- [Adobe Creative Assets](https://assets.adobe.com/) This free online tool supplied by Adobe lets you look at PSD file layers, measure distances and colors, and extract resources such as images. It works somewhat differently from Photoshop and other tools, but it can be a useful alternative to purchasing Photoshop or using one of the above tools.

If you find one of these programs or another application useful, or find that one doesn't work, let us know!

## PNG Design Files

In the absence of Photoshop, we will provide you with a design file that we've collapsed down to a PNG format. PNG files aren't the best tool for the job, but they work well enough for your Launch School projects.

There are several problems with using PNG files for design:

- There is no way to examine and measure fonts.
- It is hard to measure colors when the color patch is less than 5-10 pixels thick, such as line drawings and text.
- Extracting images is tedious. If it has curved, jagged, or fuzzy edges, obtaining a clean result may be almost impossible. We'll avoid this by providing you with the images that you need.

To use PNG design files, you'll need tools that:

- open and view PNG files at the intended screen size
- measure sizes, padding, and margins
- measure colors

The macOS program, Preview, displays PNG files. Use View, Actual Size to view the image at its actual size. Drag out rectangular marquees to measure a component. However, there is no way to measure colors.

On a Mac, Digital Color Meter (found under Applications, Utilities) can help measure colors. Select View, Display Values, as Hexadecimal to display color values in hex, and use Display in sRGB on the drop-down list. You can use Shift-Cmd-C to copy the color under the cursor to the cut-and-paste buffer as a hex value suitable for use in your CSS.

Depending on your browser and display, you may find that text in PNG files looks blurry in your browser. This is an unfortunate side effect of the difference between physical and CSS pixels. See the assignment on Dimensions in The Box Model lesson for a discussion of these two types of pixel measurements.

### Blink Comparisons

The lack of font measurements and the difficulty of measuring small items makes PNG files an inadequate substitute for a PSD file. Using Preview and Digital Color Meter will get you most of the way, but, sooner or later, you must perform a **blink comparison**.

1. Create an HTML file that does nothing more than load the PNG design file:

   Copy Code

   ```html
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="utf-8">
       <title>Design File</title>
       <style>
         body, img {
           margin: 0;
           padding: 0;
         }
       </style>
     </head>
     <body>
       <img src="design-file.png" alt="design file">
     </body>
   </html>
   ```

2. Load the HTML in your browser.

3. Set the width and height of your browser as precisely as possible to match the width and height of the PNG file.

4. Create your HTML file and load it in a separate tab.

5. Toggle your browser tabs back and forth between the files (Ctrl-Tab and Shift-Ctrl-Tab work with most browsers).

6. Observe the differences between the design file and your file. Make corrections in your file.

7. Return to step 5 until your files match as well as possible.

The following short video illustrates what a blink comparison looks like in action:

<video id="video_8b6624b8f874_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/202/videos/lesson_7/blink.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/202/videos/lesson_7/blink.mp4)

From this short video, you can readily see that the white text area is the wrong size, the logo at the top of the page is in the wrong position, and the text colors aren't quite right. You would then go back to your HTML and CSS, make some adjustments, and try another comparison. This iterative approach will ultimately lead to a close replica of the desired design.

## HTML Design Files

At Launch School, we will sometimes ask you to duplicate a design based entirely on an existing web page. You could cheat and use View Source and the Inspector, but you won't learn much doing that. In fact, some web pages may leave you even more confused than trying to do it on your own.

Instead, you can perform a blink comparison. The process is identical to that described above except that you don't have to create an HTML file to display a PNG file; you have an existing page that you can view as-is in your browser.

## Pixel Perfection

No matter how you approach implementing your design files with HTML and CSS, you probably won't get a perfect duplicate. You want to strive for "pixel perfection", a pixel-for-pixel duplicate of the design file, but you won't always be able to do that. Most issues involve tiny discrepancies in spacing and sizing, as well as more noticeable variations in the fonts, notably with the [kerning](https://en.wikipedia.org/wiki/Kerning). Try to get your final project as close to the design as you can, but always be aware that some differences may linger no matter how much effort you put into the project.

# Walkthrough: Using A Photoshop Design File

In this walkthrough, we'll demonstrate how to build a photography blog starting with a Photoshop file provided by our designer. If you have Photoshop, you can [download the design files here](https://d3jtzah944tvom.cloudfront.net/lesson_2/photography_blog/site_design.psd).

Even if you don't have Photoshop or an acceptable alternative, you should watch this video. While using a PNG file is considerably different from using a PSD file, the general techniques of measuring components are still pertinent. If you don't have Photoshop but still want to work on this project, you can extract the image files you'll need from the [completed archive](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/photo_blog_final.zip).

Our walkthrough starts with cutting the image assets from the Photoshop file, then creating the HTML and CSS for the header.

If you have a copy of Photoshop and wish to follow along, you should know that every release of Photoshop is different. The styles change, the commands change, the dialogs change. You will almost certainly see differences between the instructor's copy of Photoshop and yours. Some differences may be so extreme that you will have to resort to Google or Adobe's help site.

The instructor's intent here is to show how to use Photoshop to measure fonts, sizes, and colors. He is not aiming for "pixel perfection" in replicating the design.

- At 01:26, the instructor clicks on the camera icon to show a rectangular box with draggable corners. If you don't get that rectangle, follow these instructions:
  - While in the Photoshop file, press `v` to select the Move tool, or click on the Move tool in the tool palette.
  - In the toolbar, click the "Auto-Select" and "Show Transform Controls" checkboxes.
  - Choose "Layer" from the "Auto-Select" drop-down.
  - Click on the camera icon again. This time you should see the rectangle and drag handles.
- At around 2:59, the instructor creates a new document that had the dimensions of the image. He then pastes the image into the new document.
- At 08:26, the instructor includes a `whitespaces-reset.css` file. This file is the CSS reset we showed in the "CSS Resets" assignment.

<video id="video_b23f0380189e_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/photo_blog_1_f9b15a_s1286/photo_blog_1_f9b15a_s1286.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/photo_blog_1_f9b15a_s1286/photo_blog_1_f9b15a_s1286.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/photo_blog_1_f9b15a_s1286/photo_blog_1_f9b15a_s1286.sbv)

Duration: **21:26**

The second video covers the remainder of the project concentrating on the content area.

<video id="video_7ef30e258266_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/photo_blog_2_7adb23_s746/photo_blog_2_7adb23_s746.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/photo_blog_2_7adb23_s746/photo_blog_2_7adb23_s746.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/photo_blog_2_7adb23_s746/photo_blog_2_7adb23_s746.sbv)

Duration: **12:26**

Here is a [completed archive of the project](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/photo_blog_final.zip). You can [preview it here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/photo_blog_final/index.html).

# On Your Own: Using a PNG Design File

In this project, we'll repeat the project demonstrated in the previous lesson. However, this time we're going to use a PNG file. You can download the PNG design file and its associated images [here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/photo_blog_png.zip).

Recall that the font is the Roboto Condensed font from [Google Fonts](https://fonts.google.com/specimen/Roboto+Condensed). See the first video from the Photoshop demonstration for information on how to install this font (the font segment begins at 09:00 into the video).

Ideally, you'll end up with a project that looks identical to the one supplied in the PNG file. In practice, you can expect some minor differences. Your goal is to get as close to the PNG file as you can; don't give up too soon.

Begin the project as you would any other project. When you're ready to begin coding, use the PNG file to measure the different box sizes, margins, padding, etc., as well as the colors you will need (don't forget the font colors). Get as much of the project done as possible before turning to a blink comparison.

Once you've got most of the project done, use a blink comparison to patch up the most visible issues.

You can compare your results against [our solution from the Photoshop demonstration](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/photo_blog_final/index.html). You may also request a Code Review. For the best results, ask some specific questions in your review; it will help us focus on the parts that matter to you.

# On Your Own: A Company Splash Page

You may notice different versions of the project in the videos on this page, as well as in the image that shows the structure of the `main` and `footer` areas. Don't worry about the pictured discrepancies; the downloaded design files show the design we want you to use.

In this project, you will take a simple design file and some image assets, and write the HTML and CSS you need to duplicate the design as well as you can. We provide you with both PSD and PNG design files, together with the image assets you will need. ([Download the zip file](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page.zip).)

If you have Photoshop or a workable alternative, we recommend that you try to create the final page using the PSD file. Otherwise, use the PNG file.

Watch our overview video to become more familiar with the project. Your job is to create the HTML and CSS to match the design.

<video id="video_8e6cb8c60387_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/overview_company_splash_page_2f6693_s55/overview_company_splash_page_2f6693_s55.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/overview_company_splash_page_2f6693_s55/overview_company_splash_page_2f6693_s55.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/overview_company_splash_page_2f6693_s55/overview_company_splash_page_2f6693_s55.sbv)

Duration: **0:55**

Make sure you choose the most appropriate semantic HTML elements when creating the markup. The logo is the primary heading of the site, even though it is an image element; it should be the site header. The white box contains your main content, with subheadings and paragraphs of text, while the gray area includes a list of social media icons used as a footer; each image is a link to the appropriate social media site. You can use `#` as the URL.

While coding, be sure to check your work using the W3C [HTML](https://validator.w3.org/#validate_by_input) and [CSS](https://jigsaw.w3.org/css-validator/#validate_by_input) validators.

Your completed page should look like [ours](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page_final/site.html). Compare your markup and styles and see how close you came.

## Guidelines

When you start a project that already has a design, the first thing you should do is determine the HTML you need to recreate the design. Identify the major components of the page: headers, footers, main content areas, sections, asides, navigation, headings, paragraphs, etc. Build an initial copy of the HTML without worrying about the styles; this will give you something to look at as you work on the design. Your concern at this point is using semantic HTML to ensure the document structure makes sense.

Once you've built the HTML, you can start working on the CSS. Most developers will start with the overall look: the page background, the default font, the colors used, and the general placement of components. If you use Flex or Grid, you want to determine what columns, rows, and grid you need, and what elements go where. Your goal is to build something that approximates the final look.

Once you have a page that looks similar, you can start worrying about the details like padding, margins, borders, positioning, etc.

On this page, the starry background is a background image. The downloaded file contains this image along with the logo and the social media icons. Since the background image will cover the entire page, you can add it to your `body` element selector.

We show the background image below. Notice that it is a small portion of the entire background. You need to set the image to repeat in both directions to ensure it fills the page.



![Stars background](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page_final/bg_body.gif)



Here is the logo and name:



![Company Logo and Name](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page_final/logo.png)



This asset contains the text since the font is unavailable in most browsers. Note that the asset uses transparency to reveal the background.



![Main Content Area](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page_final/main_content.png)



A white block encloses the rest of the page content - our `main` element - followed by the light gray block that contains our footer.

Use the character entity `•` to produce the bullets before and after the heading text.

This project uses the Avenir font family as the default font:

- The two main headings use Avenir Heavy.
- The blue heading uses Avenir Black.
- The text content uses Avenir Medium.

You can use these fonts if you have them on your system, or you can download and install a free look-alike font named Nunito (Google it). If you can't use the Avenir variants or Nunito, try Helvetica, Arial, and the browser's default sans-serif font instead; note, though, that using any font other than Avenir or Nunito will make your job more difficult when you try to match the exact appearance.

## Solution Video

<video id="video_6ef8ed7d596f_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/company_splash_page_dbd0c5_s1107/company_splash_page_dbd0c5_s1107.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/company_splash_page_dbd0c5_s1107/company_splash_page_dbd0c5_s1107.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/company_splash_page_dbd0c5_s1107/company_splash_page_dbd0c5_s1107.sbv)

Duration: **18:27**

You can see our [completed example here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page_final/site.html). We also have an [example that uses Flex](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/company_splash_page_final/site2.html) for the footer.

## Challenge

If you want an additional challenge, try changing the page layout to a variable width by using a combination of min-width and max-width CSS properties. As you resize the browser window, the content should adjust in width to match the minimum and maximum widths.

# Improving Your HTML and CSS

As you learn HTML and CSS, you will find it hard to determine what the best HTML and CSS is for any given scenario. It doesn't get any easier even after you realize that there is no "one true way" to achieve a result. Much of front-end development involves interpreting the information you wish to present and identifying common styles to make your CSS as concise as possible.

In this video, we will review a typical web page and identify several areas where we can improve it. In the end, we should have a web page that is more semantic and easier to extend.

[Link to jsbin](http://jsbin.com/muvonubube/1/edit?html,css,output)

<video id="video_3072d79e5946_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/improving_html_css_c2f3c2_s984/improving_html_css_c2f3c2_s984.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/improving_html_css_c2f3c2_s984/improving_html_css_c2f3c2_s984.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/improving_html_css_c2f3c2_s984/improving_html_css_c2f3c2_s984.sbv)

Duration: **16:24**

#### Why use the role attribute?

As a CSS selector, the role attribute loosens the coupling between your CSS and HTML. When you use something like `#header` or `body > header`, you have a case of tight coupling between your HTML and code; if you change the HTML, you probably need to change the CSS, and vice versa. When you use roles, you can use it to select any HTML node type. That means you can change the HTML or the CSS without changing the other, provided you don't change the role.

Here is a [useful Stack Overflow post](https://stackoverflow.com/questions/10403138/what-is-the-purpose-of-the-role-attribute-in-html/18664038#18664038) that talks about the purpose of the `role` attribute.

# On Your Own: Company Site

To date, our projects have been simple, single-page projects, but most websites have multiple pages and different layouts throughout those pages. We're going to build a more realistic site by turning design files for the Space Designs company into a nearly complete HTML and CSS web site.

Space Design wants us to upgrade their site from the single page we built in the previous lesson to a multi-page site with pages for projects and the team in addition to the homepage. Each page will have the same markup for the header and footer, but it will highlight the selected page in the navigation bar.

Start by [downloading the design files](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/spacedesign.zip); it contains the design files and the cutout images you'll need. You can obtain text copy from a site like [lipsum](http://lipsum.com/).

We've learned that GIMP does not handle the PSD design files for this project properly. There doesn't seem to be a good fix for this issue.

The design files use the `Avenir` font, a font not pre-installed on most systems. You can choose the font stack Avenir, Nunito, Helvetica, Arial, sans-serif. If you want, you can download Nunito for free.

Link the three pages together via the navigation links. Make sure you place a class on the nav item for the current page to make it visually distinct.

## Header and Navigation

In this part of the project, construct the header and navigation part of the company site.

### Solution Video

Remember: the video may differ from the written instructions and the completed example. The written instructions take precedence.

<video id="video_7d0b502fbd74_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_1_b6e703_s865/company_site_1_b6e703_s865.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_1_b6e703_s865/company_site_1_b6e703_s865.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/company_site_1_b6e703_s865/company_site_1_b6e703_s865.sbv)

Duration: **14:25**

## Home Page

In this part of the project, construct the `main` area and the `footer` for the homepage.

When you construct the footer, you will run into the problem of how to display the list of social media icons, all of which are in a single file named `icons_social-media.png`. We call resources like this **sprites**. Using sprites isn't hard, but we haven't shown you how to do it. Instead, try doing some research on your own. If you can't figure it out on your own, see the example below.

You don't have to memorize how to use sprites.

Using Sprites for the Icon List

Copy Code

```html
<footer>
  <ul>
    <li><a href="#" class="twitter">Twitter</a></li>
    <li><a href="#" class="facebook">Facebook</a></li>
    <li><a href="#" class="email">Email</a></li>
    <li><a href="#" class="instagram">Instagram</a></li>
  </ul>
</footer>
```

Copy Code

```css
footer ul {
  margin: 0;
  padding: 0;
}

footer li {
  display: inline-block;
  padding: 0 60px;
}

footer li a {
  background:
    transparent
    url("https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/spacedesign/images/icons_social-media.png")
    0 0 no-repeat;
  display: block;
  height: 46px;
  overflow: hidden;
  text-indent: -8685px;
  width: 46px;
}

footer li a.twitter {
  background-position: 0 0;
}

footer li a.facebook {
  background-position: 0 -46px;
}

footer li a.email {
  background-position: 0 -92px;
}

footer li a.instagram {
  background-position: 0 -138px;
}
```



![Using Sprites](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_7/using-sprites-01.png)



The instructor will cover this material in the next video.

Remember: the videos may differ from the written instructions and the completed example. The written instructions take precedence.

### Solution Video for Home Page

<video id="video_8b58052b91ea_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_2_5d2dba_s1085/company_site_2_5d2dba_s1085.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_2_5d2dba_s1085/company_site_2_5d2dba_s1085.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/company_site_2_5d2dba_s1085/company_site_2_5d2dba_s1085.sbv)

Duration: **18:05**

## Projects Page

In this part of the project, finish the projects page.

### Solution Video for Projects Page

<video id="video_0fb65631c56c_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_3_d8d1cc_s556/company_site_3_d8d1cc_s556.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_3_d8d1cc_s556/company_site_3_d8d1cc_s556.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/company_site_3_d8d1cc_s556/company_site_3_d8d1cc_s556.sbv)

Duration: **9:16**

## Team Page

In this part of the project, finish the team page.

### Solution Video for Team Page

<video id="video_c541fc998029_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_4_894f12_s504/company_site_4_894f12_s504.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/company_site_4_894f12_s504/company_site_4_894f12_s504.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/company_site_4_894f12_s504/company_site_4_894f12_s504.sbv)

Duration: **8:24**

## Project Completion

You should now have a completed site that looks like [ours](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/spacedesign-final/home.html).

# On Your Own: Web Store Catalog

In this project, you will build a simple web store page from scratch, using `web_store.jpg` and `product_clicked.jpg` from [this downloadable archive](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/web_store_catalog.zip). The download also includes an `images` directory that contains the images that you need for the page.

We would typically use psd or png files for design work, but our designer lost them. All he has are these low-quality images. Using them as design files is identical to using pngs, but a bit harder since jpgs have a fuzzy appearance in the details and faded colors. Your boss asks you to do your best.

[Here's the completed project](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/web_store_catalog_final/index.html).

As with the previous project, your goal is to replicate the design as close as possible. Be sure to use semantic markup wherever possible. When you click anywhere on a product, you should display a larger version of the product image horizontally centered on the page. You should also dim the rest of the page, and let the user click anywhere on the page to restore the original display.

Hint 1

Use floats to list the products four to a row. Make sure you clear the floats to prevent the parent container from collapsing.

Hint 2

Use the `nth-of-type` pseudo-class to set the left margin for the first product in each row to zero.

Hint 3

If you place a checkbox control inside a `<label>` tag, you can click anywhere inside the area enclosed by the `<label>` to toggle its state. Even if you hide the checkbox with CSS, you can still toggle it by clicking.

Use this technique to add a hidden checkbox to the HTML for each product on the page; when you click the product, you toggle the state of the corresponding checkbox. You can then use the `:checked` pseudo-class and adjacent sibling selectors to display and hide the enlarged image.

This technique involves putting block elements inside each `<label>` tag, which is a violation of the standards. Thus, W3C validation will issue error messages like **Element “figure” not allowed as child of element “label” in this context.** You may ignore these for this project.

An [alternative approach to the checkbox trick](http://www.outofscope.com/css-only-menu-toggle-no-javascript-required/) uses the `label` element's `for` property and avoids the associated validation errors. The trade-off is that the user loses the ability to click anywhere to close the enlarged image; she must click something within the image, such as an `x` button/link.

Hint 4

Use absolute positioning to position the enlarged image on the screen.

Hint 5

To dim the rest of the page when displaying enlarged images, you will need a fixed position pseudo-element that stretches to all four window edges. You should be able to click on the pseudo-element (that is, anywhere on the page) to restore the original page.

Try to complete this on your own before referring to the walkthrough videos.

Remember: the videos may differ from the written instructions and the completed example. The written instructions take precedence.

The first walkthrough video demonstrates how to create the central HTML and CSS for our page. The second walkthrough then shows you how to achieve the click-to-expand functionality.

<video id="video_30bb0e5c3222_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/web_store_catalog_1_a3b092_s1130/web_store_catalog_1_a3b092_s1130.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/web_store_catalog_1_a3b092_s1130/web_store_catalog_1_a3b092_s1130.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/web_store_catalog_1_a3b092_s1130/web_store_catalog_1_a3b092_s1130.sbv)

Duration: **18:50**

<video id="video_9a9f2242b0fe_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/web_store_catalog_2_709a84_s415/web_store_catalog_2_709a84_s415.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/web_store_catalog_2_709a84_s415/web_store_catalog_2_709a84_s415.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/web_store_catalog_2_709a84_s415/web_store_catalog_2_709a84_s415.sbv)

Duration: **6:55**

We don't use Grid in this project, but we could use it for the main grid of items for sale. Contrast the above solution with [this solution that uses Grid](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_7/web_store_catalog_final/index-grid.html).

Now that you know the clever trick of using a checked pseudo-class to affect the next sibling, can you think of other uses for this pseudo-class? One possibility is to create a drop-down menu or an accordion of information that uses CSS animation.

You'll often want to toggle an element's state when clicking another, and this trick can be useful when you don't need to toggle more than one. Remember that a `label`'s `for` attribute can connect to a hidden checkbox elsewhere on the page; a clickable area on the left of the screen can affect an element on the right.

# Summary

This lesson covered the basics of converting a design file to a finished web page. We also discussed CSS resets and learned a bit about how to improve your HTML and CSS.

Now, let's take a moment to appreciate how far we've come in this course. You started with minimal HTML and CSS experience, but now you can create sophisticated applications that work well on phones, tablets, laptops, and desktops. What a huge accomplishment! You've come far in a short time.

Are you hungry for more front-end knowledge? Would you like to learn JavaScript in depth? Check out our next front-end course to learn more!