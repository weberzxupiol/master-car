# Serwis MOTRIO · Master Car Dębica

Strona warsztatu samochodowego **Master Car** w Dębicy (sieć MOTRIO) — wielostronicowa, z rezerwacją online i lokalnym SEO.

- **Adres:** Leśna 40, 39-200 Dębica
- **Telefon:** 533 831 303
- **Ocena:** 4,7/5 (48 opinii Google)

## Struktura (multipage)
- `index.html` — strona główna
- `uslugi.html` — usługi + FAQ
- `rezerwacja.html` — rezerwacja online (Cal.com)
- `o-nas.html` — o nas + opinie
- `kontakt.html` — kontakt, mapa, godziny
- `sitemap.xml`, `robots.txt` — SEO

Statyczne `HTML/CSS/JS`, bez build. Projekt UI wg skilla **ui-ux-pro-max** (grafit + czerwień, Oswald/Inter).

## Rezerwacja online — Cal.com
Domyślnie na `rezerwacja.html` wyświetla się **wizualny podgląd** kalendarza. Aby uruchomić prawdziwą rezerwację:
1. Załóż darmowe konto na https://cal.com i utwórz typ wydarzenia (np. „Wizyta w warsztacie", 30 min). Link będzie postaci `nazwa-uzytkownika/wizyta`.
2. W pliku `rezerwacja.html` (sekcja `<script>` na dole) ustaw:
   - `CAL_ENABLED = true;`
   - `CAL_LINK = "nazwa-uzytkownika/wizyta";`

Wtedy zamiast podglądu pojawi się działający kalendarz, a rezerwacje trafią do kalendarza warsztatu (z potwierdzeniem i przypomnieniem e-mail).

## Lokalne SEO
- Unikalne `title`/`description`/`canonical` na każdej podstronie
- JSON-LD: `AutoRepair` (geo, godziny, `areaServed`, oceny), `BreadcrumbList`, `FAQPage`
- Geo meta, Open Graph, spójne NAP w stopce, `sitemap.xml` + `robots.txt`

## Uruchomienie lokalne
```bash
python -m http.server 5180
```
Następnie otwórz http://localhost:5180

## Wdrożenie
Hosting: **Cloudflare Pages** (`master-car.pages.dev`). Repozytorium: GitHub.
