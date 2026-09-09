# SpesAPP — Releases

Distribuzione degli APK di **SpesAPP** e manifest per l'aggiornamento
automatico in-app.

Qui non ci sono sorgenti: questo repository contiene solo binari firmati,
il changelog e `latest.json`. Il codice sta in un repository privato.

## Installazione (Android)

1. Scarica l'APK più recente da [Releases](../../releases/latest)
2. Consenti l'installazione da origini sconosciute quando Android lo chiede
3. Dagli aggiornamenti successivi ci pensa l'app

## Aggiornamenti automatici

L'app legge [`latest.json`](latest.json) e confronta `versionCode` con la
versione installata. Se è più alto propone il download.

```json
{
  "versionName": "0.1.0",
  "versionCode": 1,
  "releaseDate": "2026-09-09",
  "mandatory": false,
  "notes": "Vedi CHANGELOG.md",
  "android": {
    "url": "https://github.com/.../releases/download/v0.1.0/spesapp-0.1.0.apk",
    "sha256": "…",
    "sizeBytes": 0
  }
}
```

| Campo | Significato |
|---|---|
| `versionCode` | Intero crescente, corrisponde al `+n` di `pubspec.yaml`. È l'unico campo su cui si decide se aggiornare. |
| `mandatory` | Se `true`, l'app blocca l'uso finché non si aggiorna. Da usare solo per bug che corrompono i dati. |
| `android.sha256` | Checksum verificato dopo il download: se non corrisponde, il file viene scartato. |

## Verificare un APK a mano

```bash
sha256sum spesapp-0.1.0.apk
```

Deve corrispondere al campo `android.sha256` di `latest.json`.

## iOS

Non distribuito da qui: su iOS il sideload non è possibile, si passerà da
TestFlight.
