# MoveTech Katalog

Statiska tillgångar för MoveTechs webbkatalog (flipbook) på `movetech.com/katalog`.

- **`katalog.pdf`** — aktuell katalog, webb-optimerad (beskuren till trim, ~150 dpi, kundadress borttagen).
  Serveras via jsDelivr CDN och laddas av `katalog.html` (som ligger i Vendre `/template/movetech_live/`).
- **`katalog.html`** — referens/källa till bläddraren (produktkartan inlinad).

## Uppdatera katalogen
1. Prep:a den tryckfärdiga PDF:en:
   `python scripts/crop_print_pdf.py NY_TRYCK.pdf katalog.pdf --optimize --redact "SIDA:x0,y0,x1,y1"`
   (crop-scriptet finns i CRM-repot). Kolla adress-rutans koordinater med `--inspect`.
2. Ersätt `katalog.pdf` här, committa och pusha.
3. jsDelivr uppdateras inom ~12h (eller rensa direkt: `https://purge.jsdelivr.net/gh/techymover/movetech-katalog@main/katalog.pdf`).
