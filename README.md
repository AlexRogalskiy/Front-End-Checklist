# Front-End Checklist

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Front-End Checklist** HTML sayfanızı yayına almadan önce test etmeniz gereken tüm öğelerin kapsamlı bir listesidir.

Liste, diğer açık kaynaklı listelerden gelen eklemelerle birlikte Front End geliştiricilerinin yıllara dayanan deneyimlerinin bir ürünüdür.

*Front-End Checklist'i daha fazla insanın duymasına yardımcı olmak için Product Hunt üzerinden oy verin.*
[![](http://res.cloudinary.com/djnyaloac/image/upload/v1508896898/upvote-producthunt_vzys4c.jpg)](https://www.producthunt.com/posts/front-end-checklist)

## İçindekiler

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Görseller](#images)**
6. **[JavaScript](#javascript)**
7. **[Güvenlik](#security)**
8. **[Performans](#performance-1)**
9. **[Ulaşılabilirlik](#accessibility)**
10. **[SEO](#seo)**

## Nasıl kullanılır?

Çoğu proje için **Front-End Checklist** içerisindeki öğelerin tamamının kullanılması gerekir. Ancak bazı öğelerin kullanımı ihmal edilebilir. (Örneğin bir yönetim paneli uygulamasında, RSS beslemesine ihtiyacınız olmayabilir). Öğelerin önemi konusunda 3 seviye belirledik:

* ![Düşük][low_img] etiketi **önerilen** ancak bazı durumlarda es geçebileceğiniz öğeleri ifade eder.
* ![Orta][medium_img] etiketi **kesinlikle önerilen** ve sadece nadir durumlarda görmezden gelebileceğiniz öğeleri ifade eder. Bazı elementlerin ihmal edilmesi performans ve SEO konusunda kötü sonuçlara neden olabilir.
* ![Yüksek][high_img] etiketi öğe kullanımının **zorunlu** olduğunu ve hiçbir şartta görmezden gelinemeyeceğini ifade eder. Aksi halde sayfanızda fonksiyonel kayıplar yaşayabilir, ulaşılabilirlik ve SEO konusunda ciddi sorunlarla karşılaşabilirsiniz. Test önceliği daima bu etikete sahip öğelerdedir.

Bazı kaynaklar içeriğin türünü anlayabilmeniz için çeşitli ifadeler içerir.

* 📖: dokümantasyon veya makale
* 🛠: çevrimiçi araç / test aracı
* 📹: medya veya video içeriği

---

## Head

> **Notlar:** HTML dökümanının `<head>` bölümünde bulunması gereken elementlerin tam listesini [burada](https://github.com/mkg0/HEAD) bulabilirsiniz.

### Meta tag

* [ ] **Doctype:** ![High][high_img] Doctype, HTML5'dir ve tüm HTML sayfalarınızın en üstünde yer almalıdır.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> * 📖 [Karakter kodlamasını belirleme - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*Sonraki 3 meta tag (Charset, X-UA Compatible ve Viewport) head bölümünün en başında yer almalıdır.*

* [ ] **Charset:** ![High][high_img] Karakter seti (UTF-8) doğru şekilde tanımlanmalıdır.

```html
<!-- Dökuman için karakter kodlaması -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Medium][medium_img] X-UA-Compatible meta tagı yer almalıdır.

```html
<!-- Internet Explorer'a en son oluşturma motorunu kullanmasını söyleyin -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> * 📖 [Eski döküman modlarını ayarlama (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![High][high_img] Viewport doğru şekilde tanımlanmalıdır.

```html
<!-- Responsive bir tasarım için viewport -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![High][high_img] Başlık tüm sayfalarda kullanılmalıdır. (SEO: Google, başlıkta kullanılan karakterlerin piksel genişliğini hesaplar; 472 ve 482 piksel arasında kesilecektir. Buna göre ortalama karakter limiti 55 civarındadır).

```html
<!-- Döküman Başlığı -->
<title>55 karakterden daha kısa bir başlık</title>
```

> * 📖 [Başlık - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** ![High][high_img] Eşsiz bir meta açıklaması bulunmalı ve açıklama uzunluğu 150 karakteri aşmamalıdır.

```html
<!-- Meta Açıklaması -->
<meta name="description" content="Description of the page less than 150 characters">
```

> * 📖[Meta Açıklaması - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** ![Medium][medium_img] Tüm faviconlar ayrı ayrı oluşturulmalı ve doğru şekilde ayarlanmalıdır. Eğer sadece `favicon.ico` dosyasına sahipseniz, dosyayı sitenizin ana klasörüne koyun. Normal şartlarda dosyayı işaret eden bir element kullanmanıza gerek yok ancak aşağıdaki örnekte olduğu gibi döküman içerisinde belirtmek iyi bir pratik olabilir. Günümüzde `.ico` formatında (boyut: 32x32px). **PNG** biçiminin kullanılması önerilmektedir.

```html
<!-- Standart favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Önerilen favicon biçimi -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Low][low_img] Apple touch favicon (apple-mobile-web-app-capable) kullanılmalıdır *(Desteklemek isteyebileceğiniz tüm boyutları karşılayacak, en az 200x200px boyutlarında bir Apple Icon oluşturun).*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> * 📖 [Web Uygulamalarını Yapılandırma](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Low][low_img] Windows tiles kullanılmalı ve doğru şekilde belirtilmelidir.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

Browserconfig.xml dosyası için gerekli minimum xml işaretlemesi aşağıdaki gibidir:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> * 📖 [Tarayıcı yapılandırmaları için şema referansı](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Medium][medium_img] Yinelenen içeriği önlemek için `rel =" canonical "` kullanın.

```html
<!-- Yinelenen içerik sorunlarını önlemeye yardımcı olur -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

> * 📖 [Kanonik URL'leri kullanın - Search Console Yardım - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [rel=canonical ile ilgili sıkça yapılan yapılan 5 hata - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML tags

* [ ] **Language attribute:** ![High][high_img] Web sitenizde `lang` niteliğini kullanmalı ve geçerli sayfanın dili ile ilişkilendirmelisiniz.

```html
<html lang="en">
```

* [ ] **Direction attribute:** ![Medium][medium_img] Sayfa yazıların yönü html etiketinde belirtilmelidir. (Farklı bir html etiketi kullanılabilir).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] Aktif olan sayfanın dili belirtilmelidir.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![Low][low_img] Gerekirse IE için koşullu ifadeler kullanılmalıdır.

> * 📖 [Koşullu ifadeler hakkında (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low][low_img] Eğer projeniz bir blog ise ya da makaleler içeriyor ise; bir RSS link sağlanmalıdır.

* [ ] **Inline critical CSS:** ![Medium][medium_img] CSS which styles content that is immediately visible during pageload ("above the fold content") is called "critical CSS". It is embedded before your principal CSS call and between `<style></style>` in a single line (minified).
Sayfanın yüklenmesi sırasında (Tüm içeriklerden önce) mutlaka görünmesi gereken CSS betikleri kritik CSS olarak adlandırılır. Genel CSS içeriklerinden önce `<style></ style>` arasında tek bir satırda (sıkıştırılmış) verilmelidir.
> * 🛠 [Critical, Addy Osmani on GitHub](https://github.com/addyosmani/critical) bu işlemi otomatik hale getirir.

* [ ] **CSS order:** ![High][high_img] Tüm CSS dosyaları JavaScript dosyalarından önce `<head>` bölümünde tanımlanmalıdır. (JS dosyalarının asenkron olarak sayfanın en üstünde yüklenebildiği durumlar dışında).

### Sosyal meta

***Facebook OG*** ve ***Twitter Cards*** tüm web siteleri için önerilir. Eğer belirli bir sosyal siteyi hedefliyor ve içeriklerinizi tanıtmak istiyorsanız diğer etiketlerde kullanılabilir.

* [ ] **Facebook Open Graph:** ![Low][low_img] Tüm Facebook Open Graph (OG) verileri test edilmeli ve hiçbiri eksik ya da hatalı bilgi içermemelidir. Resimler en az 600 x 315 piksel boyutunda olmalıdır. 1200 x 630 piksel önerilir.

> **Notlar:** `og:image:width` ve `og:image:height` tanımlarını kullanarak resim boyutlarını belirtmeniz; örümceğin asenkron olarak resimleri yükleyip işleme sokmadan, direk kullanabilmesine olanak sağlayacaktır. 

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<!-- Sonraki etiketler opsiyoneldir ancak kullanılması önerilir -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [Web Yöneticileri için Paylaşım Kılavuzu](https://developers.facebook.com/docs/sharing/webmasters/)
> * 📖 [En İyi Teknikler - Paylaşım](https://developers.facebook.com/docs/sharing/best-practices/)
> * 🛠 Sayfanızı [Facebook OG test aracı](https://developers.facebook.com/tools/debug/) ile test edin.

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Twitter card'larına giriş — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Sayfanızı [Twitter card doğrulayıcı](https://cards-dev.twitter.com/validator) ile test edin.

**[⬆ başa dön](#table-of-contents)**

---

## HTML

### En iyi teknikler

* [ ] **HTML5 Semantik Elementler:** ![High][high_img] HTML5 Semantik Elementler doğru şekilde kullanılmalı (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Hata sayfaları:** ![High][high_img] 404 Hata sayfası and 5xx sayfası bulunmalıdır. 5xx hata sayfalarındaki CSSlerin sayfa içine entegre edilmesi gerektiği unutulmamalıdır. (Sunucuya herhangi bir çağrı yapımamalıdır).

* [ ] **Noopener:** ![Medium][medium_img] `target="_blank"` ile harici bağlantılar kullanmanız durumunda, tab nabbing'i önlemek için bağlantınız `rel="noopener"` niteliğine sahip olmalıdır. Eğer Firefox'un eski versiyonlarına destek vermek isterseniz `rel="noopener noreferrer"` şeklinde kullanabilirsiniz.

> * 📖 [rel=noopener Hakkında](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments:** ![Low][low_img] Yayına çıkmadan önce gereksiz kodlar sayfadan temizlenmelidir.

### HTML testleri

* [ ] **W3C compliant:** ![High][high_img] HTML kodundaki olası sorunları tanımlamak için tüm sayfaların W3C doğrulayıcıyla test edilmesi gerekir.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] HTML içerisindeki tüm sorunları analiz etmek için aşağıdaki araçları kullanabilirsiniz.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)

> * 🛠 [Sonar a linting tool for the web](https://sonarwhal.com/)

* [ ] **Link checker:** ![High][high_img] Sayfanızda kırık link bulunmamalıdır. Herhangi bir 404 hatası alınmadığını doğrulayın.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Medium][medium_img] Web siteniz reklam engelleme araçları aktifken doğru şekilde görüntülenebilmelidir (Bir mesaj ile ziyaretçileri eklentiyi pasif hale getirmeleri yönünde uyarabilirsiniz).



**[⬆ başa dön](#table-of-contents)**

---

## Webfonts

> **Notlar:** Webfont kullanımı stillendirilmemiş / görünmez yazılara neden olabilir - may cause Flash Of Unstyled Text/Flash Of Invisible Text - Fallback fontlar kullanmayı ya da webfont yükleyicilerini kullanarak bunu önleyin.
> * 📖 [Google'ın webfontlar konusunda düşünceleri](https://developers.google.com/fonts/docs/technical_considerations)

* [ ] **Webfont format:** ![High][high_img] WOFF, WOFF2 ve TTF tüm modern tarayıcılar tarafından desteklenir.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType ve OpenType font desteği](https://caniuse.com/#feat=ttf)
> * 📖 [@font-face kullanımı - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High][high_img] Webfont boyutları 2 MB'ı aşmamalıdır. (Tüm türevleri ile birlikte).

* [ ] **Webfont loader:** ![Low][low_img] Webfont yükleyiciler ile yükleme akışını kontrol edin.

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ başa dön](#table-of-contents)**

---

## CSS

> **Notlar:** Çoğu Front-End geliştiricinin takip ettiği [CSS Kılavuzları](https://cssguidelin.es/) ve [Sass Kılavuzları](https://sass-guidelin.es/)nı inceleyin. Eğer CSS özellikleri konusunda çekinceleriniz var ise, [CSS Kaynakça](http://cssreference.io/)sını ziyaret edin. Tutarlılık için bu kısa [Kod Kılavuzu](http://codeguide.co/) da kullanılabilir.

* [ ] **Responsive Web Design:** ![High][high_img] Web sitesinin tasarımı responsive olmalı.
* [ ] **CSS Print:** ![Medium][medium_img] Baskı(yazdırma) için tüm sayfalarda geçerli olan bir CSS bulunmalı.
* [ ] **Preprocessors:** ![Low][low_img] Sayfanız bir CSS önişlemcisi kullanmalı ([Sass](http://sass-lang.com/) önerilir).
* [ ] **Unique ID:** ![High][high_img] Eğer ID kullanılmışsa tümü eşsiz olmalı.
* [ ] **Reset CSS:** ![High][high_img] Güncel bir CSS reset (reset, normalize ya da reboot) kullanılmalı. *(Eğer Bootstrap ya da Foundation gibi bir CSS Framework kullanıyorsanız Normalize hali hazırda buna dahil edilmiştir)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Low][low_img] Javascript dosyalarındaki tüm sınıflar (ya da IDler) **js-** ile başlamalı ve CSS dosyaları içerisinde kullanılmamalıdır.

```html
<div id="js-slider" class="my-slider">
<!-- Ya da -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Embedded or inline CSS:** ![High][high_img] `<style>` etiketleri arasında ya da satır içi CSS kullanmaktan kaçının: sadece geçerli bir sebebiniz varsa kullanın (örn. slider için arkaplan resmi, kritik CSS).
* [ ] **Vendor prefixes:** ![High][high_img] Vermek istediğiniz tarayıcı desteğine göre CSS tarayıcı önekleri kullanılmalıdır.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performans

- [ ] **Concatenation:** ![High][high_img] CSS dosyaları tek bir dosyada birleştirilmelidir *(HTTP/2 hariç)*.
- [ ] **Minification:** ![High][high_img] TÜm CSS dosyaları sıkıştırılmalıdır.
- [ ] **Non-blocking:** ![Medium][medium_img] CSS dosyaları DOM'un yüklenmesini engellememelidir.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Low][low_img] Kullanılmayan CSS'ler silinmelidir.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS testleri

* [ ] **Stylelint:** ![High][high_img] Hiçbir CSS ya da SCSS dosyası hata içermemelidir.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High][high_img] Tüm sayfalar 320px, 768px, 1024px (Analitik verilerinize göre daha farklı olabilir) kırılma noktaları için test edilmelidir.

* [ ] **CSS Validator:** ![Medium][medium_img] CSS test edilmeli ve bilinen hatalar düzeltilmeli.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers:** ![High][high_img] Tüm sayfalar bilinen tüm masaüstü tarayıcılarda test edilmeli (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Mobile Browsers:**  ![High][high_img] Tüm sayfalar bilinen tüm mobil tarayıcılarda test edilmeli (Native browser, Chrome, Safari...).
* [ ] **OS:**  ![High][high_img] Tüm sayfalar bilinen tüm işletim sistemlerinde test edilmeli (Windows, Android, iOS, Mac...).

- [ ] **Pixel perfect:** ![High][high_img] Sayfanız hazırlanan tasarımla %100 aynı olmasada buna oldukça yakın olmalı.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction:** ![High][high_img] Eğer desteklenecekse tüm sayfalar LTR ve RTL diller için test edilmeli.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ başa dön](#table-of-contents)**

---

## Görseller

> **Notlar:** Resim optimizasyonunu hakkında detaylı bilgi için ücretsiz ekitap'dan faydalanın. **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### En iyi teknikler

* [ ] **Optimization:** ![High][high_img] Tüm görseller tarayıcıda kullanılmadan önce optimize edilmelidir. Anasayfa gibi önemli sayfalarda WebP formatını kullanabilirsiniz.

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 [ImageOptim](https://imageoptim.com/) ile resimlerinizi ücretsiz şekilde optimize edebilirsiniz.
> * 🛠 [Kraken.io](https://kraken.io/web-interface) da png ve jpg optimizasyonu için başarılı çözümler bulabilirsiniz. 1mb'a kadar olan dosyalar ücretsiz plana dahil.

* [ ] **Picture/Srcset:** ![Medium][medium_img] Kullanıcının ekran boyutuna göre en uygun resmin görüntülenmesi için srcset özelliği kullanılmalıdır.

> * 📖 [Srcset ile responsive görseller hazırlama](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** ![Low][low_img] Retina desteği için görsellerin 2x ve 3x formatları bulunmalıdır.
* [ ] **Sprite:** ![Medium][medium_img] Küçük resimler bir sprite dosyasında yer almalıdır (ikonlar SVG sprite dosyalarında bulunabilir).
* [ ] **Width and Height:** ![High][high_img] Eğer render edilecek görselin boyutları biliniyorsa `<img>` elementlerinin `width` ve `height`değerleri girilmelidir (CSS üzerinden boyutlandırmalarda kullanılmayabilir).
* [ ] **Alternative text:** ![High][high_img] Tüm `<img>` elementleri görseli açıklayan bir yazı barındırmalıdır.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** ![Medium][medium_img] Resimler lazyload ile yüklenmeli. (Daima bir noscript alternatifi bulunmalı).

**[⬆ başa dön](#table-of-contents)**

---

## JavaScript

### En iyi teknikler

* [ ] **JavaScript Inline:** ![High][high_img] Javascript kodlar döküman içinde kullanılmamalı (HTML kodu ile karışık şekilde).
* [ ] **Concatenation:** ![High][high_img] Javascript dosyaları birleştirilmeli.
* [ ] **Minification:** ![High][high_img] JavaScript dosyaları sıkıştırılmalı (`.min` soneki kullanılabilir).

> * 📖 [İçerikleri Sıkıştırmak (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> * 📖 [JavaScript'i Kullanan Güvenli Uygulamalar Geliştirme Rehberi](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **Non-blocking:** ![Medium][medium_img] JavaScript dosyaları asenkron(`async`) ya da defer(`defer`) ile yüklenmeli.

> * 📖 [Oluşturmayı Önleyici Javascript'i Kaldırma](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] Bazı özel nitelikleri hedeflemeniz gerekiyorsa, `<html>` etiketinize sınıf eklemek için özel bir Modernizr kullanabilirsiniz.

> * 🛠 [Modernizr'ınızi Kişiselleştirin](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![High][high_img] ESLint ile herhangi bir hata almamalısınız (Standart kurallara ya da kendi ayarlarınıza göre).

> * 📖 [ESLint - JavaScript ve JSX için modüler linting asistanı](https://eslint.org/)

**[⬆ başa dön](#table-of-contents)**

---

## Güvenlik

### Web sitenizi tarayın ve kontrol edin

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Best practices

* [ ] **HTTPS:** ![Medium][medium_img] Tüm sayfalar ve harici içeriklerde HTTPS kullanılmalı (eklentiler, resimler...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Katı Taşıma Güvenliği (HSTS):** ![Medium][medium_img] HTTP header'ı 'Strict-Transport-Security' şeklinde ayarlanmalı.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Siteler Arası İstek Sahteciliği (CSRF):** ![High][high_img] CSRF saldırılarını önlemek ve sunucuya yapılan isteklerin doğruluğu için gelen isteklerin web sitenizden / uygulamanızdan geldiğine emin olun.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] Sayfanız veya web siteniz, olası XSS sorunları içermemeli.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] Google Chrome ve Internet Explorer'ın bir yanıtın içerik türünü sunucu tarafından bildirilenlerden farklı olarak algılamasını(mime-sniff) önler.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] Ziyaretçilerinizi tıklama saldırılarına karşı koruyun.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

* [ ] **Content Security Policy** ![Medium][medium_img] İçeriğin sitenizde nasıl yüklendiğini ve nerede yüklenmesine izin verdiğini tanımlar. Ayrıca tıklama saldırılarına karşı koruma sağlamak için de kullanılabilir.

> * 📖 [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
> * 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
> * 📖 [CSP Cheat Sheet - OWASP](https://www.owasp.org/index.php/Content_Security_Policy_Cheat_Sheet)

**[⬆ başa dön](#table-of-contents)**

---

## Performans

### Best practices

- [ ] **Page weight:** ![High][high_img] Sayfa boyutları 0 ile 500 KB arasında olmalı.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium][medium_img] HTML'i sıkıştırmalısınız.
> * 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Medium][medium_img] Resim, script ve CSS dosyaları sayfa yanıt süresini iyileştirmek için lazyload ile yüklenmeli (Detaylı bilgiye kendi başlıkları altından ulaşılabilir).

* [ ] **Cookie size:** Eğer çerez kullanıyorsanız, her bir çerezin 4096 bayttan fazla olmadığına ve alan adınızın 20'den fazla çerez içermediğine emin olun.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Third party components:** ![Medium][medium_img] Third party iframes or components relying on external JS (like sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping your users activity private.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] DNS of third-party services that may be needed are resolved in advance during idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Low][low_img] DNS lookup, TCP handshake and TLS negotiation with services that will be needed soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Low][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`) in advance using `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![High][high_img] All your pages were tested (not only the homepage) and have a score of at least 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
> * 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **Notes:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Medium][medium_img] Major functionality like main navigation and search should work without JavaScript enabled.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![High][high_img] Headings should be used properly in the right order (H1 to H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>` has `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` has `role="navigation"`.
- [ ] **Role main:** ![High][high_img] `<main>` has `role="main"`.

> * 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)
> * 📖 [ARIA roles categorization](https://www.w3.org/TR/wai-aria/roles#roles_categorization)

### Semantics

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] This is especially important for mobile devices that show customized keypads and widgets for different types.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![High][high_img] A label is associated with each input form element. In case a label can't be displayed, use `aria-label` instead.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing

* [ ] **Accessibility standards testing:** ![High][high_img] Use the WAVE tool to test if your page respects the accessibility standards.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Medium][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![High][high_img] If the focus is disabled, it is replaced by visible state in CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] Google Analytics is installed and correctly configured.
* [ ] **Headings logic:** ![Medium][medium_img] Heading text helps to understand the content in the current page.
* [ ] **sitemap.xml:** ![High][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously Google Webmaster Tools).
* [ ] **robots.txt:** ![High][high_img] The robots.txt is not blocking webpages.

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] Pages using structured data are tested and are without errors. Structured data helps crawlers understand the content in the current page.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Heirarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Medium][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of your website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

**[⬆ back to top](#table-of-contents)**

---

## Çeviri

Front-End Checklist diğer dillerde de mevcuttur. Tüm çevirmenlerlere teşekkürler!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
* 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
* 🇫🇷 French: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)

---

## Front-End Checklist Rozeti

Front-End Checklist Listesinin kurallarını izlediğinizi göstermek isterseniz bu rozeti Benioku dosyasında kullanabilirsiniz.

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ başa dön](#table-of-contents)**

---

## Katkıda Bulunma

**Değişiklikler veya eklemeler önermek için issue açabilir veya pull sorgusu gönderebilirsiniz.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](http://frontendchecklist.com/) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

### Katkıda Bulunanlar

Katkıda bulunanları [buradan](https://github.com/thedaviddias/frontendchecklist/graphs/contributors) görüntüleyebilirsiniz.

## Destek

Herhangi bir sorunuz veya öneriniz varsa, Gitter veya Twitter'ı kullanmaktan çekinmeyin:

* [Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Facebook](https://www.facebook.com/frontendchecklist/)
* [Twitter](https://twitter.com/thedaviddias)

## Yazar

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## Çevirmen

**[Eray Çetinay](https://github.com/eraycetinay/Front-End-Checklist)**

## Lisans

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ başa dön](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
