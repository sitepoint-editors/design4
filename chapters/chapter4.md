---
title: Chapter 4- Typography
description: Lavishly illustrated with detailed examples, The Principles of Beautiful Web Design is an easy-to-follow guide that will lead you through the process of creating great designs from start to finish. No prior web design experience is required.
image: set note default image (for link preview)
tags: Design, Book
breaks: set to use line breaks

---

# Chapter 4: Typography

### Jason Beaird and James George

Chapter 4


Let’s face it: the core purpose of all web design is communication. Whether we’re talking about an online retail store, a web presence for a Fortune 500 company, or a profile for a social networking site, typography is a vital component of your message. For most people, typography is simply about arranging a familiar set of shapes to make words, sentences, and paragraphs. But, ironically, having the ability to set type with only a few mouse clicks or strokes on a keyboard has allowed us to forget about the creative and artistic possibilities of this medium.

 

There are numerous obstacles to the effective customization of typography for the Web—and I’ll address these in the coming pages—but the power of type should be motivation enough to push the proverbial envelope. Unconvinced? Pick up a magazine, turn on a television, or take a walk through a grocery store. You will undoubtedly see hundreds of creative and effective uses of type. It’s the substance of branding, the key to unspoken communication, and an essential piece of the web design pie.

 

### This Topic May Be Addictive!

After studying typography for some time, you’ll never look at a billboard, brochure, or book the same way again. You might start snapping pictures of ride signage at theme parks, rather than your kids. Pondering whether the entrées in a restaurant menu are set in Cantoria or Meyer Two may become more interesting than choosing between the entrées themselves. The study of typography is one that draws many people in... and never lets them go! Consider yourself warned.

 

In order to unlock the potential of type, we must first understand it. Admittedly, this is no easy task. The minute details of letterforms and the spaces around them have been carefully calculated over centuries of investigation and practice. In the early days of print, every letter of every typeface had to be carved into wood or cast from lead, inked, and then pressed into paper. This was a professional craft requiring exacting attention to detail. Even though the physical craft has long been surpassed by modern printing methods, many colleges and universities offer classes in letterpress, so that future graphic designers can both appreciate the benefits of working with type on a computer, and see the potential for typographic exploration.

 

My personal love of typography is twofold. As a designer, I enjoy working with type for the artistic aspects of it. I like the unique voices that different fonts provide, and the expressiveness of typographic collages like the one in Figure 4.1. After all, the root words that comprise typography are _typos_ , meaning impression or mark, and _grapheia_, meaning writing; typography literally means making impressions with writing. As a programmer, I also appreciate the puzzle-like problem-solving that working with type involves. The choices of font and color are only the tip of the type iceberg. In fact, the majority of the decisions that need to be made in our work with type involve the space around the letterforms and text blocks, rather than the actual type itself. Nevertheless, choosing an appropriate typeface is a crucial step.

 

![A collage of found typography](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000035.jpg)

Figure 4.1. A collage of found typography

 

The history and implementation of type is a topic that could fill hundreds of books—and indeed, it has. In this chapter, though, I’ll merely provide a brief introduction to the world of typography. First, I’ll cover some of the issues with—and solutions for—taking type to the Web. Then, together we’ll examine some basic typeface terminology, explore some usage guidelines, and investigate the characteristics of different fonts. From our discussion of legibility concerns, to the question of using dynamic headings online, I hope you’ll find this chapter to be practical and inspirational. If you like what you see here, and would like to explore the rabbit hole a little deeper, here are a few web resources that I highly recommend:

 

* The Elements of Typographic Style Applied to the Web, at [http://webtypography.net](http://webtypography.net/)

* Typophile, at [http://typophile.com/](http://typophile.com/)

* I Love Typography, at [http://ilovetypography.com](http://ilovetypography.com/)

* Typographica, at [http://typographica.org](http://typographica.org/)

* The Font Feed, at [http://fontfeed.com/](http://fontfeed.com/)

 

## Taking Type to the Web

 

When it comes to the Web and choosing fonts for text that will be displayed in a browser, it doesn’t matter if you have five, or 5,000, fonts installed; you have to think in terms of the lowest common denominator.

 

The number of font families that are supported, by default, across both Mac or PC is very small. This list of nine font families in Figure 4.2 is commonly known as **web safe fonts**.

 

![The nine “web safe” fonts that are installed by default on both Windows and Mac OS X](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000088.jpg)

 

Figure 4.2. The nine “web safe” fonts that are installed by default on both Windows and Mac OS X

 

The downside to the safe list is that there’s limited variety within each font category. If you need a standard sans-serif<sup>[7]</sup> font, you have to choose between Arial, Trebuchet MS, and Verdana. For someone who hasn’t been exposed to many fonts, that may seem like a reasonable variety, but for those of us who know the nuances of other sans-serif fonts like Helvetica Neue, Futura, and Univers, using one of the safe fonts can be like using a screwdriver to drive in a nail.

 

Fortunately, the `font-family` property of CSS allows you to choose multiple fonts in order of preference. This is referred to as a **font stack**. If the first font is unavailable, the second font will be used; if the second font is absent, the third font will be used, and so on. Let’s say that you want your section headlines to have a serif font. You think the best font for the job is Calisto MT, so you specify that first—for the few people that have it installed. Your second choice is your first backup plan, and for this you choose Georgia. If users don’t have Calisto MT installed, they’ll see Georgia. Even though Georgia is on the safe list, some people may not have it installed. Times New Roman is a close equivalent, so you decide that you might as well add it as your next alternative. To finish off the preferential list, to cater to users who don’t have any of those fonts installed, you add what the W3C calls a **generic font family**. The generic font families are `serif` , `sans-serif` , `cursive` (similar to script or hand lettering), `fantasy` (or novelty), and `monospace` . All your font choices so far have been from the serif family, so that’s the generic family you specify. In summary, your font stack would look like this:

 

``` font-family: 'Calisto MT', Georgia, 'Times New Roman', serif; ```

 

#### Fonts with Spaces

Remember that any font family names that include spaces must be quoted, either using single ( `'` ) or double ( `"` ) quotes.

 

The key to creating an effective font stack is knowing which fonts are most similar and, more importantly, which ones are installed by default in each operating system. For a handle on the first part, I recommend reading Nathan Ford’s 2008 article,[“Building Better Font Stacks.”](http://unitinteractive.com/blog/2008/06/26/better-css-font-stacks/)A great resource for checking on the prevalence of specific fonts in various operating systems is Code Style’s interactive[Font Stack Builder.](http://www.codestyle.org/servlets/FontStack)

 

## Web Fonts with `@font-face`

 

Jason Cranford Teague, the author of_Fluid Web Typography,_<sup>[8]</sup>recently asked in a presentation, “What do these three things have in common: flying cars, trips to Jupiter, and downloadable web fonts?” The answer is that we were supposed to have them all by the year 2010. What Teague was talking about was the ability to display text on a website using fonts not installed on the visitor’s computer. A mechanism for doing just that has been a part of CSS since 1998. It’s called `@font-face` , and it works like this:

 

``` @font-face { font-family: "League Gothic"; src: url("/type/league_gothic.otf") format("opentype");}≠≠h1 { font-family:"League Gothic", Arial, sans-serif;} ```

 

If you’re familiar with CSS, the syntax of `@font-face` is brilliantly self-explanatory. We’re simply defining a URL where the font family League Gothic can be found. Once that’s established, you list it in your font stack the same way you would any other font. So why haven’t we been using this all along? The two main roadblocks have been resistance from font foundries, and inconsistencies in supported font formats.

 

The resistance from the foundries is understandable. They make their money through licensing the use of their fonts, so want to deter people from downloading, copying, and using them for free. The licenses that protect these fonts usually don't allow for use of their fonts on the Web. Always be sure to read the license and usage guidelines. The file format part of the story is a little messier. Some browsers support the TTF and OTF formats, iOS devices (such as the iPhone and iPad) require SVG, Internet Explorer only uses Microsoft’s proprietary EOT format, and to cap it all off there’s an up-and-coming open source format (WOFF) that’s supported by the very latest versions of most browsers. Over the last few years, though, the technical issues with embedding fonts have been overcome. This led to a huge explosion in commercial-use free fonts, which, in turn, forced the foundries to reconsider their position on licensing fonts for embedding.

 

Unfortunately, though, it looks like we’ll have to wait a long while yet for flying cars and trips to Jupiter.

 

### Self-hosted Web Fonts

 

Because of the difference in required formats, you can’t just toss a TTF file into a folder on your site and link to it as I suggested in the simplified `@font-face` code above. What’s more, doing so would most likely violate your End User Licensing Agreement (EULA) with the font’s foundry. If you want to host your own fonts, they’ll have to be licensed for web embedding, you’ll need several different font formats, and you’ll need the latest code for embedding all those formats. That’s where [Font Squirrel,](http://www.fontsquirrel.com/)seen in Figure 4.3, comes to the rescue. On this very useful site, you’ll find hundreds of excellent free fonts, downloadable kits for embedding those fonts into your sites, and a generator that can convert your own font files into all the required formats. If you’re unable to find what you’re looking for in Font Squirrel’s collection of free fonts, visit their sister site, [Fontspring](http://www.fontspring.com/). Here you can purchase commercial fonts from actual font foundries who allow `@font-face` embedding, many of which offer an unlimited domains license for a small surcharge.

 

![A selection of the vast array of free fonts available at Font Squirrel](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000102.jpg)

 

Figure 4.3. A selection of the vast array of free fonts available at Font Squirrel

 

### Web Font Services

 

If you’d rather not bother with all the font files and ever-evolving code for embedding them, there are several services that host the fonts and keep up with the embedding nuances for you. With each of these services, you simple pick a font, grab a snippet of code to drop into your site, and voilà! Your type is displayed in that font.



Typekit, at [http://typekit.com](http://typekit.com/)
:    This is the original and most popular hosted font solution, developed by industry thought leaders including Jeffrey Veen and Jason Santa Maria. Because Typekit has a huge library and a number of type foundries on board, it’s been referred to as the iTunes of fonts. They offer a free trial library for a single site; otherwise, their pricing is based on a yearly subscription that varies based on page views per month. 

Fontdeck, at [http://fontdeck.com](http://fontdeck.com/)
:    Like Typekit, Fontdeck is a subscription-based service developed by industry leaders. The difference is that this service developed by Clearleft and OmniTI allows you to pay for only the fonts you’re using, rather than the entire collection. 

WebINK, at http://www.webink.com/
:    Extensis is the developer of one of the most popular font management applications available. WebINK is its entry into the hosted web font market. It has the backing of a large number of font foundries, but the subscriptions are monthly instead of yearly. 

Google Fonts, at https://www.google.com/fonts
:    With some help from Typekit, Google recently released its own font-hosting solution. Currently the selection is more limited than Fontdeck or Typekit, but because it only hosts creative commons licensed fonts, it’s completely free. 

 

There are a number of other web font services out there, with more popping up every week. Several font foundries have even joined in on the action, offering hosted versions of their own fonts. Because support for `@font-face` is so new, it’s hard to know which ones will shine and which ones will fizzle out. Regardless, downloadable web fonts are here to stay. A great place to find the latest info about `@font-face` and web fonts is the [webfonts.info](http://webfonts.info/) wiki.

 

## Text Image Replacement

Web typography is nowhere near as limited as it used to be. In the past, if you wanted a beautiful, highly customized type treatment for your website, you pretty much had to resort to **image replacement**; in other words, replacing the text on the page with images created in Photoshop or similar software. Now, with CSS3, you can create some amazing type effects, such as arched text. However, if you want this effect to display properly in older browsers, you’ll have to use JavaScript as a fallback when CSS3 features aren’t supported (you can use a tool like [Modernizr](http://modernizr.com/) to determine which features are supported).

 

Text Image replacement still has its place on the Web in certain instances. Sometimes people disable JavaScript, or their browser might not support a specific CSS3 feature. If you are worried about users being unable to display your text as intended due to compatibility issues, then you may want to consider text image replacement. Note that this doesn't mean just tossing an `<img>` tag with your text straight into your HTML. Using an image tag to display text is neither accessible nor search engine friendly—because any visitors who’re unable to see the image will be left in the dark. This includes search engine spiders, of course.

 

Instead, you’ll want to mark up your text as actual text. Take the example of the [Barstow website](http://www.ridebarstow.com/), shown in Figure 4.4. It features rounded vintage text, which looks great and stands out against all of the straight and grid-based typography on the web. If I wanted to make the logo and text accessible, I would make it an HTML `<a>` element and give it a class of `logo-active` .

 

To replace that with an image, I’d then use CSS to set the width and height of the link to the size of my image, and set the `display` property to `block` , since links are inline by default. Then, I typically use what’s known as the **Phark Method** of image replacement. This involves setting my image as the background of the element, and then adding a negative `text-indent` value high enough to move my text content out of the block (and off the screen!). The CSS would look like this:

 

``` .logo-active { display:block; width:300px; height:150px; background:url(/images/clowns.png); text-indent:-9999px;} ```

 

![The Barstow website](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000181.jpg)

 

Figure 4.4. The Barstow website

 

#### What’s up with Phark and dotted outlines?

As you click on or tab to a link in an HTML document, you activate its `:focus` state. By default, Firefox adds a dotted border around focused links using the `outline` property, so that users navigating a site by keyboard can see what link they’re currently on. That outline usually includes your negative indented text, so users will see a dotted outline that extends all the way to the edge of the page. There are two options for fixing this. You can add `overflow:hidden` to the link to contain the outline, or remove it entirely by adding `outline:0` . If you do this, be sure to define a `:focus` style for users that might be navigating by keyboard.

 

Displaying text in images works well for static text that changes infrequently, but what if you want to use a specific font for text that changes periodically, like the headline of a news article? Constantly creating and uploading new text graphics would be a tedious task, even for a designer who’s a pro at using image-editing software. If, for example, you’re setting up a blog for a client who has no idea how to use Photoshop or write HTML, you might as well forget about this option.

 

Another image replacement option is to use SVG, or **Scalable Vector Graphics**. SVG has a small file size, and is infinitely scalable. You can use it in an `<img>` tag, and you can size it with CSS. The benefits of SVG are that it doesn't lose clarity as you scale it, and that you have a lot of control over how it appears.

 

Sam Ruby's site, [Intertwingly](http://intertwingly.net/), shown in Figure 4.5, uses SVG instead of images to accompany each article.

 

![Sam Ruby's Intertwingly](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000168.jpg)

 

Figure 4.5. Sam Ruby's Intertwingly

 

You can learn more about SVG at the following resources:

 

* [Learnable](https://learnable.com/books/jump-start-html5-canvas-and-svg#overview)

* [A List Apart](http://alistapart.com/article/using-svg-for-flexible-scalable-and-fun-backgrounds-part-i)

* [CSS Tricks](http://css-tricks.com/using-svg/)

 

## Anatomy of a Letterform

 

Some of the design classes I took in college delved fairly deeply into the anatomy and terminology of type. Many people can already identify serifs, ascenders, and descenders, but for one class, we had about 100 terms to memorize. While I’ll be nicer here, it’s important that you know some basic terminology before we continue learning about type. Sure, I _could_ just talk about type using informal words like squiggles, slants, and thingies to describe letterforms, but that could grow confusing rather quickly.


*Figure 4.6* represents an example of each component of a typeface. We’ll go over them in turn below.

 

![The terminology of type](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000147.jpg)

 

Figure 4.6. The terminology of type

 

1. Baseline
:    The **baseline** is the imaginary horizontal line on which most characters sit. The only character that hangs below the baseline in Figure 4.6 is the lowercase “q.” 
2. Cap height
:    The **cap height** or **capline** is another imaginary line. This one marks the height of all capital letters in a typeface. Notice that the cap height is below the maximum height of the typeface. 
3. Crossbar
:    A stroke that connects two lines in the capital letterforms of “A” and “H” is called a **crossbar**. A horizontal stroke that does not connect two lines, like the one in the lower case “f” or “t,” is known as a **cross stroke**. 
4. Serif 
:    **Serif** is the name given to the finishing strokes at the bottoms and tops of certain typefaces. I’ll talk more about serifs when we cover typeface distinctions. 
5. Mean line
:    Another imaginary horizontal line that marks the top edge of the lowercase letters is the **mean line** (or **midline** ). Contrary to what you might imply from its name, the mean line isn’t always exactly centered between the baseline and the cap height.
6. Bowl
:    The **bowl** of a letter is the rounded curve that encloses negative space in a letterform. Examples of bowls can be seen in the letters “D,” “o,” and “g.”
7. Descender
:    The lower portion of a lowercase letter (such as “g,” “j,” “p,” “q,” and “y”) that extends below the baseline of a typeface is known as the**descender**. The only other characters that typically extend below the baseline are the old-style numerals in some typefaces. These types of numerals, examples of which from the Georgia typeface can be seen in Figure 4.7, were thought to blend better with lowercase roman numerals, and they look particularly good when used within a body of text.

    ![Old-style numerals in the Georgia font on the left, and standard numerals in Helvetica on the right](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000171.jpg)

    Figure 4.7. Old-style numerals in the Georgia font on the left, and standard numerals in Helvetica on the right 
8. Counter
:    The negative space within a letter is called the **counter**. In some letters, like “A,” “o,” and “P,” the counter is fully enclosed. The non-closed negative spaces in letters like “G,” “u,” and “c” are also known as counters. 
9. Stem
:    A stem is the main vertical or diagonal stroke in a letterform. These include the vertical portions of the letters “I” and “H,” as well as all the strokes in the letter “W.”
10. Tittle
:    This is probably my favorite typeface term. **Tittle** is the name given to the dot above the lowercase “j” and “i.” 
11. Terminal
:    The end of a stem or stroke that has no serif is known as a **terminal**. Even the ends of some serif typefaces have terminals, as you can see in the letter “c” in Figure 4.6. 
12. Ascender
:    Some lowercase letters have an **ascender**, which is an extension that rises above the mean line. Those letters are “b,” “d,” “f,” “h,” “k,” “l,” and “t.” 
13. Leg
:    The lower angled strokes seen in the letters “K,” “R,” and “Q” are known as legs. These are also sometimes referred to as tails. 
14. Ligature
:    You may have noticed in *Figure 4.6* that the “f” and “i” of the word “fix” are combined into one character. This joining of characters is known as a **ligature**. Ligatures are most often seen in serif faces, and exist to give the spacing between certain characters a greater aesthetic balance, as *Figure 4.8* illustrates.

    ![Example of an “ae” ligature in the font Insignia](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000034.jpg)
    Figure 4.8. Example of an “ae” ligature in the font Insignia
15. x-height
:    Simply put, **x-height** is the vertical space occupied by the lowercase “x” in a given typeface. More accurately, it’s the distance between the baseline and mean line that defines the body of lowercase letterforms—excluding ascenders and descenders. X-height is a key factor in typeface identification, and typefaces with larger x-heights are generally regarded as being more readable.

    Although it’s impractical, you can actually use x-height as a relative unit of measurement in CSS ( `ex` ). 

 

## Text Spacing

 

Now that you know how to describe the parts of a letterform, the next step is to be able to define and adjust the space between letters. I mentioned before that many typographic decisions are based on spacing. This is has always been true with printed type, and became applicable to web type with the advent of CSS. Regardless of whether we’re talking about using type for print or for the Web, there are two directions in which we can control spacing: horizontally and vertically.

 

### Horizontal Spacing

 

Kerning and tracking are two terms you’ll often hear in conversations about horizontal letter spacing. **Kerning** is the process of adjusting the space between individual letters. Often when you’re working with type, you’ll notice pairs of letters that appear too close together, or too far apart. Most fonts have a set of rules that determine the spacing between specific characters. The kerning between the letters “Wa,” for instance, should be—and is—much tighter than the kerning between “WV.” Most of the time, the rules for the font are sufficient to make the text readable. Otherwise, you can adjust the individual letter pairs within your image creation software of choice. *Figure 4.9* shows examples of text with no kerning applied, automatic kerning, and manually adjusted kerning.

 

![AWE-inspiring kerning examples](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000143.jpg)

Figure 4.9. AWE-inspiring kerning examples

 

For the text in a web page, it’s impossible to make letter-by-letter kerning adjustments. What you _can_ do is adjust the `letter-spacing` CSS property, which is known in the print world as adjusting the font’s  **tracking**. Like kerning, tracking adjusts the horizontal spacing between letterforms, but applies to the space between each letter. If you want your text to have a more open, airy feel, try adding a bit of letter spacing as I’ve done in *Figure 4.10*.

 

![Letter spacing example](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000007.jpg)

 

Figure 4.10. Letter spacing example

 

Another horizontal spacing option in CSS is provided by the `word-spacing` property. This property can take a positive or negative length, or the keyword `normal` . As you might expect, it affects the amount of whitespace between words.

 

### Vertical Spacing

 

In print design language, the vertical space between lines of text is known as **leading**. This term comes from the early days of letterpress when blank strips of lead were used to separate lines of metal type. When there were no added spacers, the lines were said to be set “solid.” Text with added vertical space is much easier to read. As you can see in the first paragraph in *Figure 4.11*, the default spacing between lines of text is too small. Ideally, you want the line height on your body copy to be about one-and-a-half times the size of your text; so if you have 12px text, 18px is a good readable line height. 

In the second paragraph we’ve adjusted the CSS `line-height` property to 1.5em. An em is a CSS unit that measures the size of a font, from the top of a font’s cap height to the bottom of its lowest descender. Originally, the em was equal to the width of the capital letter M, which is where its name came from.

 

![Leading example](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000060.jpg)

 

Figure 4.11. Leading example

 

## Text Alignment

 

Have you ever noticed that the text you see in books and magazines is often aligned along both the left- and right-hand sides of the page or column? This type of text alignment is known is **justification**. When text is justified, the letter and word spacing is automatically adjusted so that each full line of text has a word or letter that lines up against the left and right edges of the text area. Many print designers will use justified text for any text block that’s over two lines long and is wide enough. You can take this same text treatment to the Web with CSS by setting the `text-alignment` property to `justify` . Before you go and justify the whole Internet, though, let me give you two warnings about justified text:

 

A river runs through it
:    Occasionally, a gap created by wider spacing in one justified row will line up with a gap in the next row, and the next, and the next… and you end up with a canyon or **river** in your type, as shown in *Figure 4.12*. This can be distracting for the reader. Print designers can makes adjustments to fix this sort of problem, but on the Web, it’s difficult to predict and impossible to fix. 

What? Are? You? Saying?
:    The river problem is even more pronounced with narrow columns. Words will often be isolated against the left and right margin, or stretched over the entire width of the column. Most word processing programs fix this problem by hyphenating words where necessary. Browsers are unable to do this kind of auto-hyphenation, so web designers should avoid using justified text in narrow spaces. 

 

![Justification problems: can you spot the three other rivers present in this lorem ipsum text?](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000138.jpg)

 

Figure 4.12. Justification problems: can you spot the three other rivers present in this lorem ipsum text?

 

If you don’t want to change the `text-alignment` of your text to `justify`, your other options are `left` , `right` , or `center` . When text is centered or aligned along the left or right edge of the page or column, the spacing between the characters and words remains constant. The river problem can occur with any text block, but it’s much less likely to cause legibility issues in text that’s centered or justified on one side only.

 

If you want to see how some HTML text will look in the browser with different leading, tracking, and alignment settings applied, two great tools to check out are Marko Dugonjic’s [Typetester](http://www.typetester.org/) and Panduka Senaka’s [Typechart.](http://www.typechart.com/) Both of these web applications enable you to try out a variety of typographic configurations for HTML text, and then grab the CSS needed to create the effect.

 

![Typetester (left) and Typechart (right) allow you to quickly test-drive HTML type configurations](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000174.jpg)

Figure 4.13. Typetester (left) and Typechart (right) allow you to quickly test-drive HTML type configurations

 

## Typeface Distinctions

 

Everybody knows what a font is. It’s a set of letters that appear in a certain style; they come pre-installed on your computer. And you change the font when you want your text to look different. The average Windows PC has just over 40 fonts installed by default, while the average Mac user has access to around 100 fonts. Many of these fonts are grouped together into font families, with each font within the family representing a different variation of the core font. Most font families include the regular font face, along with italic, bold, and bold italic variants. Some fonts have no variations at all; some may only have bold or italic, and some commercially available font families have hundreds of variants.

 

![Fourteen Gs](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000073.jpg)

Figure 4.14. Fourteen Gs

 

Just as all the members of some families have big ears or abnormally long pinkie toes, every font family has its own unique, identifiable characteristics. Take a look at the variation that exists between fonts for the letter “g” in *Figure 4.14*.

 

These characteristics are what help us to categorize fonts and font families. The majority of font families can be classified as either serif or sans-serif. Of the 14 different fonts represented in *Figure 4.14*, seven could be classified as serif and seven as sans-serif. Can you distinguish between them? Beyond this distinction, there are many other ways in which we can classify and group fonts. I prefer to group fonts into six simple categories: serif, sans-serif, handwritten, monospace, novelty, and dingbats. Let’s look at each of them now.

 

### Serif Fonts

 

Historians believe that the serif has its origin in Roman stone carving. There is much debate over the original purpose of these ornamental strokes, but in more recent history, they’ve been proven to increase legibility in large blocks of text by providing a horizontal line of reference. When designers choose a serif font, Times New Roman is often the first one that comes to mind. However, there’s a great variety of serif fonts on offer. To help us with that decision, it’s a good idea to first decide what type of_voice_we want our text to have.

 

![Serif categories](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000202.jpg)

 

Figure 4.15. Serif categories

 

Take a look at the Garamond text in Figure 4.15. Garamond is an **old-style serif** font. Old-style serif fonts are adapted from the brushstrokes of Italian scribes and can be recognized both by the smooth transitions between thick and thin strokes, and by their rounded serif edges. When I see an old-style serif font, it exudes historic, handcrafted charm. At the same time, fonts like Garamond are extremely versatile: they’re not so old-fashioned that they're unusable in modern applications.

 

The second font in Figure 4.15 is Baskerville, a **transitional serif** font. The curved angle that connects the terminal of the stroke to the serif is known as a **bracket**. The brackets of transitional serif fonts are rounded, but the edges of the serifs are squared off. The simple addition of 90-degree angles and perfectly straight lines gives this category of font a more modern and mechanical voice. This category of serif fonts is known as transitional because it provides a transition between old-style and modern serif fonts.

 

The third font, Didot, is a **modern serif** font. Modern serif fonts provide a large amount of contrast between the thick and thin strokes, and their serifs are often completely unbracketed. Modern serif fonts were introduced during the Industrial Revolution as a radical alternative to the transitional serif style. Today, these fonts have an association with elegance, sophistication, and fashion. They represent timelessness more than cutting-edge modernity. Because of their fine line details, modern serif fonts are really only suitable for use in headlines. The consistent use of Italian Didot in [_Vogue_ magazine,](http://www.vogue.com/)as seen in Figure 4.16, helped to establish both the font and the magazine as icons of style. Other famous magazines that use modern serif font faces for their mastheads include _Brides_ , _W_ , _Elle_ , _Parents_ , _Seventeen_ , and _Harper’s Bazaar_ s. They’re fairly uncommon in web design, but are certainly a classy choice if high style is what you’re aiming for.

 

![Modern serifs lending a classy feel to Vogue](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000045.jpg)

 

Figure 4.16. Modern serifs lending a classy feel to Vogue

 

In the later part of the 1800s, as advertising, posters, and flyers became more common, a bolder variation of modern serif fonts was needed to catch people’s attention. It was at this time that **slab serif** fonts were first introduced. Slab serif faces like Rockwell have an industrial but friendly voice that’s far less snooty than modern serifs, and even more contemporary. Because most slab serifs were designed to be readable from a distance, they make for excellent headlines and have been very popular on the Web lately. Figure 4.17 shows a couple of beautiful examples of slab serifs in action. On the left [_The Sew Weekly_’s](http://www.sewweekly.com/) logo features a typeface called Brosse. On the right we have [_The Mid-century Modernist_,](http://midcenturymodernist.com/) which uses Rockwell Light for its logo. I personally think that slab serifs tend to feel masculine. The Sew Weekly is a beautiful contradiction to that notion, and evidence that you can go against convention when choosing fonts.

 

![Slab serifs at the Mid-century Modernist and Sew Weekly](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000010.jpg)

 

Figure 4.17. Slab serifs at the Mid-century Modernist and Sew Weekly

 

### Sans-serif Fonts

 

At the time when typographers began experimenting with slab serifs, the idea of eliminating the serif altogether seemed like a huge mistake. Serifs were a tradition, so removing them was typographic castration. The initial sans-serif fonts were so loathed in the 1800s that they were referred to as grotesque. Eventually, though, people began to warm to the idea of serif-less typefaces, and by the 1920s some speculated that the serif would soon be eliminated.

 

Although serif fonts are still used extensively, the popularity and versatility of the sans-serif font category continues to grow. These types of fonts have a cleaner and more contemporary feel. They stand out as headlines, especially when paired with body text that’s set in a serif face. This has long been a standard practice in print design, and is a tip that I was taught in college for creating contrast between headlines and body copy. On the Web, though, the roles have been reversed for a very long time. This is mainly due to the one-two punch of low-resolution display hardware, combined with poor text hinting and rendering in older operating systems. Because of the stroke variation and minute detail of serif fonts, they can become almost unreadable at small sizes on lower-resolution displays. As the pixel density of displays increase and older computers die off, we’re free to serif, or not to serif. Figure 4.18 shows [Spoongraphics,](http://blog.spoongraphics.co.uk/) a design blog I enjoy following, which uses the time-honored tradition of sans-serif headings and serif body copy.

 

![An Example From Spoongraphics](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000016.jpg)

 

Figure 4.18. An Example From Spoongraphics

 

Regardless of how they’re used, sans-serif fonts are extremely legible and practical for almost any purpose. The most ubiquitous sans-serif fonts on the Web are Arial and Verdana. Each of these font families exists in the default font sets of both major operating systems, and, as a result, they're predictably the workhorses of web body copy. In the design world, these families have a reputation for being overused and generic (and in the design community, Arial has the added stigma of being widely considered the poor cousin of Helvetica). This makes Arial and Verdana great for body text, where voiceless legibility is the goal, but for headlines and artistic applications, a more characterful feel is often required. Sometimes a stronger serif font, or a more distinguished sans-serif, will do the trick, but there are certainly many more options available outside these two categories.

 

### Handwritten Fonts

 

![Handwritten fonts: for a human touch](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000076.jpg)

 

Figure 4.19. Handwritten fonts: for a human touch

 

Before the invention of movable type systems, all text had to be carved, brushed, or written by hand. The downside to handwritten text—especially my own—is that achieving a uniformity of letterforms, alignment, and spacing can be frustrating. And, as a result of these challenges, handwritten text can be very difficult to read. Yet the wonderful aspect about handwriting is that it acts as a symbol of humanity, giving a tangible personality to the text it represents. Just look at the text in Figure 4.19. Each line was written to represent the personality of the font in which it’s written.

 

Handwritten fonts provide a personal touch without the human error factor. The lettering and alignment in a handwritten font will be consistent, and if the font is well-designed, the spacing should be good, too. As you look around at handwritten fonts on the Web, you’ll probably start to think that anyone and their cousin’s dog could create one, and it’s true. Unlike serif and sans-serif faces that require practice and precision, handwritten fonts are all about personality. If you want to create a font from your own handwriting, there are dozens of tools and services out there. One of the simplest sites for this is [YourFonts.com.](http://yourfonts.com/) You simply print out a PDF template, scribble your glyphs into the little boxes, scan it, upload it, and for a small fee, you can download an OpenType format font file.

 

If you’re trying to make a website feel very friendly and human, sometimes a font, even a handwritten one, is a little too perfect. Take the [Packdog Website](http://chirp.twitter.com/) in Figure 4.20, for example. If you look closely at the lettering, you’ll notice that no two letters are exactly the same. That’s because rather than being a font, it’s a beautiful example of hand lettering. Most people probably would fail to notice the subtle variation between the same letters here, but that tiny detail helps this conference website feel a lot more fun and friendly.

 

![Hand lettering on the Packdog.com site](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000031.jpg)

 

Figure 4.20. Hand lettering on the Packdog.com site

 

### Fixed-width Fonts

 

You may have noticed by now that in most fonts, each letter takes up a different amount of space. For instance, the capital “W” takes up a large area, while the letter “l” has a very narrow footprint. To illustrate this point in plain text, take a guess which of the sentences in Figure 4.21 has more characters.

 

![A proportionately spaced font](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000191.jpg)

 

Figure 4.21. A proportionately spaced font

 

That was a trick question; they actually have the same number of characters! So why does the first sentence appear so much longer than the second? The explanation for this phenomenon is that the majority of fonts are proportionately spaced. Associated with each character of each font are rules that determine not only the width of the character, but also the amount of space that will appear around each character. Take a look at those two sentences again, this time displayed in the Courier font, in Figure 4.22.

 

![A fixed-width or monospaced font](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000187.jpg)

 

Figure 4.22. A fixed-width or monospaced font

 

The reason the two sentences appear to be the same width now is that Courier is a fixed-width or monospaced font. This category of fonts has uniform spacing, and the letterforms are designed so that they’re similar in width. Fixed-width fonts were initially designed around the technical limitations of typewriters. Since early typewriters were incapable of moving the typed page a different distance when a “w” was typed, rather than an “i,” specialized fonts were developed for these devices. These fonts had to remain readable, despite the spacing being the same for every letter. Early computer displays employed fixed-width fonts as well, but it was only a short time before computers were able to display much more legible variable-width (or proportional) fonts.

 

So why are fixed-width fonts still around today? Mainly for the sanity of coders and accountants. When you have to write code or display data as text, it’s important that characters line up from row to row and column to column. If you’re reading this book, you’re probably already familiar with fixed-width fonts from writing HTML and CSS. The benefits of these monspaced faces can be seen clearly in Figure 4.23. [CSS3, please!](http://css3please.com/) is a cross-browser CSS3 rule generator that allows you to experiment with CSS3 properties.

 

![Fixed-width fonts in action at CSS3, please!](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000170.jpg)

 

Figure 4.23. Fixed-width fonts in action at CSS3, please!

 

On the Web, the standard way to display text in a fixed-width font is to wrap it with `<pre>` and `</pre>` tags. `pre` is short for preformatted text, and aside from displaying fixed-width characters, the `pre` element also preserves tabs, spaces, and line breaks. This usually makes displaying code or tabular data on a website as simple as cutting and pasting from the source. I say_usually_because HTML tags that exist within preformatted text will be rendered normally, so if you’re trying to include any tags in your code, you’ll need to replace any `<` s with the HTML character code equivalent of `<` , and any `>` s with `>` . As with every other HTML element, `pre` can be styled with CSS. Often, web developers who plan to show code on a page want the code to stand out from the regular text. Using CSS, the `pre` tag can be given a border, a background treatment, additional margins, or a different text treatment to help it to stand out.

 

Another interesting, albeit obsolete, use of fixed-width fonts is in the creation of ASCII art. ASCII (American Standard Code for Information Interchange) was one of the original English character encodings for communications equipment, and for several years the 95 printable characters in this seven-bit system were the only graphics that ever showed up on a display. Before the Internet existed outside of the military and academia, there were networks of dial-up bulletin board systems (BBSs), many of which displayed menus and game graphics in ASCII characters. Having grown up during the peak of the BBS era, I loved to see the “underground” graphics people could create using only fixed-width type.

 

Although you can now create more intricate ASCII art with web apps like [ASCII-O-Matic](http://www.typorganism.com/asciiomatic/) or Patrick Gillespie’s [Text Ascii Art Generator,](http://patorjk.com/software/taag/) the ASCII art created during the late 1980s and early 1990s was composed character by character, and really pushed the limits of the medium. This type of artwork, like the Energy BBS title in Figure 4.24, is an often-overlooked link in the history of computer graphics.

 

![Energy BBS ASCII art by Carsten Cumbrowski](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000189.jpg)

 

Figure 4.24. Energy BBS ASCII art by Carsten Cumbrowski

 

### Novelty Fonts

 

![Examples of novelty fonts](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000204.jpg)

 

Figure 4.25. Examples of novelty fonts


**Novelty fonts**, which are also known as **display** , **decorative** , or **fantasy**fonts, represent the vast majority of free fonts that are available online. Some of the fonts in this category are modified versions of popular serif or sans-serif fonts, and some are completely off-the-wall ideas that would be better described as conceptual art than a font face. By their very nature, these fonts are less legible than their traditional counterparts, but when used sparingly, they can add a wealth of personality and flair to a design. A few examples of novelty fonts are shown in Figure 4.25.

 

Sometimes, a good place to use a novelty font is as a starting block for a logo design. Take a look at Tony Yoo’s personal portfolio site [Hype-nation](http://hype-nation.com/) in Figure 4.26. It’s a bold, retro, geometric design that works well with the blocky typeface that he’s used for the logo. It looks a lot like the capital letters from a font called La Moda, but most likely it was customized to give it a personal touch.

 <!-- Browser --> <div class="sitepreview"> <div class="browser"> <div class="browser__bar"> <div class="browser__dots"></div> <div class="browser__address"> <a class="browser__url" target="_blank" id="site-url" href="https://besthorrorscenes.com/">https://besthorrorscenes.com/</a> </div> </div> <div class="browser__body"> <img id="target" alt="Figure: 2:16 https://besthorrorscenes.com/ " class="browser__image" src="https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000163.jpg" /> </div> </div> </div>



Figure 4.26. Hype-nation’s bold retro design

 

While I do know a thing or two about typefaces, I’m hardly a font-recognizing machine. Usually, if I come across an interesting string of text in a font I fail to recognize, the first thing I think is WTF! I am, of course, referring to MyFont’s excellent [WhatTheFont](http://new.myfonts.com/WhatTheFont/) automatic font identification system. All you have to do is crop and clean up a block of type, upload it to WTF, and it will search for character matches in its database. Figure 4.27 shows some of the matches for the Hype-nation text above. WTF really is an invaluable tool, and if it fails to recognize your text, the site has a forum of “cloak-draped font enthusiasts” who love to solve typographic puzzles.

 

![MyFonts’ WhatTheFont service](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000039.jpg)

 

Figure 4.27. MyFonts’ WhatTheFont service

 

As with all design choices, before you use a novelty font, you should think about your client’s requirements and target audience. Most clients will already have some form of branding in place, and choosing a bizarre or offbeat novelty font may tarnish the company’s image. Even so, it’s best to keep an open mind when you’re coming up with themes for a website design. It may be that the company you’re working with wants to stray from its corporate image.

 

### Dingbat Fonts

 

When you’re looking for illustrations and artwork to incorporate into the design of a website, you should consider **dingbat* *or **symbol** fonts. In the early days of print, dingbats were ornamental characters used to separate printed text and fill whitespace. Original dingbat fonts consisted mainly of flourishes and commonly used symbols; however, the concept of dingbat fonts changed radically with the digital font revolution. Now, any series of graphics can be assigned as characters in a dingbat font.

 

While these fonts may not be of much use from a typesetting perspective, they can be useful as supportive vector graphics and icons. Since fonts consist of scalable vector shapes, dingbat glyphs can be converted to outlines in Photoshop or Illustrator, and then resized, dismantled, and manipulated without any loss of quality. The only issue when using these fonts is that you have to know where to find the glyph you’re after. Occasionally, I’ll remember an arrow or symbol from a dingbat font, and type out half the alphabet before I find the one I want. Fortunately, though, most dingbat fonts have a theme, so it’s easy to remember which font the glyph is in, even if the specific character is hard to find.

 

When people think about dingbats, the first sets that come to mind are Wingdings and Webdings, the dingbat fonts that come pre-installed in Windows. There are actually hundreds of other dingbat fonts available on the Web. A few examples are given in Figure 4.28.

 

![A few examples of free dingbat fonts](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000046.jpg)

 

Figure 4.28. A few examples of free dingbat fonts

 

## Finding Fonts

 

Although I’ve mentioned that you can find fonts on the Web a few times now, I’ve yet to really give you any places to look for them. If you start googling for fonts, you’ll probably discover that there are three main categories of font sites out there: free font galleries, commercial font galleries, and sites for individual artists and foundries. All are great sources of fonts to add to your typographic tool belt.

 

### Free Font Galleries

 

These websites list and categorize free fonts from many designers. Some of the designers listed on these galleries have their own websites, through which they sell other fonts that they’ve designed. If you enjoy the fonts created by particular designers, be sure to track down the rest of their work. Remember that there are a lot of really ugly free fonts out there, and while many websites claim to offer free fonts, you often have to wade through loads of annoying ads to download them. Also, if you plan to embed a font (even a free one) into your site using `@font-face` , be sure that the font’s license allows it. With that said, here are a few great resources for free fonts:

 

* Font Squirrel, at http://fontsquirrel.com/

* The League of Movable Type, at https://www.theleagueofmoveabletype.com/

* DaFont, at http://dafont.com/

 

### Commercial Font Galleries

 

Like the free and shareware galleries mentioned above, these websites promote fonts from many different designers and foundries. But unlike those galleries, most of the fonts here cost money. In most cases, though, you really get what you pay for with typography. If you license a font from one of these sites, as well as gaining a complete set of characters, the purchased fonts often include bold, italic, oblique, and other variants.

 

* FontShop, at http://fontshop.com/

* Monotype, at http://fonts.com/

* Veer, at http://veer.com/products/fonts/

* MyFonts, at http://myfonts.com/

* Adobe Fonts, at http://adobe.com/type/

 

### Individual Artists and Foundries

 

Many of my favorite contemporary fonts come from a handful of individual artists and companies. Most of these websites have a few free fonts, as well as offering fonts for sale:

 

* Jos Buivenga’s exljbris Font Foundry, athttp://www.exljbris.com/. Creator of such popular typefaces as Museo, Anivers, and Diavlo.

* Letterhead Fonts, at [http://letterheadfonts.com](http://letterheadfonts.com/). This little foundry has over 200 high-quality unique fonts from which to choose.

* Blue Vinyl Fonts by Jess Latham, athttp://bvfonts.com/. Like many font designers, Jess started designing fonts as a hobby. His freeware and paid fonts have a unique style and are very well done.

* Fountain Type by Peter Bruhn, athttp://fountaintype.com/. Fountain features some of the best fonts from about 20-odd designers around the world. The site also provides attractive freeware fonts.

* Typodermic Fonts by Ray Larabie, athttp://typodermicfonts.com/. Ray is a rock star in the realm of free fonts. His work is known for having large character sets that are top quality.

* Misprinted Type by Eduardo Recife, athttp://misprintedtype.com/. Eduardo is the man when it comes to weathered, worn, and eclectic font faces. His work is unmistakably unique, if a little twisted.

* Pizzadude by Jakob Fischer, athttp://pizzadude.dk/. Jakob has an admittedly goofy and laid-back style, but has cranked out over 500 handmade fonts since 1998.

 

## Choosing the Right Fonts

 

Even if you understand all the technical aspects of letterforms and typeface categories, and have access to all the fonts in the world, you can still have difficulty choosing the right ones. That’s because font selection is based just as heavily on artistic license and emotional association as it is on technical issues. So, where do we begin?

 

In order to start your quest for the perfect font, you should first define the feelings you’re trying to evoke in your target audience. Are you trying to show that the company the website represents is hip and young, or would you rather portray an aura of steadfast wisdom? Do you want to create a site based on a certain theme, like a Hawaiian luau or a Mexican fiesta, or are you trying to convey a more formal identity? By asking yourself these kinds of questions, and thinking about fonts on an emotional level, you should be able to decide reasonably easily whether a given font is appropriate for your application.

 

If you’re unable to answer those questions about a particular font, make up your own questions. Take a look at the screenshot from [G'nosh](http://www.gnosh.co.uk/) in Figure 4.29. What questions do you think the designers of that site asked themselves as they were choosing the fonts for it? Obviously they were going for a handwritten feel, but why? I’m guessing they wanted to establish a brand that was as casual and approachable as possible.

 

![The casual and approachable G'nosh's website](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000132.jpg)

 

Figure 4.29. The casual and approachable G'nosh's website

 

Think about it, you’ve seen billions of letters and millions of words in your lifetime; so, whether you know it or not, you already have some emotional connections on which you can base your font choices. Think back to the logos, the album covers, the textbooks, and the signage you’ve seen. How have those typographic elements affected your perception of the entities they represent?

 

Now, let’s take that idea and work backwards, using a generic entity like Joe’s Restaurant. The font that you choose for this design will play a crucial role in the way potential diners perceive the attitude and identity of the restaurant. Take a look at Figure 4.30, and try to choose some fonts that make you think of a casual Italian bistro. Okay, now pick fonts that suggest a metropolitan restaurant serving five-star cuisine. How about a tacky dockside bar? There’s no right answer for any of these scenarios, but there are definitely some fonts that will outright fail to work in each case. First, try to narrow the field down to a few good candidates, and then try to refine your choices again, until you find one that works well.

 

![20 different fonts to make you want to eat at Joe’s](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000033.jpg)

 

Figure 4.30. 20 different fonts to make you want to eat at Joe’s

 

Remember that there are no bad fonts, just inappropriate ones. While a particular font might fail to work for one purpose, it may strike just the right chord in another situation. The trick is to try to keep an open mind. If you can narrow the field to a few possibilities, try asking a friend or co-worker the question, “Which one makes you feel more [adjective]?”, inserting the feeling you’re aiming to elicit.

 

Finally, when you’re choosing fonts, it’s important to limit your selection. As a rule of thumb, try to use at least two, but no more than four different fonts in a website design. Before incorporating a new font, remember that you probably have some variants (bold, italic, condensed, black, regular, and so on) at your disposal to vary your type while maintaining consistency. Try to also avoid combining two different serif fonts or two different sans-serif fonts in the same project. Like the discordant colors phenomenon I talked about in Chapter 2, placing different fonts from the same family next to each other in a design can feel eerily uncomfortable.

 

### Setting Font Size and Line Height

 

The size of text is—and always has been—a confusing topic. Over 300 years had elapsed in the history of printed type before the French typefounder Père Sébastien Truchet introduced the typographic point. Although points have been the standard units of measurement for typography ever since, the exact size of this_standard_unit has changed several times throughout history, due to differences between the English and French units of measurement. It was only with the onset of digital typography that the official size of the point was set to 1/72 of an inch.

 

Setting the size of text on the Web has had an equally shaky past. While the size of type in the print world is measured by points, the size of type on the Web is relative to the resolution of the viewer’s monitor and can be set in various types of units. The most popular units for setting text on the web are pixels, points, %, and ems. Without going too deeply into it, it’s easiest to say that 16px = 12pt = 100% = 1em. In CSS, the pixel (px) is the smallest—and best—relative unit for setting the size of text. Monitor resolution is set in pixels, as are the dimensions of all display graphics, so it makes sense to control text size with pixels, as well. So, why doesn’t everyone set web text sizes in pixels? Well, mainly because some browsers don’t allow text that’s set in pixels to be scaled. This is potentially an accessibility problem for users unable to read small text. I say it’s_potentially_a problem, because most browsers now give users the option to zoom the page rather than having to try to increase the font size. If you want to ensure that the text in your site is scalable as well as zoomable, you can set your text in ems.

 

Because I think in pixels, my current approach to setting font size and line height on the Web follows the logic of Wilson Miner’s 2007_A List Apart_article,[“Setting Type on the Web to a Baseline Grid.”](http://www.alistapart.com/articles/settingtypeontheweb) Like our vertical, column-based grids, a baseline grid is a set of equally spaced horizontal lines which your text should line up with. Following a baseline grid helps give your content a sense of rhythm instead of feeling arbitrarily placed. The main concept in Wilson’s article is that you remove the default margin and padding from all elements, set your `font-size` and `line-height` in the `body` element, then give all elements a `line-height` and a bottom margin that either matches or is a multiple of your `body` `line-height` . It sounds complicated, but it’s really quite easy.

 

### Using Punctuation and Special Characters

 

![The quotation mark key on a standard keyboard](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000011.jpg)

 

Figure 4.31. The quotation mark key on a standard keyboard

 

When you type text into any relatively modern word-processing program, you see nice “curly” opening and closing punctuation marks when you hit the double quotation marks key. Curly quotation marks can’t be found on your keyboard, as Figure 4.31 shows; however, word-processing programs understand that when you put words in quotes, you want nice left and right quotes, and it replaces the characters you typed in with the correct ones. The same goes with apostrophes. Have you ever seen an ASCII apostrophe like the one on your keyboard in a book or brochure? Of course not. What we usually see in printed material is a closing single quotation mark. In fact, a vast array of characters are unrepresented on a standard keyboard, even though these characters show up on web pages and in printed material.

 

Now, that’s all well and good for people using word processors. For those of us typing text into an HTML document, though, there’s no system to automatically replace the characters from our keyboards with the grammatically correct equivalents. Depending on which type of character encoding your website uses, when you paste these characters directly into an HTML document, you may see a bunch of gibberish on the rendered page. Additionally, the inclusion in text of characters that are used by HTML, like < and >, will wreak havoc in your page, as they’ll be interpreted as the beginning or ending of an HTML tag.

 

For these reasons, a series of special codes or **entities** has been created; we type these into our HTML documents to produce correct punctuation marks and just about any special character that we could need. The examples in Table 4.1 are just a sample of the many HTML character codes that exist. The code on the far left is known as an entity name or keyword. For instance, to produce a copyright symbol in your document, enter `©` directly into your HTML, and you’ll see a © in the rendered page. Each of these entities also has a numerical equivalent; for `©` it’s `#169` , so `©` will produce the same symbol. For a more complete list of codes and their alternative entity numbers, check out [W3Schools HTML entities page.](http://www.w3schools.com/tags/ref_entities.asp)

 

Table 4.1. Sample list of HTML character entity references 


Entity | Character | Description         
------ | --------- | --------------------
`<`    | <         | Less than           
`>`    | >         | Greater than        
`&`    | &         | Ampersand           
`‘`    | ‘         | Left single quote   
`’`    | ’         | Right single quote  
`“`    | “         | Left double quote   
`”`    | ”         | Right double quote  
`«`    | «         | Left angle quote    
`»`    | »         | Right angle quote   
`®`    | ®         | Registered trademark
`™`    | ™         | Trademark           
`©`    | ©         | Copyright           
`¢`    | ¢         | Cent                
`£`    | £         | Pound               
`¥`    | ¥         | Yen                 
`¼`    | ¼         | One-quarter         
`½`    | ½         | One-half            
`¾`    | ¾         | Three-quarters      

## ~~~Application: The Fine Print ~~~

 

Type is an important part of the Knoxville Reflexology Group logo. The typeface needed to be strong and have a bold presence, while being clean and friendly. The type uses a combination of Frutiger LT 45 Light and Frutiger LT 65 Bold. This combination of thick and thin typefaces gives a strong sense of contrast, but as both typefaces are from the same family, it helps to unify the logo.

 

![KRG typography in the logo](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000201.jpg)

 

Figure 4.32. KRG typography in the logo

 

For the headlines and body copy throughout the KRG site, is was important to chose a quality web font that was sans serif to maximize legibility, and to have a few different weights. Source Sans Pro Bold was used for the headlines and Source Sans Pro Light was selected for the body text. This is mainly because KRG wanted to maintain a modern, sleek look. The body text needed to have an open, inviting feel, so the line height was increased for legibility and to lighten the mood of the site.

 

The home page needed to draw the visitor in with the latest news, while offering other content to explore. It also needed to be informative, covering different procedures and providing price information. Certain elements, such as prices, could be made to stand out using special CSS classes dedicated just for those purposes. Headlines needed to be clean and bold, with contrasting supportive text.

 

![Source Sans Pro font used on body copy](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000117.jpg)

Figure 4.33. Source Sans Pro font used on body copy

 

The fonts themselves were implemented using `@font-face` , and the fonts are hosted at the site to provide maximum consistency. As you can see in Figure 4.34 below, the text has plenty of room to breathe. The menu has plenty of contrast, the news slider has a bold headline that gets your attention while making it easy to read. The text shadow in the callout box below the slider has a text shadow applied to it with CSS, which adds a slight variation to the rest of the layout.

 

![KRG case study home page KRG home page design](https://learnable-static.s3.amazonaws.com/premium/reeedr/books/the-principles-of-beautiful-web-design-3rd-edition/images/000157.jpg)

 

Figure 4.34. KRG home page design

 

We will take a look at the final details of the KRG site later. First, we need to learn about imagery: where to find it, what to look for, and how to make it rock your client’s socks off.

 

<sup>[7]</sup>If you’re unclear as to what this means, jump ahead to the section called “Typeface Distinctions” for an in-depth look at the different categories of fonts.

 

<sup>[8]</sup>Berkeley: New Riders, 2009

 

<!-- STYLES to be added  -->

<style>
  :root {
    --typescale: 1.25;
    /*the heading scaling factor relative to the <p>. ( h4 > h3 > h2 > h1). It's a 'type size ramp'.*/
    --baselineratio: calc(16/9);
    /* The 'line-height:basefont size' ratio ( i.e 16/9 = 1.777778)*/

    --basegrid: 32px;
    /* phone */
    --basegrid-tablet: 28px;
    --basegrid-laptop: 32px;
    --basegrid-wide: 36px;

    --baseline: calc(var(--baselineratio) * 1rem);
    /*--baseline: 1.7778 * 1rem;*/
    --basefont: calc(var(--basegrid) / var(--baselineratio));
    --basefont-tablet: calc(var(--basegrid-tablet) / var(--baselineratio));
    --basefont-laptop: calc(var(--basegrid-laptop) / var(--baselineratio));
    --basefont-wide: calc(var(--basegrid-wide) / var(--baselineratio));

    font-family: Roboto, sans-serif;
    font-weight: 300;
  }



  :root {
    /* DEFAULT - mobile */
    font-size: var(--basefont);
    line-height: var(--baseline);
  }

  /* The New Typography */

  h1,
  .is-size1 {
    font-size: calc(var(--typescale) * var(--typescale) * var(--typescale) * var(--typescale) * 1rem);
    line-height: calc(var(--baseline) * 2);
    /* 4 grid lines */
    margin-top: var(--baseline);
    margin-bottom: var(--baseline);
    font-weight: 400;
  }

  h2,
  .is-size2 {
    font-size: calc(var(--typescale) * var(--typescale) * var(--typescale) * 1rem);
    line-height: calc(var(--baseline) * 1.5);
    margin-top: 0rem;
    margin-bottom: calc(var(--baseline) / 2);
    font-weight: 400;
  }

  h3,
  .is-size-3,
  .h3 {
    font-size: calc(var(--typescale) * var(--typescale) * 1rem);
    line-height: calc(var(--baseline) * 1);
    margin-top: 0;
    margin-bottom: calc(var(--baseline) / 2);
    font-weight: 400;
  }

  h4,
  .is-size-h4 {
    font-size: calc(var(--typescale) * 1rem);
    line-height: calc(var(--baseline) * 1);
    margin-top: calc(var(--baseline) * 1);
    margin-bottom: calc(var(--baseline) * 1);
    font-weight: 400;
  }

  h5,
  .is-size-5 {
    font-size: 1rem;
    line-height: calc(var(--baseline) / 2);
    margin-top: calc(var(--baseline) / 2);
    margin-bottom: calc(var(--baseline) / 2);
    font-weight: 400;
  }

  p,
  ul,
  ol,
  pre,
  table,
  blockquote,
  .is-size-base {
    font-size: 1rem;
    font-weight: 400;
    margin-top: 0rem;
    line-height: calc(var(--baseline) / 1);
    margin-bottom: calc(var(--baseline) / 1);
  }

  .major {
    font-weight: 500;
    font-size: calc(var(--typescale) * var(--typescale) * var(--typescale) * var(--typescale) * var(--typescale) * 1rem);
    line-height: calc(var(--baseline) * 3);
  }

  .minor,
  figcaption {
    font-size: calc(1rem / var(--typescale));
    line-height: calc(var(--baseline) / 1);
    margin-top: 0;
    margin-bottom: calc(var(--baseline) / 1);
  }

  .small {
    font-size: calc(1rem / var(--typescale) / var(--typescale));
    line-height: calc(var(--baseline) / 2);
    margin-top: 0;
    margin-bottom: calc(var(--baseline) / 2);
  }

  ul ul,
  ol ol,
  ul ol,
  ol ul {
    margin-top: 0rem;
    margin-bottom: 0rem;
  }




  /* palette controls */

  ul.palette-ui {
    display: flex;
    margin: calc(var(--baseline) /2) 0 calc(var(--baseline) * 2);
  }

  ul.palette-ui li {
    color: #3c3c3c;
    display: inline-block;
    list-style: none;
    margin: 0 0em 0 3rem;
    padding: 0;
    position: relative;
    line-height: calc(var(--baseline) * 1.5);
  }

  ul.palette-ui li span {
    color: #333;
  }

  ul.palette-ui li::before {
    background-color: currentcolor;
    border-radius: 50%;
    content: "";
    width: 2rem;
    height: 2rem;
    border: 2px #f2f2f2 solid;
    position: absolute;
    top: calc(var(--baseline) * 0.25);
    left: -2.5rem
  }



  /* mini browser - c/o  Site Palette */
  .sitepreview {
    width: 100%;
    margin: calc(var(--baseline) / 2) 0;
  }

  .browser {
    width: 98%;
    margin: 0 auto;
    box-shadow: 0px 10px 40px -10px rgba(24, 65, 107, 0.35);
  }

  .browser__bar {
    height: calc(var(--baseline) / 1);
    background: #e7edf3;
    border-radius: 4px 4px 0 0;
    display: -webkit-flex;
    display: flex;
    justify-content: flex-end;
    padding: 7px 0 8px;
    position: relative;
    line-height: calc(var(--baseline) / 1);
    align-items: center;
  }

  .browser__dots,
  .browser__dots::after,
  .browser__dots::before {
    position: relative;
    width: 8px;
    height: 8px;
    background: #c7d1da;
    border-radius: 50%;
    margin-right: 5%;
  }

  .browser__dots::after,
  .browser__dots::before {
    margin: 0;
    position: absolute;
    content: '';
  }

  .browser__dots::after {
    right: 13px;
  }

  .browser__dots::before {
    left: 13px;
  }

  .browser__address {
    width: 86%;
    margin-right: 2%;
    height: 100%;
    background: rgba(0, 0, 0, 0.03);
    border-radius: 3px;
    white-space: nowrap;
    font-size: 9px;
    line-height: calc(var(--baseline) / 2);
    padding-left: 10px;
    color: #96abb7;
    text-overflow: ellipsis;
    overflow: hidden;
    padding-right: 5px;
  }

  .browser__address a {
    text-decoration: none;
    color: #96abb7;
    transition: all ease 0.3s;
  }

  .browser__body {
    border-radius: 0 0 4px 4px;
    overflow: scroll;
    max-height: 280px;
    max-height: 16vw;
    min-height: calc(var(--baseline) * 13);
  }

  .browser__image {
    max-width: 100%;
  }

  /* Hackmd.io-specific layout hack */
  .markdown-body figure {
    margin: 0;
  }
</style>