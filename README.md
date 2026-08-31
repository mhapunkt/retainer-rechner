# Aufwandsschätzer – mh anwälte

Öffentlicher Stunden-Rechner (ohne Preise) zum Einbetten auf der Kanzlei-Website.

## Auf GitHub laden (ohne Kommandozeile)

1. Auf github.com anmelden → **New repository** → Name z. B. `aufwandsrechner` → **Public** → *Create repository*.
2. **Add file → Upload files** → `index.html` (und optional diese `README.md`) hineinziehen → **Commit changes**.

## Als Website veröffentlichen (GitHub Pages)

3. Im Repository: **Settings → Pages**.
4. Unter *Build and deployment*: **Deploy from a branch** → Branch `main` → Ordner `/ (root)` → **Save**.
5. Nach ~1 Minute erscheint die URL, Form:
   `https://DEIN-NAME.github.io/aufwandsrechner/`

## In WordPress einbetten (Enfold Code-Block oder Custom HTML)

```html
<iframe id="mhaFrame"
        src="https://DEIN-NAME.github.io/aufwandsrechner/"
        style="width:100%;border:0;min-height:900px"
        scrolling="no" title="Aufwandsschätzer"></iframe>
<script>
window.addEventListener('message', function (e) {
  if (e.data && e.data.mhaHeight) {
    document.getElementById('mhaFrame').style.height = e.data.mhaHeight + 'px';
  }
});
</script>
```

Die Seite meldet ihre Höhe automatisch an das iframe – kein Scrollbalken, passt sich der Auswahl an.

## Werte ändern

Alle Stunden, der Faktor je Mitarbeiter und die Leistungen stehen im `CONFIG`-Block
oben im `<script>` von `index.html`. Ändern → committen → Pages aktualisiert sich selbst.

## Alternative ohne GitHub

`mha-aufwandsrechner-wordpress.html` enthält denselben Rechner als Baustein zum
direkten Einfügen in einen Enfold-Code-Block (ohne iframe/Hosting).
