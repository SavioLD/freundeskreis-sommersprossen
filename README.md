# Freundeskreis Sommersprossen Rottweil e.V. – Website

Statische Website. Kein Build, kein Framework, keine Datenbank.
Einfach hochladen und fertig.

## Struktur

```
/
├── index.html              ← Startseite
├── festival.html           ← Programm 2026 (alle 7 Konzerte)
├── verein.html             ← Über uns, Geschichte, Vorstand
├── mitglied-werden.html    ← Beitritt + PDF-Download
├── spenden.html            ← Bankverbindung + Hinweise zur Spendenquittung
├── sponsoring.html         ← Info + Interessens-Formular
├── kontakt.html            ← Kontaktdaten + Formular
├── impressum.html          ← Pflichtangaben (TODO: Registernummer ergänzen)
├── datenschutz.html        ← DSGVO-Erklärung
├── css/styles.css
├── js/main.js              ← Mobile-Menü, aktiver Link
├── assets/favicon.svg
└── downloads/
    └── programm-2026.pdf   ← Programmflyer (824 KB)
```

## Design

- **Farben**: Festival-Rot `#C8102E` · Sonnen-Gelb `#FFD60A` · Weiß · Anthrazit `#1A1A1A`
- **Schrift**: Source Sans 3 (Google Fonts) – große Schriftgröße (19 px) für gute Lesbarkeit
- **Stil**: viel Weißraum, hohe Kontraste, große Buttons, mobil-first, ohne Cookies / Tracking
- **Logo-Platzhalter**: rotes Rund mit „FS" + gelber Akzent (Brand-Mark in der Navigation) – kann durch echtes Logo ersetzt werden

## Formulare

Kontakt- und Sponsoring-Formular nutzen den `mailto:`-Mechanismus. Beim Absenden öffnet sich
das Mail-Programm des Nutzers mit den ausgefüllten Daten. **Keine Server-Logik erforderlich.**

Wenn echte Server-seitige Verarbeitung gewünscht ist (z. B. via Formspree, Netlify Forms,
oder PHP-Mailer), nur das `action`-Attribut im jeweiligen `<form>` ersetzen.

## Lokal testen

```bash
cd sommersprossen-website
python3 -m http.server 8080
# → http://localhost:8080
```

## Deployen

Reine HTML/CSS/JS-Site – läuft auf jedem Webhoster:

- **Netlify / Vercel / Cloudflare Pages**: Repository verbinden, kein Build-Command, Publish-Dir `/`
- **Klassisches Webhosting (FTP)**: Inhalt von `sommersprossen-website/` per FTP in den Webroot kopieren
- **GitHub Pages**: Repo + Pages-Settings, Branch `main` Root

## TODO vor Go-Live

1. **Impressum**: Vereinsregister-Nummer + Registergericht + Steuernummer ergänzen
2. **Domain**: DNS auf den neuen Hoster umstellen
3. **Logo**: echtes Vereinslogo (sofern vorhanden) statt der „FS"-Platzhalter-Marke einfügen
4. **Fotos**: ggf. Konzertfotos / Künstler-Bilder einbinden (Bildrechte beachten)
5. **Formularverarbeitung**: entscheiden ob `mailto:` reicht oder Backend-Service eingebunden wird
6. **Datenschutzerklärung** anwaltlich prüfen lassen
