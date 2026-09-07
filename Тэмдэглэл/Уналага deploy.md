---
tags: [тэмдэглэл, deploy]
---

# Уналага — deploy

Уналага.мн-ийг GitHub Pages дээр байршуулах бүтэц (2026-09-07).

## Бүтэц

| | Хаана | Үүрэг |
|---|---|---|
| **Эх сурвалж** | `Vault\Төслүүд\unalaga\` (dokay-vault repo дотор) | Бүх ажил энд. Obsidian-аас хянана. |
| **Deploy repo** | `github.com/Ghostshdee/unalaga` | Зөвхөн Pages-ийн толь. Гараар засахгүй. |
| **Deploy клон** | `Desktop\Claude\.deploy\unalaga\` | Локал дахь deploy repo-гийн клон. |
| **Амьд хаяг** | `ghostshdee.github.io/unalaga/` | Pages өөрөө build хийнэ. |

Яагаад тусдаа repo вэ: `dokay-vault` дээр Pages асаавал бүх тэмдэглэл
нийтийн browse хийх сайт болно + хаяг нь кирилл замтай урт болно.
Тусдаа repo нь `Code\`-ийн 6 төслийн адил цэвэрхэн.

## Шинэчлэх (deploy хийх)

`Төслүүд\unalaga\`-д өөрчлөлт хийж vault-д commit хийсний **дараа**,
веб файлуудыг deploy клон руу хуулж push хийнэ:

```bash
SRC="$HOME/Desktop/Claude/Vault/Төслүүд/unalaga"
DEP="$HOME/Desktop/Claude/.deploy/unalaga"
git -C "$DEP" pull -q
cp "$SRC"/*.html "$SRC"/*.css "$DEP"/ 2>/dev/null
[ -f "$SRC/app.js" ] && cp "$SRC/app.js" "$DEP"/
cp "$SRC"/{CLAUDE,DESIGN,BUILD}.md "$DEP"/ 2>/dev/null
git -C "$DEP" add -A && git -C "$DEP" commit -q -m "deploy $(date +%F)" && git -C "$DEP" push -q
```

`git subtree push --prefix` ашиглаж болохгүй — кирилл замтай үед
git-subtree-ийн assertion алдаа өгдөг (2026-09-07-нд тулгарсан).

Практикт: Claude-д «уналага deploy хий» гэхэд дээрхийг гүйцэтгэнэ.

## Pages анх асаах (нэг удаа)

`unalaga` repo → Settings → Pages → Source: **Deploy from a branch**
→ `main` / `/(root)` → Save. ~1 мин дараа амьд.

## Холбоотой
[[Уналага.мн]] · [[GitHub ба амьд хаяг]] · [[Ажлын хавтас]]
