# Reducing Energy Consumption

---

These aspects of digital products impact energy consumption:

* 📦 Data transport
* ⚙️Logic / data processing
* 🖥️ Displaying

---

**1 Gigabyte** of data transferred uses **0.81 kWh** of energy.

<div class="r-hstack">

![](./images/system-boundaries-swd-style.png) <!-- .element style="height: 25vh" -->

<div style="align-self: center; text-align: left">

This factors in: 

* consumer device use, 
* network use, 
* data center use and 
* hardware production.

</div>
</div>

[Calculating Digital Emissions](https://sustainablewebdesign.org/calculating-digital-emissions/)

**Disclaimer: Amount of data transferred is still just an approximation for energy consumption.** <!-- .element class="fragment" -->

---

![](./images/Eletricity%20Maps%20Germany.png) <!-- .element: style="border: 1px solid #ccc" -->

Producing **1 kWh** of energy in Germany created **372g CO²** on average 
in 2023.

[Electricity Maps](https://app.electricitymaps.com/zone/DE)

---

### Carbon Footprint of Data in Germany

1 Gigabyte = 0.81 kWh &times; 372g CO² = **301g CO²**

1 Megabyte = **0.30g CO²**

---

![](./images/Fritzbox.png) <!-- .element: style="border: 1px solid #ccc" -->

Our household's **data consumption** in one month: **1,323 Gigabytes**.

---

![](./images/Plane.jpg)

Our household's **digital carbon footprint** in one month: **398 kg** CO².

That's **[like traveling 1,666 km by plane](https://www.quarks.de/umwelt/klimawandel/CO2-rechner-fuer-auto-flugzeug-und-co/)** every month.

---

## Average Page Weight

![](./images/median-page-weight-over-time.png)

[Web Almanac](https://almanac.httparchive.org/en/2022/page-weight)

---

### Measuring the Footprint of a Webpage

---

![](./images/network%20tab%20summary.png) <!-- .element: style="border: 1px solid #ccc" -->

Network Tab in Devtools

---

<iframe src="https://www.websitecarbon.com/website/greenpeace-de/" style="width: 100%; height: 50vh"></iframe>

[Website Carbon Calculator](https://www.websitecarbon.com/)

---

![](./images/Webpagetest%20Carbon%20Control.png)

[Measure & Improve Your Site's Footprint with Carbon Control from Catchpoint WebPageTest](https://blog.webpagetest.org/posts/carbon-control/)

---

The main offender...

---
<!-- .slide: data-transition="fade" -->

![](./images/median-page-weight-by-content-type.png)

[Web Almanac](https://almanac.httparchive.org/en/2022/page-weight)

---
<!-- .slide: data-transition="fade" -->

![](./images/median-page-weight-by-content-type-images.png)

[Web Almanac](https://almanac.httparchive.org/en/2022/page-weight)

---

### Use a better Image Format

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

### What about the formats' energy consumptions?

---

Overall loading & decode energy consumption (shorter is better)  
The longer the network is active the more energy is consumed

![](./images/Greenspector%20image%20test.png) <!-- .element style="height: 33vh" -->

[Which image format choose to reduce energy consumption and environmental impact?](https://greenspector.com/en/which-image-format-to-choose-to-reduce-its-energy-consumption-and-its-environmental-impact/)

---

Energy consumption for decoding alone (shorter is better)

![](./images/Greenspector%20image%20decoding%20energy.png) <!-- .element style="height: 33vh" -->

[Which image format choose to reduce energy consumption and environmental impact?](https://greenspector.com/en/which-image-format-to-choose-to-reduce-its-energy-consumption-and-its-environmental-impact/)

---

Throuput for encoding (higher is better)

![](./images/Single_Threaded_TranscodeMPs_vs_Effort_SlowDefFast_900w.png)

[Coding Comparisons](https://storage.googleapis.com/avif-comparison/subset1.html)

---

### The Winner Formats: AVIF & WebP!

---

Next big offender...

---

JavaScript!

![](./images/median-page-weight-by-content-type-javascript.png)

[Web Almanac](https://almanac.httparchive.org/en/2022/page-weight)

---

JavaScript **hits us multiple times**:

![](./images/JavaScript%20parse%20and%20compile.avif)

* First the **network** with its **download**
* then the **CPU** with **parse & compile** costs,
* and finally the **CPU** again with its **execution** costs.

[JavaScript Startup Optimization](https://web.dev/optimizing-content-efficiency-javascript-startup-optimization/)

---

Byte for byte, **JavaScript hits a lot harder** than image data.

![](./images/JavaScript%20vs%20Image.avif)

[JavaScript Startup Optimization](https://web.dev/optimizing-content-efficiency-javascript-startup-optimization/)

---

### Can I measure the energy impact of my JavaScript?

---

**Safari** was the first browser to introduce tooling that measures energy impact.

![](./images/Safari%20energy%20consumption.webp) <!-- .element style="height: 25vh" -->

It primarily focuses on CPU and is **directionally useful**, but doesn’t offer any specific numbers.

---

Recently **Firefox** added **REAL** energy consumption profiling to its devtools!

![](./images/Firefox%20energy%20profiler.webp) <!-- .element: style="height: 25vh" -->

[Measuring website energy consumption via browser profiling](https://www.devsustainability.com/p/measuring-website-energy-consumption) / [Power profiling with the Firefox Profiler](https://fosdem.org/2023/schedule/event/energy_power_profiling_firefox/)

---
![](./images/Angular%20Reatc%20Vue.webp)

React, Angular and Vue.js are all great, but...

---

### They eat a lot of CPU cycles on the client!

![](./images/perf-planet-react-signal.png) <!-- .element: style="height: 20vh; background: #141212" -->

> rendering a simple &lt;span&gt; in React [...] is between 2.15M to 2.2M CPU instructions. Then wrapping the &lt;span&gt; in a &lt;p&gt; takes us to about 2.3M instructions.

[JavaScript component-level CPU costs](https://calendar.perfplanet.com/2019/javascript-component-level-cpu-costs/)

---

As **you are not in control of the carbon footprint of your visitors**, but in control of your server try **moving logic back to it**.

<div class="r-hstack">

![](./images/spa-web-app-architecture-diagram.webp)

👉🏼 <!-- .element style="align-self: center" -->

![](./images/ssr-web-app-architecture-diagram-1.webp)

</div>

Source: [mobidev.biz](https://mobidev.biz/blog/web-application-architecture-types)

---

If you need a lot of interactivity, consider a **"HTML Over the Wire"** approach.

<div class="r-logos">

![](./images/hotwire-logo.svg) <!-- .element: style="height: 2vh" -->

![](./images/laravel-livewire-logo.svg) <!-- .element: style="height: 2vh" -->

![](./images/htmx-logo.svg) <!-- .element: style="height: 2vh" -->

![](./images/unpoly_logo.svg) <!-- .element: style="height: 2vh" -->

</div>

<div class="r-hstack" style="align-items: center">

![](./images/draw_spa.png)<br>SPA

vs. <!-- .element style="align-self: center" -->

![](./images/draw_html_over_the_wire-1.png)<br>HTML over the Wire

</div>

---

Speaking of Servers, Backend, and maybe even Build Pipelines...

---

If you've already written the most efficient code and tuned your infrastructure to the max... 

---

Maybe switch to a more efficent language? 

## Certain server-Side Languages are more efficient than others

---

![](./images/Programming%20Languages.png) <!-- .element: style="height: 20vh" -->

Researchers ran energy tests of 27 programming languages, using standardized algorithmic problems from a project called the ["Computer Language Benchmarks Game"](https://benchmarksgame-team.pages.debian.net/benchmarksgame/)

[Energy Efficiency across Programming Languages (2017)](https://greenlab.di.uminho.pt/wp-content/uploads/2017/10/sleFinal.pdf)

---

![](./images/Efficiency%20of%20programming%20languages.png) <!-- .element: style="height: 33vh" -->

**Compiled languages fare hugely better** than interpreted languages  
(with the exception of Java & JavaScript)


---

Also: The **less transformation layers** in your stack the better.

![](./images/Container%20performance.webp) <!-- .element: style="height: 33vh" -->

<small>SSVM = Second State WebAssembly VM = Runs (Rust code compiled to) WebAssembly</small>

[Evaluation of software stack performance](https://www.infoq.com/articles/arm-vs-x86-cloud-performance/#:~:text=on%20GitHub.-,Less%20software%20bloat,-To%20preserve%20software)

---

## Choose more energy efficient hardware

![](./images/Arm%20vs%20x86.png) <!-- .element: style="height: 25vh" -->

> ARM processors are designed to have the lowest possible energy consumption while maintaining high processing power.

[The next big thing – ARM architecture](https://www.layerstack.com/blog/the-next-big-thing-arm-architecture/)

---

Let your next **development machine** be a Mac!  
(or a "Snapdragon X" laptop for that matter)

![](./images/Apple%20Macbook.jpg) <!-- .element: style="height: 15vh" -->

And think about ARM-based **servers**, too, which you can get here:

* [Hetzner](https://www.golem.de/news/cloud-hosting-hetzner-vermietet-kleinere-und-guenstigere-arm-server-2304-173366.html)
* [CloudFlare](https://blog.cloudflare.com/designing-edge-servers-with-arm-cpus/)
* [Amazon EC2](https://aws.amazon.com/de/ec2/graviton/)
* [Google Cloud](https://cloud.google.com/compute/docs/instances/arm-on-compute)
* [Microsoft Azure](https://azure.microsoft.com/en-us/blog/azure-virtual-machines-with-ampere-altra-arm-based-processors-generally-available/)

---

## Finally: Let's talk about Displays

---

### OLEDs vs LCDs

![](./images/OLED%20vs%20LCD.jpg) <!-- .element: style="width: auto; height: 33vh" -->

**OLEDs use self-illuminating pixels**. 

Therefore only bright pixels consume energy.

---

![](./images/amoled.jpg)

OLEDs **are very efficient in showing dark images**. 

They **are less efficient at displaying white images**. 

However, the white images an OLED can display are of higher quality and brightness, but in doing so, this requires more energy consumption than LCD.

[Battery Power Online](https://www.batterypoweronline.com/news/oled-displays-impact-on-battery-life-for-consumer-tech-devices/)

---

![](./images/OLED-Penetation-in-Smartphones-Chart-jpg.webp) <!-- .element: style="height: 33vh" -->

OLED Displays in Smartphones Reach 49% Global Market Share in Q1’23

[Display Daily](https://displaydaily.com/oled-displays-in-smartphones-reach-49-global-market-share-in-q123/)

---

![](./images/android-12-pixel-lock-screen-clock.avif)

Increased OLED use is the reason we have more and more "always on" lock screens.

---

### OLEDs love Dark Mode!

![](./images/Google%20Maps%20Darkmode.png)

[Android Dev Summit 2018](https://www.youtube.com/watch?v=N_6sPd0Jd3g)

---

![](./images/Wikipedia%20Dark%20Mode.jpg)

Make Dark Mode the default!

---

## Energy Cost of Color

---

![](./images/Power%20per%20pixel%20color.png) <!-- .element: style="height: 33vh" -->

With OLED screens, **blue color consumes up to 24% more energy** than green or red.

[Android Dev Summit 2018](https://www.youtube.com/watch?v=N_6sPd0Jd3g)

---

![](./images/Power%20per%20max%20brightness%20pixel%20color.png)

[Android Dev Summit 2018](https://www.youtube.com/watch?v=N_6sPd0Jd3g)

---

![](./images/Color%20wavelengths.jpg) <!-- .element: style="width: auto; height: 25vh" -->

> **Higher frequencies contain more energy** at the same amplitude.
>
> Blue light has a **shorter wavelength** than red or green.

[Quora](https://www.quora.com/Why-do-certain-colors-like-blue-consume-more-energy-on-a-screen-than-red-and-green/answer/Per-Westermark-1)

---

<div class="r-hstack">

![](./images/Conrad%20LED%20rot.png) <!-- .element: style="width: auto; height: 25vh" -->

![](./images/Conrad%20LED%20blau.png) <!-- .element: style="width: auto; height: 25vh" -->

</div>

> If you look at LED, a red LED might need 1.6V while a green may need 2.2V and a blue LED may need 3V.

[Quora](https://www.quora.com/Why-do-certain-colors-like-blue-consume-more-energy-on-a-screen-than-red-and-green/answer/Per-Westermark-1)

---

### Use energy efficient Color Palettes

<div class="r-vstack" style="gap: 0"><div class="r-hstack" style="gap: 0">

![](./images/color_palette_flowerblossom.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

![](./images/color_palette_lush.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

</div><div class="r-hstack" style="gap: 0">

![](./images/color_palette_passionfruit.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

![](./images/color_palette_summertime.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

</div></div>

[Energy efficient color palette ideas](https://greentheweb.com/energy-efficient-color-palette-ideas/)





