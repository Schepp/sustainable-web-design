# Reduktion des Energieverbrauchs

---

Folgende Teilbereiche digitaler Produkte wirken sich auf den Energieverbrauch aus:

* 📦 Datentransport
* ⚙️Logik/Datenverarbeitung
* 🖥️ Anzeige

---

**1 Gigabyte** übertragener Daten verbrauchen **0,81 kWh** an Energie.

<div class="r-hstack">

![](./images/system-boundaries-swd-style.png) <!-- .element style="height: 25vh" -->

<div style="align-self: center; text-align: left">

Dabei werden berücksichtigt:

* Nutzung von Verbrauchergeräten,
* Netzwerknutzung,
* Nutzung von Rechenzentren und
* Hardwareproduktion.

</div>
</div>

[Berechnung digitaler Emissionen](https://sustainablewebdesign.org/calculating-digital-emissions/)

**Hinweis: Die übertragene Datenmenge ist immer noch nur eine Annäherung an den Energieverbrauch.** <!-- .element class="fragment" -->

---

![](./images/Eletricity%20Maps%20Germany.png) <!-- .element: style="border: 1px solid #ccc" -->

Bei der Produktion von **1 kWh** Energie in Deutschland wurden im Jahr 2023 durchschnittlich **372 g CO²** erzeugt.

[Electricity Maps](https://app.electricitymaps.com/zone/DE)

---

### CO2-Fußabdruck von Daten in Deutschland

1 Gigabyte = 0,81 kWh &times; 372g CO² = **301g CO²**

1 Megabyte = **0,30g CO²**

---

![](./images/Fritzbox.png) <!-- .element: style="border: 1px solid #ccc" -->

Der **Datenverbrauch** unseres Haushalts in einem Monat: **1.323 Gigabyte**.

---

![](./images/Plane.jpg)

Der **digitale CO²-Fußabdruck** unseres Haushalts in einem Monat: **398 kg** CO².

Das entspricht **[einer monatlichen Flugreise von 1,666 km](https://www.quarks.de/umwelt/klimawandel/CO2-Rechner-fuer-auto-flugzeug-und-co/)**.

---

## Durchschnittliche Größe einer Webseite

![](./images/median-page-weight-over-time.png)

[Web Almanac](https://almanac.httparchive.org/en/2022/page-weight)

---

### Den Fußabdruck einer Webseite messen

---

![](./images/network%20tab%20summary.png) <!-- .element: style="border: 1px solid #ccc" -->

Registerkarte „Netzwerk“ in Devtools

---

<iframe src="https://www.websitecarbon.com/website/greenpeace-de/" style="width: 100%; height: 50vh"></iframe>

[Website Carbon Calculator](https://www.websitecarbon.com/)

---

![](./images/Webpagetest%20Carbon%20Control.png)

[Carbon Control von Catchpoint WebPageTest](https://blog.webpagetest.org/posts/carbon-control/)

---

Der Hauptschuldige...

---
<!-- .slide: data-transition="fade" -->

![](./images/median-page-weight-by-content-type.png)

[Web Almanach](https://almanac.httparchive.org/en/2022/page-weight)

---
<!-- .slide: data-transition="fade" -->

![](./images/median-page-weight-by-content-type-images.png)

[Web Almanach](https://almanac.httparchive.org/en/2022/page-weight)

---

### Bessere Bildformate verwenden

---

![](./images/Compression-comparison-of-image-formats.svg)

[Bildformatvergleich (JPEG, PNG, WEBP und AVIF) – Statistiken für 2023](https://photutorial.com/image-format-comparison-statistics/)

---

<div class="r-hstack">

![](./images/Netflix%20JPG.webp)
JPEG @ 69.445 Bytes

![](./images/Netflix%20AVIF.webp)
AVIF @ 40.811 Bytes

</div>

[AVIF for Next-Generation Image Coding](https://netflixtechblog.com/avif-for-next-generation-image-coding-b1d75675fe4)

---

### Wie sieht es mit dem Energieverbrauch der Formate aus?

---

Gesamtenergieverbrauch für das Laden und Dekodieren

Je länger das Netzwerk aktiv ist, desto mehr Energie wird verbraucht

![](./images/Greenspector%20image%20test.png) <!-- .element style="height: 33vh" -->

[Which image format choose to reduce energy consumption and environmental impact?](https://greenspector.com/en/which-image-format-to-choose-to-reduce-its-energy-consumption-and-its-environmental-impact/)

---

Energieverbrauch allein für die Dekodierung (je kürzer, desto besser)

![](./images/Greenspector%20image%20decoding%20energy.png) <!-- .element style="height: 33vh" -->

[Which image format choose to reduce energy consumption and environmental impact?](https://greenspector.com/en/which-image-format-to-choose-to-reduce-its-energy-consumption-and-its-environmental-impact/)

---

Durchsatz beim Encodierung (höher ist besser)

![](./images/Single_Threaded_TranscodeMPs_vs_Effort_SlowDefFast_900w.png)

[Coding Comparisons](https://storage.googleapis.com/avif-comparison/subset1.html)

---

### Die Gewinnerformate: AVIF & WebP!

---

Nächster großer Übeltäter...

---

JavaScript!

![](./images/median-page-weight-by-content-type-javascript.png)

[Web Almanac](https://almanac.httparchive.org/en/2022/page-weight)

---

JavaScript **beutelt uns mehrfach**:

![](./images/JavaScript%20parse%20and%20compile.avif)

* Zuerst das **Netzwerk** mit seinen **Download**
* dann die **CPU** mit **Parse & Compile**-Kosten,
* und schließlich erneut die **CPU** bei der **Programmcode-Ausführung**

[JavaScript Startup Optimization](https://web.dev/optimizing-content-efficiency-javascript-startup-optimization/)

---

JavaScript ist deutlich anspruchsvoller als Bilder.

![](./images/JavaScript%20vs%20Image.avif)

[JavaScript Startup Optimization](https://web.dev/optimizing-content-efficiency-javascript-startup-optimization/)

---

### Kann ich den Energieverrbrauch meines JavaScript messen?

---

**Safari** war der erste Browser, der Werkzeuge zur Messung der Energieauswirkungen einführte.

![](./images/Safari%20energy%20consumption.webp) <!-- .element style="height: 25vh" -->

Es konzentriert sich hauptsächlich auf die CPU und gibt **grobe Anhaltspunkte**, bietet aber keine konkreten Zahlen.

---

Kürzlich hat **Firefox** seinen Devtools **ECHTE** Profile zum Energieverbrauch hinzugefügt!

![](./images/Firefox%20energy%20profiler.webp) <!-- .element: style="height: 25vh" -->

[Measuring website energy consumption via browser profiling](https://www.devsustainability.com/p/measuring-website-energy-consumption) / [Power profiling with the Firefox Profiler](https://fosdem.org/2023/schedule/event/energy_power_profiling_firefox/)

---
![](./images/Angular%20Reatc%20Vue.webp)

React, Angular und Vue.js sind alle großartig, aber...

---

### Sie verbrauchen eine Menge CPU-Zyklen auf dem Client!

![](./images/perf-planet-react-signal.png) <!-- .element: style="height: 20vh; background: #141212" -->

> Das Rendern eines einfachen &lt;span&gt; in React [...] umfasst zwischen 2,15 und 2,2 Millionen CPU-Anweisungen. Wenn wir dann das &lt;span&gt; in ein &lt;p&gt; einschließen, kommen wir auf etwa 2,3 Millionen Anweisungen.

[JavaScript component-level CPU costs](https://calendar.perfplanet.com/2019/javascript-component-level-cpu-costs/)

---

Da **wir keine Kontrolle über den CO2-Fußabdruck unserer Besucher haben**, wohl aber über den unserer Server, sollten wir versuchen, **die Programmlogik dorthin zurückzuverlagern**.

<div class="r-hstack">

![](./images/spa-web-app-architecture-diagram.webp)

👉🏼 <!-- .element style="align-self: center" -->

![](./images/ssr-web-app-architecture-diagram-1.webp)

</div>

Quelle: [mobidev.biz](https://mobidev.biz/blog/web-application-architecture-types)

---

Wenn wir viel Interaktivität benötigen, könnten wir einen **„HTML Over the Wire“**-Ansatz in Betracht ziehen.

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

Apropos Server, Backend und vielleicht sogar Build-Pipelines...

---

Wenn wir bereits den effizientesten Code geschrieben und unsere Infrastruktur maximal optimiert haben...

---

Vielleicht auf eine effizientere Sprache umsteigen?

## Bestimmte serverseitige Sprachen sind effizienter als andere

---

![](./images/Programming%20Languages.png) <!-- .element: style="height: 20vh" -->

Forscher führten Energietests von 27 Programmiersprachen durch und verwendeten dabei standardisierte algorithmische Probleme aus einem Projekt namens ["Computer Language Benchmarks Game"](https://benchmarksgame-team.pages.debian.net/benchmarksgame/)

[Energieeffizienz in verschiedenen Programmiersprachen](https://greenlab.di.uminho.pt/wp-content/uploads/2017/10/sleFinal.pdf)

---

![](./images/Efficiency%20of%20programming%20languages.png) <!-- .element: style="height: 33vh" -->

**Kompilierte Sprachen schneiden enorm ab besser** als interpretierte Sprachen
(mit Ausnahme von Java und JavaScript)

---

Außerdem: Je **weniger Transformationsebenen** (à la Docker) im eigenen Stack, desto besser.

![](./images/Container%20performance.webp) <!-- .element: style="height: 33vh" -->

<small>SSVM = Second State WebAssembly VM = Führt (Rust-Code kompiliert zu) WebAssembly aus</small>

[Bewertung der Leistung des Software-Stacks](https://www.infoq.com/articles/arm-vs-x86-cloud-performance/#:~:text=on%20GitHub.-,Less%20software%20bloat,-To%20preserve%20software)

---

## Energieeffizientere Hardware

![](./images/Arm%20vs%20x86.png) <!-- .element: style="height: 25vh" -->

> ARM-Prozessoren sind so konzipiert, dass sie bei gleichbleibend hoher Verarbeitungsleistung den geringstmöglichen Energieverbrauch haben.

[The next big thing – ARM architecture](https://www.layerstack.com/blog/the-next-big-thing-arm-architecture/)

---

Die nächste **Entwicklungsmaschine** könnte ein Mac sein!
Oder auch ein „Snapdragon X“-Laptop!    

![](./images/Apple%20Macbook.jpg) <!-- .element: style="height: 15vh" -->

Es gibt auch ARM-basierte **Server**, die man u.a. hier bekommen kann:

* [Hetzner](https://www.golem.de/news/cloud-hosting-hetzner-vermietet-kleinere-und-guenstigere-arm-server-2304-173366.html)
* [CloudFlare](https://blog.cloudflare.com/designing-edge-servers-with-arm-cpus/)
* [Amazon EC2](https://aws.amazon.com/de/ec2/graviton/)
* [Google Cloud](https://cloud.google.com/compute/docs/instances/arm-on-compute)
* [Microsoft Azure](https://azure.microsoft.com/en-us/blog/azure-virtual-machines-with-ampere-altra-arm-based-processors-generally-available/)

---

## Reden wir über Displays

---

### OLEDs vs. LCDs

![](./images/OLED%20vs%20LCD.jpg) <!-- .element: style="width: auto; height: 33vh" -->

**OLEDs verwenden selbstleuchtende Pixel**.

Dementsprechend verbrauchen nur helle Pixel Energie.

---

![](./images/amoled.jpg)

OLEDs **sind sehr effizient bei der Anzeige dunkler Bilder**.

Sie **sind weniger effizient bei der Anzeige weißer Bilder**.

Die weißen Bilder, die ein OLED anzeigen kann, sind jedoch von höherer Qualität und Helligkeit, verbrauchen dabei aber mehr Energie als LCDs.

[Battery Power Online](https://www.batterypoweronline.com/news/oled-displays-impact-on-battery-life-for-consumer-tech-devices/)

---

![](./images/OLED-Penetation-in-Smartphones-Chart-jpg.webp) <!-- .element: style="height: 33vh" -->

OLED-Displays in Smartphones erreichen im 1. Quartal 2023 einen weltweiten Marktanteil von 49 %

[Display Daily](https://displaydaily.com/oled-displays-in-smartphones-reach-49-global-market-share-in-q123/)

---

![](./images/android-12-pixel-lock-screen-clock.avif)

Die zunehmende Verwendung von OLED ist der Grund, warum wir immer mehr „Always-On“-Sperrbildschirme haben.

---

### OLEDs lieben den Darkmode!

![](./images/Google%20Maps%20Darkmode.png)

[Android Dev Summit 2018](https://www.youtube.com/watch?v=N_6sPd0Jd3g)

---

![](./images/Wikipedia%20Dark%20Mode.jpg)

Darkmode sollte Standard werden!

---

## Energie-Impact von Farben

---

![](./images/Power%20per%20pixel%20color.png) <!-- .element: style="height: 40vh" -->

Bei OLED-Bildschirmen verbraucht **blaue Farbe bis zu 24 % mehr Energie** als grüne oder rote Farbe.

[Android Dev Summit 2018](https://www.youtube.com/watch?v=N_6sPd0Jd3g)

---

![](./images/Power%20per%20max%20brightness%20pixel%20color.png) <!-- .element: style="height: 50vh" -->

[Android Dev Summit 2018](https://www.youtube.com/watch?v=N_6sPd0Jd3g)

---

![](./images/Color%20wavelengths.jpg) <!-- .element: style="width: auto; height: 25vh" -->

> **Höhere Frequenzen enthalten mehr Energie** bei gleicher Amplitude.
>
> Blaues Licht hat eine **kürzere Wellenlänge** als rotes oder grünes.

[Quora](https://www.quora.com/Warum-verbrauchen-bestimmte-Farben-wie-blau-mehr-Energie-auf-einem-Bildschirm-als-rot-und-grün/answer/Per-Westermark-1)

---

<div class="r-hstack">

![](./images/Conrad%20LED%20rot.png) <!-- .element: style="width: auto; height: 25vh" -->

![](./images/Conrad%20LED%20blau.png) <!-- .element: style="width: auto; height: 25vh" -->

</div>

> Wenn Sie sich LEDs ansehen, könnte eine rote LED 1,6 V benötigen, während eine grüne 2,2 V und eine blaue LED 3 V benötigen könnte.

[Quora](https://www.quora.com/Why-do-certain-colors-like-blue-consume-more-energy-on-a-screen-than-red-and-green/answer/Per-Westermark-1)
---

### Verwendung energieeffizienter Farbpaletten

<div class="r-vstack" style="gap: 0"><div class="r-hstack" style="gap: 0">

![](./images/color_palette_flowerblossom.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

![](./images/color_palette_lush.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

</div><div class="r-hstack" style="gap: 0">

![](./images/color_palette_passionfruit.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

![](./images/color_palette_summertime.png) <!-- .element: style="width: auto; height: 10vh; margin: 0; aspect-ratio: 16/9; object-fit: cover; outline: 20px solid var(--r-background-color); outline-offset: -10px;" -->

</div></div>

[Energy efficient color palette ideas](https://greentheweb.com/energy-efficient-color-palette-ideas/)
