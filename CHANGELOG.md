# Changelog

Il formato segue [Keep a Changelog](https://keepachangelog.com/it/1.1.0/).

## [0.2.0] — 2026-09-09

### Aggiunto

- **Dentro lo scontrino.** Dall'elenco si tocca uno scontrino e si vede cosa
  conteneva: ogni riga con il prezzo pagato e il pollice su / giù, da mettere
  lì, con lo scontrino ancora davanti. Il giudizio vale sul prodotto, quindi si
  ritrova allo scaffale e in tutti gli altri scontrini in cui compare.
- **Quanto è cambiato il prezzo.** Su ogni riga, se lo stesso prodotto era già
  stato comprato, compare la variazione rispetto all'ultima volta:
  *+11% da marzo (era 1,16 €)*. È il numero per cui l'app esiste. Sotto l'1%
  non viene mostrato: sono arrotondamenti, e segnalarli renderebbe rumorosa
  proprio la riga che deve essere un segnale.
- La foto dello scontrino si apre a schermo intero e si ingrandisce.
- **Lo scontrino si prende anche dalla galleria**, non solo fotografandolo:
  quello digitale che alcune catene mandano via mail arriva come immagine, e
  fotografare uno schermo sarebbe assurdo.
- **«Vedi il testo letto»** nella schermata di revisione: mostra e copia quello
  che il riconoscimento ha davvero prodotto. Se una riga non torna, allegare
  quel testo alla segnalazione la rende riproducibile — ed è così che sono
  stati trovati i due difetti qui sotto.

### Corretto

- **Nessuna riga veniva riconosciuta sugli scontrini veri.** Il riconoscimento
  del testo non restituisce «descrizione … prezzo» su una riga sola: raggruppa
  per vicinanza, e uno scontrino è a colonne, quindi le descrizioni finivano da
  una parte e i prezzi dall'altra. Ora le righe si ricostruiscono dalle
  coordinate.
- **La data veniva ignorata quando l'OCR ci infilava uno spazio** (`08/09/ 2026`)
  e si ripiegava sul giorno di oggi — senza dirlo, spostando l'acquisto nel mese
  sbagliato in tutti i report.
- Dopo aver salvato uno scontrino, le schede Prodotti e Report restavano
  ferme a quello che avevano letto prima.
- L'app si chiudeva all'avvio: la minificazione rinominava classi che il
  riconoscimento del testo cerca per nome.
- I prezzi nella revisione usavano il punto invece della virgola.

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

