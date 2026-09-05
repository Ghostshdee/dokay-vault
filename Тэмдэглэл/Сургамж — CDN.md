---
tags: [тэмдэглэл, сургамж, техник]
---

# Сургамж — CDN

## Lenis — cdnjs дээр БАЙХГҮЙ

Жигд скролл хийдэг Lenis сангийн CDN хаяг олоход цаг алдсан. Тогтоосон зүйл:

```
✗ cdnjs.cloudflare.com/ajax/libs/lenis/*        → 404, огт байхгүй
✗ cdn.jsdelivr.net/npm/lenis@1.2.3/...          → 200, ГЭХДЭЭ зөвхөн ESM.
                                                   <script src> -ээр global үүсгэдэггүй
✓ cdn.jsdelivr.net/npm/@studio-freight/lenis@1.0.42/dist/lenis.min.js
```

Сүүлийнх нь UMD билд бөгөөд `globalThis.Lenis`-ыг тодорхойлдог цорын ганц
нийтлэг хувилбар.

> [!warning] Шинэ пакет ≠ дээр
> `lenis` пакетын шинэ хувилбарууд ESM-only болсон. `<script src>`-ээр
> ачаалахад `window.Lenis` үүсэхгүй тул код чимээгүй ажиллахгүй.

## Ажилладаг CDN-үүд

```html
<!-- GSAP -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>

<!-- Lenis -->
<script src="https://cdn.jsdelivr.net/npm/@studio-freight/lenis@1.0.42/dist/lenis.min.js"></script>

<!-- Tailwind (зөвхөн хөгжүүлэлтэд) -->
<script src="https://cdn.tailwindcss.com"></script>
```

## Tailwind CDN — production-д тохиромжгүй

~380 KB JS, хөтөч дээр CSS үүсгэдэг. Хост дээр тавихаас өмнө:

```bash
npx tailwindcss -i in.css -o site.css --minify
```

дараа нь `<script>`-ыг `<link rel="stylesheet" href="site.css">` болгож солино.
3G дээр ~1.5 секундээр хурдасна.

## Сан байхгүй бол юу болохыг үргэлж бод

Гадны сан ирээгүй үед хуудас **хоосон үлдэж болохгүй**. Заавал fallback тавь:

```js
if (!window.gsap || !window.ScrollTrigger) { revealAll(); return; }
```

[[Dokay portfolio]] дээр 1.2 секундын хугацаа тавьсан — GSAP ирэхгүй бол
бүх контентыг албадан харуулна.

Хамгийн хөнгөн шийдэл нь сан огт ашиглахгүй байх: нүүр хуудас
(`Ghostshdee.github.io`) нь `IntersectionObserver`-оор scroll reveal хийдэг,
ямар ч сан татдаггүй.

Холбоотой: [[Сургамж — Анимацийн алдаа]] · [[Сургамж — Фонт ба кирилл]]
