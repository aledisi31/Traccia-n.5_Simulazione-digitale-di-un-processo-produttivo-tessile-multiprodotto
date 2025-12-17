# Simulazione Fabbrica - Produzione multiprodotto per un'azienda del settore tessile

Questo progetto Python simula il processo produttivo di una fabbrica che realizza cappellini, magliette e pantaloni nell'arco di una giornata lavorativa di 24 ore simulate (1 ora = 1 secondo).
\_

## Descrizione generale

La simulazione rappresenta una fabbrica tessile multiprodotto che produce magliette, pantaloni e cappellini attraverso quattro fasi di lavorazione: Taglio, Cucitura, Controllo Qualità e Imballaggio.

Il modello opera su tre turni giornalieri (Mattina, Pomeriggio, Notte) e utilizza parallelismo logico per simulare la lavorazione simultanea di più prodotti.

\_

## Funzionalità principali

- Produzione multiprodotto parallela (fino a 5 prodotti in lavorazione contemporanea).
- Assegnazione fissa operatore→macchina:

  - Turni Mattina e Pomeriggio: un operatore per ogni macchina.
  - Turno Notte: un operatore per fase.

- Gestione fermi: operatori assenti o indisponibili e macchine guaste per periodi variabili.
- Produzione aggregata su base oraria per ogni coppia macchina–operatore–prodotto.
- Generazione automatica di un file CSV univoco per ogni simulazione.
- Inclusione nel CSV dei fermi di operatori e macchine.

\_

## Output nel terminale

L’esecuzione mostra una barra di avanzamento che cresce ad ogni prodotto completato.

Al termine viene visualizzato:

- Produzione totale per tipo di prodotto.
- Produzione suddivisa per turno.
- Makespan (24 ore simulate).
- Tempo complessivo di lavorazione (somma durate fasi).
- Tempo medio per unità prodotta.

\_

## Struttura del file CSV

Ogni riga contiene la produzione oraria aggregata:

```
ora_simulata,prodotto,fase,macchina,operatore,turno,quantita
```

Al termine del file vengono aggiunte due sezioni:

```
# --- OPERATORI INDISPONIBILI ---
turno,operatore,periodo_indisponibilita_ore

# --- MACCHINE GUASTE ---
turno,macchina,periodo_guasto_ore
```

\_

## Calcoli eseguiti

- Makespan della simulazione.
- Tempo totale impiegato nelle fasi di lavorazione.
- Tempo medio per unità.
- Quantità totali prodotte per tipo di prodotto.
- Quantità prodotte per turno.

\_

## Obiettivo accademico

Il modello consente di analizzare:

- l’impatto dei fermi su produttività e capacità della linea;
- la robustezza del sistema produttivo;
- la distribuzione oraria dei volumi lavorati;
- scenari realistici utili per un digital twin semplificato e per analisi in ambito di pianificazione aziendale.

\_

## Versioni precedenti

v1.0 – Produzione sequenziale
v1.1 – Parallelismo logico
v1.2 – Operatore assegnato per macchina
v1.3 – Log orario + CSV separato
v1.4 – Fermi operatori/macchine con riepilogo CSV
v1.4b – Riepilogo completo nel terminale + barra di avanzamento

\_

## Esecuzione

Per avviare la simulazione:

```
python simulazione_fabbrica_ore_v1_4b.py
```

Il CSV verrà generato automaticamente nella stessa directory dello script.

---

Creato da Di Si Alessandro
