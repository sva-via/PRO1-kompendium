# PRO1 Kompendium (MkDocs)

Dette projekt genererer et statisk website (HTML) med venstremenu over kapitler og bilag.

## Struktur
- `docs/` indeholder alt indhold i Markdown
- `docs/images/` indeholder billeder
- `mkdocs.yml` styrer menu og tema

## Kør
```bash
pip install mkdocs mkdocs-material
mkdocs serve
```

## Byg HTML
```bash
mkdocs build
```
Output ligger i `site/`.
