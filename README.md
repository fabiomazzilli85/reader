# Reader Modal

Una pagina HTML standalone che permette di incollare o scrivere del testo e aprirlo in una **modalità di lettura** a schermo intero, con controlli tipografici personalizzabili.

## Funzionalità

- **Editor di input** — area di testo con contatore di caratteri in tempo reale e pulsante di apertura disabilitato finché il campo è vuoto.
- **Modale di lettura** — si apre con un'animazione fluida e mostra il testo in un layout ottimizzato per la lettura.
- **Controlli tipografici** accessibili dalla barra superiore del modale:
  - **Dimensione del testo** — stepper da 12 px a 36 px (default 18 px).
  - **Interlinea** — stepper da 1.2 a 3.0, con passo 0.1 (default 1.8).
  - **Font** — tre opzioni selezionabili: Serif (Georgia), Sans-serif, Monospace.
  - **Tema colore** — quattro varianti: Paper (crema), Chiaro (bianco), Seppia, Scuro.
- **Barra di avanzamento** — mostra la percentuale di testo scorsa durante la lettura.
- **Chiusura** — tramite il pulsante ✕, click sull'overlay esterno oppure tasto `Esc`.

## Struttura del file

```
reader-modal.html
├── <style>          — CSS completo con variabili CSS e temi
├── <body>
│   ├── Editor card  — textarea + contatore + pulsante "Apri in lettura"
│   └── Overlay      — modale con controls bar, area testo, footer con progress
└── <script>         — logica interattiva (nessuna dipendenza esterna)
```

## Utilizzo

1. Aprire `reader-modal.html` in qualsiasi browser moderno (nessun server richiesto).
2. Incollare o digitare il testo nell'editor.
3. Cliccare **Apri in lettura**.
4. Regolare font, dimensione, interlinea e tema a piacere.
5. Scorrere il testo; la barra in basso mostra l'avanzamento.
6. Chiudere il modale con ✕, `Esc` o cliccando fuori.

## Compatibilità

Nessuna dipendenza esterna. Funziona in tutti i browser moderni che supportano:

- CSS Custom Properties
- `backdrop-filter`
- ES6 (const, arrow functions, template literals)

## Personalizzazione rapida

Le variabili CSS in `:root` e nella classe `.modal` controllano i colori principali:

```css
:root {
  --bg: #f5f4ef;
  --accent: #2d6a4f;   /* colore pulsanti e progress bar */
  --radius: 8px;
}
```

Per aggiungere un nuovo tema, creare una classe `.theme-custom` sul `.modal` e sovrascrivere le variabili `--modal-bg`, `--surface`, `--border`, `--text`, `--muted`, `--reader-color`.
