# PRO1 Kompendium

Dette er en redigerbar web-version af kompendiet.

## Sådan redigerer du
- Hvert kapitel ligger som Markdown i `docs/kapitel/`.
- Hvert bilag ligger i `docs/bilag/`.
- Billeder ligger i `docs/images/`.

### Indsæt en figur
1. Læg billedet i `docs/images/` (fx `figur-3-2.png`)
2. Referér i teksten:

```md
![Figur 3.2 – Beskrivelse](../images/figur-3-2.png)
```

## Byg til HTML
Installer Python + pakker og kør:

```bash
pip install mkdocs mkdocs-material
mkdocs build
```

De færdige HTML-filer ligger i mappen `site/`.

## Preview lokalt
```bash
mkdocs serve
```
