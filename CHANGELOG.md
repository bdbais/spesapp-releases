# Changelog

Il formato segue [Keep a Changelog](https://keepachangelog.com/it/1.1.0/).

## [0.1.0] — 2026-09-09

Prima versione per i tester.

> **Firmata con una chiave di prova.** Va installata e funziona, ma quando
> uscirà la versione firmata con la chiave definitiva Android **non potrà
> aggiornarla sopra**: bisognerà disinstallare e reinstallare, perdendo gli
> scontrini registrati. Per una versione di prova è un compromesso
> accettabile; è bene saperlo prima di registrare la spesa di tre mesi.

### C'è

- **Registrazione scontrini** — foto, OCR sul dispositivo (ML Kit), estrazione
  di righe, totale, data e negozio, e una schermata di revisione dove correggere
  prima di salvare
- **Pollice su / pollice giù** su ogni prodotto, con filtro per rivedere solo
  quelli da evitare
- **Scansione al supermercato** — telecamera accesa, codice a barre, verdetto
  immediato: già comprato? ti era piaciuto?
- **Report** per categoria, negozio e mese, con il totale del periodo
- **Aggiornamenti in-app** con verifica sha256 del pacchetto scaricato

### Non c'è ancora

- La lista della spesa da compilare a casa
- Il riconoscimento dei prodotti sfusi, senza codice a barre
- I grafici e l'esportazione in CSV
- L'importazione dello storico ottenuto con la richiesta GDPR

### Cosa aspettarsi dall'OCR

Gli scontrini della grande distribuzione italiana sono scritti in decine di
modi diversi. Il riconoscimento funziona bene su scontrini distesi e ben
illuminati, e sbaglia su quelli sbiaditi o stropicciati: per questo c'è la
schermata di revisione, ed è lì che conviene guardare prima di salvare.

**Le segnalazioni utili sono quelle sulle righe sbagliate**: quale catena, cosa
c'era scritto, cosa ha capito l'app.

