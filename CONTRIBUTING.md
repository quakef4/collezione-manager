# Guida per Contribuire

Grazie per il tuo interesse nel contribuire a Collezione Manager! Questo documento fornisce linee guida e istruzioni per contribuire al progetto.

## Indice

- [Codice di Condotta](#codice-di-condotta)
- [Come Contribuire](#come-contribuire)
- [Segnalazione Bug](#segnalazione-bug)
- [Richieste di Funzionalita](#richieste-di-funzionalita)
- [Pull Request](#pull-request)
- [Stile del Codice](#stile-del-codice)
- [Commit Messages](#commit-messages)
- [Sviluppo Locale](#sviluppo-locale)

## Codice di Condotta

Partecipando a questo progetto, accetti di rispettare il nostro [Codice di Condotta](CODE_OF_CONDUCT.md). Ti preghiamo di leggerlo prima di contribuire.

## Come Contribuire

Ci sono molti modi per contribuire:

1. **Segnalare bug** - Aiutaci a trovare e correggere problemi
2. **Suggerire funzionalita** - Proponi nuove idee
3. **Migliorare la documentazione** - Correggi errori o aggiungi contenuti
4. **Scrivere codice** - Implementa nuove funzionalita o correggi bug
5. **Testare** - Prova l'applicazione e segnala problemi
6. **Tradurre** - Aiuta con le traduzioni in altre lingue

## Segnalazione Bug

Prima di segnalare un bug:

1. **Verifica** che non sia gia stato segnalato cercando nelle [Issues](https://github.com/quakef4/collezione-manager/issues)
2. **Aggiorna** all'ultima versione e verifica se il problema persiste
3. **Isola** il problema creando un caso di test minimo

### Template Bug Report

Usa il template fornito in `.github/ISSUE_TEMPLATE/bug_report.md` e includi:

- Descrizione chiara del problema
- Passi per riprodurre
- Comportamento atteso vs. comportamento attuale
- Screenshot se applicabili
- Ambiente (browser, sistema operativo, versione)

## Richieste di Funzionalita

Per richiedere nuove funzionalita:

1. **Cerca** nelle Issues esistenti per evitare duplicati
2. **Descrivi** chiaramente la funzionalita e il suo caso d'uso
3. **Spiega** perche sarebbe utile per altri utenti

Usa il template in `.github/ISSUE_TEMPLATE/feature_request.md`.

## Pull Request

### Prima di iniziare

1. Apri una Issue per discutere le modifiche proposte
2. Aspetta feedback dai maintainer prima di iniziare il lavoro
3. Fork il repository e crea un branch dal `main`

### Processo

1. **Fork** il repository
2. **Crea un branch** per la tua modifica:
   ```bash
   git checkout -b feature/nome-funzionalita
   # oppure
   git checkout -b fix/descrizione-bug
   ```
3. **Implementa** le modifiche
4. **Testa** accuratamente
5. **Commit** con messaggi chiari (vedi sezione sotto)
6. **Push** al tuo fork
7. **Apri una Pull Request** verso `main`

### Checklist PR

- [ ] Il codice segue le linee guida di stile
- [ ] Ho testato le modifiche su diversi browser
- [ ] Ho aggiornato la documentazione se necessario
- [ ] Ho aggiunto test se applicabile
- [ ] I commit sono atomici e ben descritti

## Stile del Codice

### JavaScript/React

- Usa ES6+ syntax
- Preferisci `const` e `let` a `var`
- Usa arrow functions dove appropriato
- Nomi variabili/funzioni in camelCase
- Componenti React in PascalCase
- Indentazione: 2 spazi
- Punto e virgola a fine istruzione
- Virgolette singole per stringhe JS

```javascript
// Esempio di stile corretto
const MyComponent = ({ title, items }) => {
  const [isOpen, setIsOpen] = useState(false);

  const handleClick = () => {
    setIsOpen(!isOpen);
  };

  return (
    <div className="my-component">
      <h2>{title}</h2>
      {items.map(item => (
        <Item key={item.id} {...item} />
      ))}
    </div>
  );
};
```

### CSS

- Usa variabili CSS per colori e valori comuni
- Nomi classi in kebab-case
- Un selettore per riga per selettori multipli
- Ordina le proprieta alfabeticamente o per gruppo logico

```css
/* Esempio di stile corretto */
.card-container {
  background: var(--bg-card);
  border: 1px solid var(--border-subtle);
  border-radius: 8px;
  padding: 16px;
}

.card-container:hover {
  border-color: var(--border-medium);
}
```

### HTML

- Indentazione: 2 spazi
- Attributi su righe separate per elementi con molti attributi
- Usa attributi semantici (`aria-*`, `role`) dove appropriato

## Commit Messages

Segui il formato [Conventional Commits](https://www.conventionalcommits.org/):

```
<tipo>(<scope>): <descrizione>

[corpo opzionale]

[footer opzionale]
```

### Tipi

- `feat`: Nuova funzionalita
- `fix`: Correzione bug
- `docs`: Modifiche alla documentazione
- `style`: Formattazione, punto e virgola mancanti, ecc.
- `refactor`: Refactoring del codice
- `test`: Aggiunta o modifica test
- `chore`: Manutenzione, dipendenze, configurazione

### Esempi

```
feat(items): aggiunta filtro per anno di produzione

fix(export): correzione encoding caratteri speciali nel PDF

docs(readme): aggiornamento istruzioni installazione

refactor(utils): estrazione funzioni di formattazione date
```

## Sviluppo Locale

### Setup

```bash
# Clone il repository
git clone https://github.com/quakef4/collezione-manager.git
cd collezione-manager

# Apri nel browser
open collezione-manager-v5.html
# oppure avvia un server locale
python -m http.server 8080
```

### Test

Testa manualmente su:

- Chrome (ultima versione)
- Firefox (ultima versione)
- Safari (ultima versione)
- Edge (ultima versione)

Verifica:

1. Creazione/modifica/eliminazione oggetti
2. Import/export JSON
3. Generazione PDF
4. Responsive design (desktop, tablet)
5. Persistenza dati dopo refresh

### Debug

- Usa la console del browser per errori JavaScript
- Verifica localStorage in Application > Storage
- Usa React DevTools se disponibile

## Domande?

Se hai domande, apri una Issue con label `question` o contatta i maintainer.

---

Grazie per contribuire a Collezione Manager!
