# Számla feldolgozó – VESC triatlon

Banki PDF kivonatokból kigyűjti a triatlon szakosztály tagjainak befizetéseit.

## Mit csinál

1. **Taglista** – beillesztett névlista (opcionálisan havi díjjal: `Kovács Péter; 8000`).
2. **PDF beolvasás** – a böngészőben, pdf.js-sel; semmi nem kerül fel szerverre.
   A tételeket a dátummal kezdődő sorok mentén bontja, a terheléseket (negatív összeg) kihagyja.
3. **Párosítás** – a befizető nevét a taglistával veti össze (ékezet- és sorrendfüggetlen).
   A nem klubtag befizetések kimaradnak (bekapcsolható a kézi hozzárendeléshez).
4. **Közlemény és jogcím** – a „Közlemény:” / „Megjegyzés:” rovatot kiolvassa,
   és kulcsszavak alapján jogcímet ad (Tagdíj, Havidíj, Úszás, Edzőtábor…). A kulcsszólista az oldalon szerkeszthető.
5. **Ellenőrzés** – minden tétel kipipálatlanul indul; csak a jóváhagyott (bepipált) tételek kerülnek a riportba.
   Figyelmeztet, ha az összeg nem a havi díj többszöröse, vagy duplikátumnak tűnik.
6. **Gyűjtő riport** – tabbal tagolt táblázat (Dátum, Név, Összeg, Időszak, Jogcím, Közlemény, Forrás),
   jogcímenkénti összesítővel; Excelbe / Google Sheetbe beilleszthető.

## Futtatás

Statikus oldal: `index.html`. GitHub Pages-en: Settings → Pages → Branch: `main`, mappa: `/ (root)`.

## Korlátok

- Szkennelt (kép alapú) PDF-ből nem olvas – szöveges PDF kell.
- A banki formátumot heurisztikusan olvassa; új bank formátumánál a `buildItems` / `noteOf` függvényt kell igazítani.
- A tagdíj apphoz még nincs bekötve.
