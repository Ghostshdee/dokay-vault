---
tags: [ажил, нэг-хуудас]
төлөв: амьд
он: 2026
---

# Dokay Journeys

Аяллын үйлчилгээний нэг хуудас танилцуулга. «Бид аяллын байгууллага биш,
бид аяллын үргэлжлэл» — явахаас өмнө, үед, дараа гэсэн гурван үе шат.

- **Амьд:** https://ghostshdee.github.io/dokay-journeys-onepager/
- **Код:** https://github.com/Ghostshdee/dokay-journeys-onepager
- **Локал:** `Desktop\Claude\Code\dokay-journeys-onepager\`

## Онцлог

Хамгийн хөнгөн ажил — 12 KB. Tailwind ч, GSAP ч байхгүй, зөвхөн статик
HTML + CSS + Google Fonts.

`CONFIG` объект байхгүй — агуулгыг шууд HTML дотроос өөрчилнө. Бусад
сайтуудаас ялгаатай тал энэ.

## Зассан алдаа

**viewport meta байхгүй байсан.** Утсан дээр хуудас 980px өргөнөөр буугаад
бүх зүйл жижгэрч, чимхэж томруулах шаардлагатай байв. 2026-09-04-нд нэмсэн.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

> [!tip] Дүрэм
> Шинэ HTML эхлүүлэх бүрд `<head>`-д эхний хоёр мөр нь `charset` ба
> `viewport` байх ёстой. Аль нэг нь дутвал утсан дээр эвдэрнэ.

## Дутуу

- [ ] og:image, og:title зэрэг Open Graph мета таг огт байхгүй
- [ ] Холбоо барих мэдээлэл шалгах
