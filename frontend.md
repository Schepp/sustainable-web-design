## Frontend

---

![](./images/Venn%20diagram.svg)

A performant website is an eco-friendly website

---

### Reduce page weight

---

<iframe title="Median page weight over time." class="fig-iframe" tabindex="-1" width="600" height="371" seamless="" frameborder="0" scrolling="no" loading="lazy" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vS-yCXlRH7TMaQg1T2YsESIiUNe4BSga5NWwEElHgU3ZaNLXNauwAxsn3k_el5v1fxvtc_YA5k9i689/pubchart?oid=1631675184&amp;format=interactive"></iframe>

---

<iframe title="Median page weight by content type." class="fig-iframe" tabindex="-1" width="600" height="371" seamless="" frameborder="0" scrolling="no" loading="lazy" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vS-yCXlRH7TMaQg1T2YsESIiUNe4BSga5NWwEElHgU3ZaNLXNauwAxsn3k_el5v1fxvtc_YA5k9i689/pubchart?oid=1961492622&amp;format=interactive"></iframe>

---

### Use a better image format

---

![](./images/Compression-comparison-of-image-formats.svg)

[Image Format Comparison (JPEG, PNG, WEBP, & AVIF) - 2023 Statistics](https://photutorial.com/image-format-comparison-statistics/)

---

<div class="r-hstack">

![](./images/Netflix%20JPG.webp)  
JPEG @ 69,445 bytes

![](./images/Netflix%20AVIF.webp)  
AVIF @ 40,811 bytes

</div>

[AVIF for Next-Generation Image Coding](https://netflixtechblog.com/avif-for-next-generation-image-coding-b1d75675fe4)

---

### AVIF is not always the best choice

<table>
  <thead>
  <tr>
    <th scope="col"><strong><em>Feature</em></strong></th>
    <th scope="col"><strong><em>JPEG</em></strong></th>
    <th scope="col"><strong><em>WebP</em></strong></th>
    <th scope="col"><strong><em>AVIF</em></strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
    <td>Alpha transparency</td>
    <td>❌</td>
    <td>✅</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>HDR</td>
    <td>❌</td>
    <td>❌</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>Effective lossless compression</td>
    <td>❌</td>
    <td>✅</td>
    <td>❌</td>
  </tr>
  <tr>
    <td>Progressive decoding</td>
    <td>✅</td>
    <td>❌</td>
    <td>❌</td>
  </tr>
  <tr>
    <td>Animation</td>
    <td>❌</td>
    <td>✅</td>
    <td>✅</td>
  </tr>
  </tbody>
</table>

![](./images/Decoding%20and%20Rendering%20Speed%20combined.avif) <!-- .element style="height: 15vh; width: 70%; object-fit: cover; object-position: top center;" -->  
![](./images/Image%20decoding%20legend.png) <!-- .element style="height: 5vh" -->

---

### What about the formats' energy consumptions?

---

Overall loading & decode energy consumption - the longer the network is active the more energy is consumed.

![](./images/Greenspector%20image%20test.png)

[Which image format choose to reduce energy consumption and environmental impact?](https://greenspector.com/en/which-image-format-to-choose-to-reduce-its-energy-consumption-and-its-environmental-impact/)

---

Energy consumption for decoding alone

![](./images/Greenspector%20image%20decoding%20energy.png)

[Which image format choose to reduce energy consumption and environmental impact?](https://greenspector.com/en/which-image-format-to-choose-to-reduce-its-energy-consumption-and-its-environmental-impact/)

---

### Reduce JavaScript

---

JavaScript hits the CPU multiple times:

![](./images/JavaScript%20parse%20and%20compile.avif)

* First with parse & compile costs, 
* then with its execution cost. 

[JavaScript Startup Optimization](https://web.dev/optimizing-content-efficiency-javascript-startup-optimization/)

---

Byte for byte, JavaScript hits a lot harder than image data.

![](./images/JavaScript%20vs%20Image.avif)

[JavaScript Startup Optimization](https://web.dev/optimizing-content-efficiency-javascript-startup-optimization/)

---

![](./images/w3c-no-bars%20(1).svg)

> Use the least powerful language suitable for expressing information, constraints or programs on the World Wide Web

[W3C - The Rule of Least Power](https://www.w3.org/2001/tag/doc/leastPower.html)

---

![](./images/Whats%20new%20in%20CSS%20and%20UI.avif) <!-- .element style="height: 25vh" -->

> The past few months have ushered in a golden era for web UI. New platform capabilities have landed with tight cross-browser adoption that support more web capabilities and customization features than ever.

[What's new in CSS and UI: I/O 2023 Edition](https://developer.chrome.com/blog/whats-new-css-ui-2023/)

---

### HTML > CSS > JavaScript

* ~Resize Observer~ CSS Container Queries
* ~Styled Components~ CSS Scoped styles
* ~`Math`~ CSS Trigonometric functions
* ~popper.js~ HTML `popover` & CSS anchor positioning
* ~Vue.js Transition~ View Transition API
* ~Select2~ `<selectmenu>`
* ~Greensock~ Scroll-driven animations

**Stay up to date with the Web Platform!**

---

![](./images/scroll%20driven%20animations%20main%20thread.avif)

[A case study on scroll-driven animations performance](https://developer.chrome.com/en/blog/scroll-animation-performance-case-study/)



* Transfer Volume
* CPU HTML > CSS > JS
* GPU image formats
* Screen OLED
* SPA vs. HTMx vs. SSR
* Old devices obsolete
