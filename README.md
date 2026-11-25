# Brahma

A Brahmi (U+11000 block) font in which conjuncts are shown with a continuous
headline bar (shirorekha) instead of conjunct ligatures.

**Live tester:** type in Devanagari and see it set in Brahmi — see the GitHub Pages
link in the repository sidebar.

## Files

| File | What it is |
|---|---|
| `Brahma-Regular.ttf` | Desktop font |
| `Brahma-Regular.woff2` | Web font |
| `index.html` | The tester page (Devanagari → Brahmi) |

## How the bar works

The bar appears only on consonants joined by a virama (U+11046). The virama itself
is hidden and the bar takes its place. Three bar forms are swapped in by the `ccmp`
feature:

| Glyph suffix | Where it is used | Bar runs |
|---|---|---|
| `.shV` | A consonant joined to the next one (first or middle of a conjunct) | across the letter and slightly into the next |
| `.shE` | The last consonant of a conjunct, with no virama after it | from the left edge to the middle of the letter |
| `.shD` | A dead consonant (standalone, or with a trailing virama) | the full width of the letter, balanced on both sides |

Plain consonants and vowel signs never get a bar. Vowel signs sit above it.

## Use on the web

```css
@font-face {
  font-family: "Brahma";
  src: url("Brahma-Regular.woff2") format("woff2"),
       url("Brahma-Regular.ttf") format("truetype");
}
.brahmi { font-family: "Brahma", serif; }
```

Shaping features (`ccmp`, `mark`, `mkmk`) are on by default in browsers; do not
disable ligature or composition features.

## Known gaps

- RA (U+1102D) has no bar forms yet.
- Brahmi digits, danda and double danda are not drawn.

## Licence

No licence has been added yet. Until the owner adds one, all rights are reserved.
