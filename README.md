# Collezione Manager

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![React](https://img.shields.io/badge/React-18.2-61DAFB?logo=react&logoColor=white)](https://reactjs.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

Applicazione web per la gestione di collezioni di macchine da scrivere e calcolatrici vintage. Progettata per collezionisti, musei e appassionati di tecnologia d'epoca.

![Collezione Manager Screenshot](docs/screenshot.png)

## Indice

- [Caratteristiche](#caratteristiche)
- [Demo](#demo)
- [Installazione](#installazione)
- [Utilizzo](#utilizzo)
- [Struttura Dati](#struttura-dati)
- [Funzionalita](#funzionalita)
- [Contribuire](#contribuire)
- [Licenza](#licenza)

## Caratteristiche

- **Gestione Completa Collezione**: Cataloga macchine da scrivere, calcolatrici meccaniche, addizionatrici e registratori di cassa
- **Categorizzazione Avanzata**: Sistema gerarchico con categorie, sottocategorie, marchi e modelli personalizzabili
- **Tracciamento Stato**: Monitora condizioni estetiche e funzionali di ogni pezzo
- **Gestione Accessori**: Registra accessori con stato (presente, mancante, ordinato, danneggiato)
- **Storico Lavori**: Documenta restauri, riparazioni e manutenzioni con costi e foto
- **Gestione Immagini**: Supporto immagini multiple per oggetto, lavori e accessori (conversione automatica WebP)
- **Localizzazione**: Traccia la posizione fisica di ogni oggetto (vetrine, scaffali, laboratorio)
- **Statistiche Dashboard**: Panoramica valore collezione, distribuzione per categoria, stato restauri
- **Import/Export JSON**: Backup completo e portabilita dei dati
- **Stampa PDF**: Genera schede dettagliate e report della collezione
- **Interfaccia Responsive**: Design elegante tema vintage, ottimizzato per desktop e tablet
- **Persistenza Locale**: Salvataggio automatico nel browser (localStorage)

## Demo

Apri semplicemente il file `collezione-manager-v5.html` nel tuo browser. Non richiede server o installazione.

**Browser supportati:**
- Google Chrome 90+
- Mozilla Firefox 88+
- Microsoft Edge 90+
- Safari 14+

## Installazione

### Metodo 1: Download Diretto

1. Scarica il file `collezione-manager-v5.html`
2. Aprilo con un browser moderno
3. Inizia a catalogare la tua collezione

### Metodo 2: Clone Repository

```bash
git clone https://github.com/quakef4/collezione-manager.git
cd collezione-manager
```

Poi apri `collezione-manager-v5.html` nel browser.

### Metodo 3: Server Locale (opzionale)

Per funzionalita avanzate o sviluppo:

```bash
# Con Python 3
python -m http.server 8080

# Con Node.js
npx serve .

# Con PHP
php -S localhost:8080
```

Poi visita `http://localhost:8080/collezione-manager-v5.html`

## Utilizzo

### Primo Avvio

Al primo avvio, l'applicazione mostra una collezione di esempio con 4 oggetti demo. Puoi:

1. **Esplorare l'interfaccia** per familiarizzare con le funzionalita
2. **Eliminare i dati demo** e iniziare da zero
3. **Importare una collezione esistente** da file JSON

### Aggiungere un Oggetto

1. Clicca su **"+ Nuovo oggetto"** nella barra superiore
2. Compila i campi richiesti:
   - **ID**: Identificativo univoco (generato automaticamente se vuoto)
   - **Marca e Modello**: Seleziona da lista o aggiungi nuovi
   - **Categoria**: Tipo di oggetto
   - **Stato funzionale**: Condizioni operative
   - **Stato estetico**: Valutazione aspetto
   - **Ubicazione**: Posizione fisica
3. Aggiungi informazioni opzionali (anno, numero serie, costo, note)
4. Carica immagini
5. Salva

### Gestione Lavori e Accessori

Per ogni oggetto puoi:

- **Aggiungere lavori**: Restauri, riparazioni, manutenzioni con data, costo e foto
- **Registrare accessori**: Custodie, manuali, nastri, cavi con stato disponibilita

### Backup e Ripristino

- **Esporta**: Menu > Esporta JSON (salva backup completo)
- **Importa**: Menu > Importa JSON (ripristina da backup)

## Struttura Dati

### Oggetto Collezione

```javascript
{
  id: "ITEM-001",
  description: "Descrizione oggetto",
  brandId: "brand-1",
  modelId: "model-1",
  category: "Macchine da scrivere portatili",
  subcategory: "Standard",
  purchaseCost: 350,
  purchaseYear: "2023",
  status: "Funzionante",
  aestheticGrade: "Ottimo",
  location: "Vetrina A",
  year: "1950",
  serialNumber: "ABC-12345",
  version: "1a serie",
  defectFound: "",
  notes: "Note aggiuntive",
  images: ["data:image/webp;base64,..."],
  works: [...],
  accessories: [...],
  dateAdded: "2024-01-10",
  lastModified: "2024-03-10"
}
```

### Categorie Predefinite

| Categoria | Descrizione |
|-----------|-------------|
| Macchine da scrivere portatili | Portatili, travel, ultracompatte |
| Macchine da scrivere da tavolo | Standard, elettriche, professionali |
| Calcolatrici meccaniche | A manovella, a tastiera |
| Calcolatrici elettroniche | Da tavolo, tascabili |
| Addizionatrici | Macchine per addizioni |
| Registratori di cassa | Casse meccaniche ed elettromeccaniche |

## Funzionalita

### Dashboard

- Valore totale collezione
- Numero oggetti per categoria
- Distribuzione stati funzionali
- Oggetti in restauro/manutenzione
- Ultimi oggetti aggiunti

### Filtri e Ricerca

- Ricerca testuale su tutti i campi
- Filtro per categoria
- Filtro per marca
- Filtro per stato
- Filtro per ubicazione
- Ordinamento per data, valore, nome

### Personalizzazione

Tutti gli elenchi sono personalizzabili:

- Categorie e sottocategorie
- Marchi e modelli
- Stati funzionali
- Gradi estetici
- Ubicazioni
- Tipi di accessori

## Stack Tecnologico

- **React 18.2**: UI library
- **Babel**: Transpiler JSX
- **jsPDF**: Generazione PDF
- **JSZip**: Gestione archivi
- **Playfair Display & Source Sans 3**: Typography
- **localStorage API**: Persistenza dati

## Contribuire

Contributi, segnalazioni bug e richieste di funzionalita sono benvenuti!

Consulta [CONTRIBUTING.md](CONTRIBUTING.md) per le linee guida.

### Segnalare Bug

Usa il template [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md)

### Richiedere Funzionalita

Usa il template [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md)

## Roadmap

- [ ] Supporto multilingua (EN, FR, DE)
- [ ] Sincronizzazione cloud opzionale
- [ ] App mobile (PWA)
- [ ] Integrazione API prezzi mercato
- [ ] Scansione codici a barre/QR
- [ ] Gestione prestiti/esposizioni temporanee

## Licenza

Questo progetto e rilasciato sotto licenza **GNU General Public License v3.0**.

Consulta il file [LICENSE](LICENSE) per i dettagli completi.

## Autore

Sviluppato con passione per il vintage computing.

## Riconoscimenti

- Design ispirato all'estetica delle macchine da scrivere Olivetti
- Icone e font da Google Fonts e CDN pubbliche
- Community dei collezionisti di macchine da scrivere italiani

---

**Collezione Manager** - Preserva la storia, un tasto alla volta.
