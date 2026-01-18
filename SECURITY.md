# Policy di Sicurezza

## Versioni Supportate

| Versione | Supportata        |
| -------- | ----------------- |
| 5.x      | :white_check_mark: |
| < 5.0    | :x:               |

## Segnalare una Vulnerabilita

La sicurezza di Collezione Manager e importante per noi. Se hai scoperto una vulnerabilita di sicurezza, ti preghiamo di segnalarla in modo responsabile.

### Come Segnalare

1. **NON** aprire una Issue pubblica per vulnerabilita di sicurezza
2. Invia una segnalazione privata tramite [GitHub Security Advisories](https://github.com/quakef4/collezione-manager/security/advisories/new)
3. In alternativa, contatta i maintainer privatamente

### Cosa Includere

Nella tua segnalazione, includi:

- Descrizione della vulnerabilita
- Passi per riprodurre il problema
- Impatto potenziale
- Suggerimenti per la correzione (se disponibili)

### Cosa Aspettarsi

- **Conferma**: Riceverai una conferma entro 48 ore
- **Aggiornamenti**: Ti terremo aggiornato sullo stato della correzione
- **Riconoscimento**: Se lo desideri, ti riconosceremo pubblicamente per la segnalazione responsabile
- **Timeline**: Puntiamo a risolvere le vulnerabilita critiche entro 7 giorni

## Considerazioni sulla Sicurezza

### Architettura dell'Applicazione

Collezione Manager e un'applicazione client-side che:

- Funziona interamente nel browser
- Salva i dati in localStorage
- Non trasmette dati a server esterni
- Carica risorse da CDN pubblici (React, jsPDF, etc.)

### Potenziali Rischi

1. **Dati Locali**: I dati sono salvati nel browser e accessibili a chiunque abbia accesso al dispositivo
2. **CDN**: Le librerie sono caricate da CDN di terze parti
3. **Import JSON**: File JSON malevoli potrebbero contenere dati problematici

### Raccomandazioni per gli Utenti

- **Backup**: Esporta regolarmente i tuoi dati
- **Browser Aggiornato**: Usa sempre l'ultima versione del browser
- **Import**: Importa solo file JSON da fonti fidate
- **Dispositivo**: Proteggi l'accesso al dispositivo dove usi l'applicazione

### Best Practice Implementate

- Sanitizzazione input utente
- Escape di caratteri speciali nell'output HTML
- Validazione dati importati
- Nessuna esecuzione di codice dinamico dai dati

## Dipendenze

Le librerie esterne sono caricate da CDN affidabili:

- React (cdnjs.cloudflare.com)
- Babel (cdnjs.cloudflare.com)
- jsPDF (cdnjs.cloudflare.com)
- JSZip (cdnjs.cloudflare.com)
- Google Fonts (fonts.googleapis.com)

## Aggiornamenti di Sicurezza

Gli aggiornamenti di sicurezza saranno pubblicati tramite:

- Release GitHub
- Security Advisories
- CHANGELOG.md

## Contatti

Per questioni di sicurezza urgenti, usa i canali privati menzionati sopra.

---

Grazie per aiutarci a mantenere Collezione Manager sicuro!
