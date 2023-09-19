# web-dev-resources
My guide for some web dev resources, which helps in day-to-day web development practices.

## Browser Fundamentals
### Browsers with their Engines

| Browser       | Browser Engine                  | JS Engine |
|---------------|---------------------------------|-----------|
| Google Chrome | Blink                           | V8 (C++)  |
| Mozilla       | Gecko                           | SpiderMonkey | 
| Safari        | Webkit                          | JavascriptCore |  
| Edge          | Blink (Edge is Chromium based)  | V8 (From Chromium) |

#### Timeline of the the development of the Browser engines, which is when the new Web standards were being implemented in the engine.
![Timeline](https://upload.wikimedia.org/wikipedia/en/timeline/glana2o0f7cziybkkmx2fgelmo287vj.png)

* **Blink** is a fork of the WebCore component of WebKit, which origininally is a fork of KHTML and KJS libraries from KDE.
* For iOS platform, all the web browsers must you Apple's webkit to implement any kind of webview/browser.
* **Blink's** naming was influenced by a combination of two major factors: the **connotations of speed**, and a **reference to the non-standard presentational blink HTML element**, which was introduced by Netscape Navigator and supported by Presto (Opera's browser engine implementation) and Gecko-based browsers until August 2013. Blink has, contrary to its name, never functionally supported the element, you can see why here: ![Blink tag functionality](https://miro.medium.com/v2/resize:fit:430/0*I9Rl7iW4N_cEHk_D.gif) Such an annoying tag.
* Edge used **EdgeHTML** is the beginning, but then eventually they shifted to Blink recently.
* **Trident** was the engine used in Internet Explorer.

#### Reference Links
[https://en.wikipedia.org/wiki/Comparison_of_browser_engines](https://en.wikipedia.org/wiki/Comparison_of_browser_engines)

### What is ```text-rendering: auto | optimizeSpeed | optimizeLegibilty | geometricPrecision``` ?
It is a SVG specific property, but browser engines let you apply this on HTML elements also.
The ```text-rendering``` CSS property provides information to the rendering engine about what to optimize for when rendering text.
* ```auto```: The browser makes educated guesses about when to optimize for speed, legibility, and geometric precision while drawing text.
* ```optimizeSpeed```: The browser emphasizes rendering speed over legibility and geometric precision when drawing text. It disables kerning and ligatures.
* ```optimizeLegibility```: The browser emphasizes legibility over rendering speed and geometric precision. This enables kerning and optional ligatures.
* ```geometricPrecision```: In SVG, when text is scaled up or down, browsers calculate the final size of the text (which is determined by the specified font size and the applied scale) and request a font of that computed size from the platform's font system. But if you request a font size of, say, 9 with a scale of 140%, the resulting font size of 12.6 doesn't explicitly exist in the font system, so the browser rounds the font size to 12 instead. This results in stair-step scaling of text.

But the geometricPrecision property — when fully supported by the rendering engine — lets you scale your text fluidly. For large scale factors, you might see less-than-beautiful text rendering, but the size is what you would expect—neither rounded up nor down to the nearest font size supported by Windows or Linux.

### What is ```font-synthesis: auto | none | weight | style``` ?
The ```font-synthesis``` property in CSS is used to control how font rendering should be synthesized when a specific ```font-weight``` or ```font-style``` is not available for a given text element. It's primarily used to ensure that text remains legible even when the exact desired font variation is not present.
  * ```auto```: If ```font-weight``` is 700 (bold) is encountered and the font-family used is not having the bold styles, then the browser will try to syntesise 700 boldness at its own.
  * ```none```: This value disables font synthesis entirely. If a requested font weight or style is not available, the browser will use the closest available font instead without any synthesis.
  * ```weight```: This states that ```font-synthesis``` would only be limited to weight only. The browser would not synthesis *italic* or *oblique* styles on its own.
  * ```style```: This states that ```font-synthesis``` would only be limited to style only. The browser would not synthesis ```font-weight``` styles on its own.

### What is ```-webkit-font-smoothing: none | subpixel-antialiased | antialiased``` ?

#### Reference Links
* [Antialiasing 101](https://web.dev/antialiasing-101/)

### What is ```-webkit-text-size-adjust: 0-100%``` ?
* It is a non standard CSS property -webkit-text-size-adjust that is used to control how text is scaled when a user zooms in or out on a web page. It's often used to prevent the automatic adjustment of font sizes when users zoom in on a webpage, ensuring that the text remains at its original size.
* Typically used on body element like ```body { -webkit-text-size-adjust: 100% }```
* It's use is becoming less and less relevant, due to the rise of the modern techniques for responsive design and handling zooming are employed, such as using relative units like em and rem for font sizes and media queries for responsive layouts.
* It is vendore specific tag and may not work everywhere.

## Links
* [Flex Playground (Codepen)](https://codepen.io/daxter-army/pen/WNZQWGL)
* [Flex Cheatsheet](https://yoksel.github.io/flex-cheatsheet/)
* [React-Hooks Cheatsheet](https://react-hooks-cheatsheet.com/)
