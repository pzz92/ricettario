# Come attivare la PWA - Istruzioni

## Step 1: Aggiungi questa riga nel tag `<head>` (dopo il tag `<meta name="viewport">`):

```html
<link rel="manifest" href="manifest.json">
<meta name="theme-color" content="#2a8f7e">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Ricettario">
```

## Step 2: Aggiungi questo codice prima della chiusura del tag `</body>`:

```javascript
// Registra il Service Worker
if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('service-worker.js')
        .then(registration => {
            console.log('Service Worker registrato con successo:', registration);
        })
        .catch(error => {
            console.log('Errore nella registrazione del Service Worker:', error);
        });
}
```

## Step 3: File structure richiesti

Devi avere questi tre file nella stessa cartella:
```
/
├── index.html (il file HTML principale dell'app)
├── manifest.json (il file manifest che hai ricevuto)
└── service-worker.js (il file service worker che hai ricevuto)
```

## Come installare l'app su Android:

### Chrome/Edge:
1. Apri l'app nel browser
2. Tocca il menu (⋮) in alto a destra
3. Seleziona "Installa app" oppure "Aggiungi alla schermata iniziale"
4. L'app apparirà come app standalone sulla home screen

### Firefox:
1. Apri l'app nel browser
2. Tocca il menu (≡)
3. Seleziona "Installa"

### Samsung Internet:
1. Tocca il menu
2. Seleziona "Aggiungi a Home"

## Caratteristiche della PWA:

✅ **Offline**: Funziona completamente offline
✅ **Cache**: L'app si aggiorna automaticamente
✅ **Home Screen**: Icona sulla schermata iniziale
✅ **Standalone**: Si apre come app nativa (senza barra del browser)
✅ **Dati Locali**: localStorage è preservato
✅ **Fast**: Caricamento istantaneo dalle cache

## Testing:
- Chrome DevTools → Application → Service Workers (verifica che sia registrato)
- Chrome DevTools → Application → Manifest (verifica il manifest)
- Chrome DevTools → Application → Cache (verifica i file in cache)

Tutto fatto! 🚀
