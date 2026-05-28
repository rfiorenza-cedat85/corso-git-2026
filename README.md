# Corso Git (edizione 2026) - Workspace didattico

Repository didattico di supporto al **Corso Git**.

- Titolo del corso: Corso Git (edizione 2026)
- Docente: [Riccardo Fiorenza](mailto:rfiorenza@cedat85.com)

## Descrizione

Il repository raccoglie i materiali del corso destinati ai partecipanti: ambiente di sviluppo (dev container), guida di setup e risorse di riferimento.

## Struttura del repository

| Area                           | Contenuto                                | Scopo                                              |
| ------------------------------ | ---------------------------------------- | -------------------------------------------------- |
| [.devcontainer](.devcontainer) | Configurazione dev container (VS Code)   | Ambiente di sviluppo riproducibile (profilo C)     |
| [docs](docs)                   | Documentazione, guide di setup, risorse  | Materiali di riferimento del corso                 |
| [lessons](lessons)             | Materiali operativi delle sessioni       | Esercizi e tracce pubblicati sessione per sessione |
| [playground](playground)       | Spazio libero di esercitazione           | Cartella in cui i partecipanti sperimentano        |

## Calendario del corso

| Sessione    | Data       | Durata | Cartella di lavoro    |
| ----------- | ---------- | ------ | --------------------- |
| sessione-1  | 05/06/2026 | 1 ora  | `lessons/sessione-1/` |
| sessione-2  | 12/06/2026 | 2 ore  | `lessons/sessione-2/` |
| sessione-3  | 19/06/2026 | 2 ore  | `lessons/sessione-3/` |
| sessione-4  | 26/06/2026 | 2 ore  | `lessons/sessione-4/` |
| sessione-5  | 03/07/2026 | 2 ore  | `lessons/sessione-5/` |
| sessione-6  | 10/07/2026 | 1 ora  | `lessons/sessione-6/` |

## Come usare questo repository

1. Clona il repository: `git clone https://github.com/rfiorenza-cedat85/corso-git-2026.git`
2. Prepara il tuo ambiente seguendo [docs/setup/README.md](docs/setup/README.md) (prima dell'inizio del corso).
3. Consulta [docs](docs) per i materiali condivisi dal docente (guide, slide e risorse finali).

## Modalità di partecipazione

Il corso può essere seguito in due modalità:

- **Passiva** — si segue la lezione senza riprodurre i comandi sulla propria macchina.
- **Attiva** (consigliata) — si riproducono in autonomia i comandi e gli esercizi mostrati dal docente.

La modalità attiva è **fortemente consigliata** perché permette di fissare realmente le nozioni apprese e di chiarire subito eventuali dubbi.

Per la modalità attiva è necessario aver preparato in anticipo il proprio ambiente di lavoro: bastano pochi minuti, ma è fondamentale per poter seguire efficacemente le sessioni pratiche.
Si consiglia di farlo **prima della prima sessione** seguendo le istruzioni in [docs/setup/README.md](docs/setup/README.md), dove sono descritti tre profili di installazione (**A — Base**, **B — Intermedio**, **C — Completo**) tra cui scegliere in base alle proprie esigenze e preferenze. Il profilo **C** è quello usato dal docente e garantisce un ambiente isolato e identico a quello mostrato a lezione.

## Risorse consigliate

- [Pro Git (libro gratuito)](https://git-scm.com/book)
- [Learn Git Branching (interattivo)](https://learngitbranching.js.org)
- [Git-Flow: A Successful Git Branching Model](https://nvie.com/posts/a-successful-git-branching-model/)
