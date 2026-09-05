---
tags: [тэмдэглэл, github]
---

# GitHub ба амьд хаяг

## Бүртгэл

**`Ghostshdee`** — `gh` CLI-аар нэвтэрсэн. Token scopes: `repo`, `workflow`, `gist`, `read:org`.
Git тохиргоо: `Dokay` / `Dulguun.ah@gmail.com`

## Бүтэц — чухал

`Code` хавтас **өөрөө repo биш** гэж бодож болохгүй — тэр нь **нүүр хуудасны repo**
(`Ghostshdee.github.io`). Дэд хавтас бүр нь **тусдаа бие даасан repo**.
Тиймээс `.gitignore` дотор дэд хавтаснуудыг хассан.

```
Code\                  → Ghostshdee.github.io   → ghostshdee.github.io
├── index.html
├── .gitignore         ← дэд хавтаснуудыг хасдаг
├── NOTES.md           ← локал, push хийгддэггүй
└── <сайт>\            → тус бүр өөрийн repo   → ghostshdee.github.io/<сайт>/
```

## Амьд хаягууд

| Сайт | Хаяг |
|---|---|
| Нүүр | https://ghostshdee.github.io/ |
| [[Dokay portfolio]] | /dokay-portfolio/ |
| [[Dokay AI Service]] | /dokay-ai-service/ |
| [[Dokay Journeys]] | /dokay-journeys-onepager/ |
| [[Урилга — Хурим]] | /urilga-hurim-batbayar-altantsetseg/ |
| [[Урилга — Сэвлэг үргээх]] | /urilga-sevleg-mongolhuu/ |
| [[Урилга — Онгодоо залах]] | /urilga-ongodoo-zalah/ |

## Өөрчлөлт оруулах

**Тухайн сайтын хавтас дотор** байж:

```bash
git add -A
git commit -m "юу зассанаа бич"
git push
```

GitHub Pages шинэчлэгдэхэд **1–2 минут**. Хөтөч хуучинг барьвал `Ctrl+Shift+R`.

## Нүүр хуудсанд шинэ ажил нэмэх

`Code\index.html` дотор `CONFIG.works` жагсаалтад нэг мөр нэмээд push хийнэ.
Ажлын тоо, дараалал автоматаар шинэчлэгдэнэ.

```js
{
  title:'Ажлын нэр', kind:'Цахим урилга', year:'2026', tone:'lime',
  desc:'Товч тайлбар.', tech:['GSAP'],
  live:'https://ghostshdee.github.io/repo-нэр/',
  code:'https://github.com/Ghostshdee/repo-нэр',
  note:''
}
```

`tone`: `lime` `teal` `amber` `rose` `violet` `blue`

## Private болгох

```bash
gh repo edit Ghostshdee/<repo> --visibility private --accept-visibility-change-consequences
```

⚠️ Private болговол GitHub Pages **унтарна** (үнэгүй эрхэд). Амьд хаяг ажиллахаа болино.

Холбоотой: [[Ажлын хавтас]]
