# Istruzioni per GitHub Copilot — corso-git-2026

## Contesto del progetto

Questo è il repository **per i partecipanti** del **Corso Git (edizione 2026)**, un corso interno aziendale rivolto a sviluppatori software con livello misto (da principianti a utenti basici).

- Repository: `rfiorenza-cedat85/corso-git-2026` (public)
- Docente: Riccardo Fiorenza

Il repository serve come **workspace di lavoro** durante le sessioni del corso: contiene il dev container, la guida di setup, le risorse di riferimento distribuite dal docente e una cartella `playground/` vuota dove i partecipanti possono sperimentare i comandi Git visti a lezione.

## Architettura a due repository

Il corso è organizzato su due repository: **questo è il repo pubblico per i partecipanti**. I sorgenti editoriali del docente (scalette, esercizi, **soluzioni**, tooling di build) vivono in un repository separato e privato (`corso-git-2026-authoring`) non accessibile da qui. Le soluzioni degli esercizi non vanno chieste a Copilot: sono materiale che il docente discute a lezione dopo i tentativi in autonomia dei partecipanti.

## Struttura del repository

```text
corso-git-2026/
├── README.md                        ← benvenuto e istruzioni d'uso
├── .devcontainer/                   ← ambiente di sviluppo Dev Container (Docker + VS Code)
├── docs/
│   ├── setup/                       ← guida di setup ambiente (prerequisiti, profili A/B/C)
│   ├── slides/                      ← slide del corso (pubblicate dal docente)
│   └── resources/                   ← risorse di riferimento (Pro Git, cheat sheet, GitFlow)
├── lessons/                         ← materiali operativi delle sessioni (popolata gradualmente)
├── playground/                      ← area libera per esercitarsi (vuota, da popolare)
└── .github/
    └── copilot-instructions.md      ← questo file
```

Eventuali altre sottocartelle compaiono mano a mano che il docente pubblica nuovi materiali.

## Come Copilot deve aiutare i partecipanti

- **Spiegare i comandi Git** che il partecipante sta provando in `playground/`, in modo chiaro e adatto a un livello principiante–intermedio.
- **Suggerire alternative idiomatiche** quando un comando è verboso o ha forme più moderne (es. `git switch` vs `git checkout`).
- **Diagnosticare errori** comuni in output di Git (conflitti, detached HEAD, push respinti, ecc.) e proporre come risolverli.
- **Non eseguire commit o push automatici** senza esplicita richiesta del partecipante.
- **Non risolvere gli esercizi del corso al posto del partecipante**: se viene chiesto "qual è la soluzione dell'esercizio NN", invitare a provare prima in autonomia e a confrontarsi con il docente.

## Regole di stile per i file nel repository

### File Markdown

Tutti i file `.md` devono essere ben formattati e passare [markdownlint](https://github.com/DavidAnson/markdownlint) con le regole di default.

### File di codice nel playground

Il contenuto di `playground/` è libero: Copilot non deve imporre convenzioni rigide, ma può suggerire buone pratiche quando appropriato.

## Messaggi di commit

Quando Copilot propone un messaggio di commit:

- usare **l'italiano** all'imperativo (es. "Aggiunge prima prova di branching");
- essere brevi e descrittivi;
- preferire un messaggio per ogni cambiamento logico (uno dei concetti che il corso insegna).

## Setup dell'ambiente

I partecipanti scelgono tra tre profili di installazione descritti in [docs/setup/README.md](../docs/setup/README.md):

- **A — Base**: Git + git-flow (solo terminale)
- **B — Intermedio**: Git + git-flow + VS Code + `mhutchie.git-graph`
- **C — Completo** ⭐: Git + git-flow + Docker + VS Code + Dev Containers (è il profilo usato dal docente e garantisce un ambiente identico a quello mostrato a lezione)

Se il partecipante apre questo repository in Dev Container, l'ambiente è già configurato con Git aggiornato e tutto il necessario.
