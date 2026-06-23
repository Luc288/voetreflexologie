# Voetreflexologie Martine Smet — Hugo-site

Statische website voor Voetreflexologie Martine Smet (Deurne, Antwerpen), klaar om te bouwen en hosten met [Hugo](https://gohugo.io/).

## Lokaal bekijken

```bash
hugo server
```

Open daarna http://localhost:1313/.

## Bouwen voor hosting

```bash
hugo --minify
```

De volledige site staat dan in `public/`. Upload de inhoud van die map naar je host (Netlify, Cloudflare Pages, GitHub Pages, of een gewone webserver).

> Pas in `hugo.toml` de `baseURL` aan naar het definitieve domein vóór de productie-build.

## Structuur

```
hugo.toml                      # configuratie, contactgegevens, hoofdmenu
content/                       # één bestand per pagina (titel + SEO-beschrijving)
  _index.md  aanbod.md  over.md  cursussen.md  contact.md  faq.md
data/faq.yaml                  # alle FAQ-vragen (genereert zowel de pagina als de schema.org-data)
layouts/_default/baseof.html   # HTML-omhulsel (head + header + footer)
layouts/partials/              # header, footer, cta (herbruikbaar)
layouts/index.html             # homepage
layouts/_default/*.html        # overige pagina's (aanbod, over, cursussen, contact, faq)
static/style.css               # styling
static/script.js               # mobiel hamburgermenu
```

## Aanpassen

- **Contactgegevens** (telefoon, e-mail, adres): centraal in `hugo.toml` onder `[params]`.
- **Menu**: in `hugo.toml` onder `[[menu.main]]`. De actieve pagina wordt automatisch gemarkeerd.
- **Teksten van een pagina**: in de bijbehorende `layouts/_default/<naam>.html` (of `layouts/index.html` voor de home).
- **FAQ-vragen**: alleen `data/faq.yaml` bewerken — de uitklaplijst én de Google-rich-result-data (schema.org FAQPage) worden daaruit gegenereerd.
- **Pagina-titel / SEO-beschrijving**: in de front matter van het `content/*.md`-bestand.

## Aandachtspunten / nog aan te vullen

- De originele site verwees naar afbeeldingen op het oude DNN-domein (logo, foto's). Plaats eventuele afbeeldingen in `static/` en verwijs er relatief naar.
- In `data/faq.yaml` staan twee `note`-regels ("hier aan te vullen") voor exacte duur en tarieven.
- "Gebruiksovereenkomst · Privacybeleid" in de footer zijn nog platte tekst zonder link.
