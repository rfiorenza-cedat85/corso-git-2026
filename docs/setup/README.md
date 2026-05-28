# Corso Git (edizione 2026) - Setup environment

Guide di **installazione** dei software necessari per seguire attivamente il corso. Le guide coprono **Linux** (distribuzioni basate su Debian/Ubuntu) e **Windows** (10/11): in ogni mattoncino le istruzioni per i due ambienti sono fornite in sezioni separate.

## Scegli il tuo profilo

Il setup è organizzato per **tre profili** di installazione, da scegliere in base alle proprie esigenze e preferenze:

| Profilo            | Livello | Per chi vuole                                            | Cosa installa                                          |
| ------------------ | ------- | -------------------------------------------------------- | ------------------------------------------------------ |
| **A — Base**       | ⭐      | lavorare solo da terminale, con il minimo indispensabile | Git + git-flow                                         |
| **B — Intermedio** | ⭐⭐    | avere un editor completo e operare anche in visuale      | Git + git-flow + VS Code + `mhutchie.git-graph`        |
| **C — Completo**   | ⭐⭐⭐  | replicare l'ambiente del docente con Docker e container  | Git + git-flow + Docker + VS Code + **Dev Containers** |

Tutti i profili sono adatti al corso; ordine di preferenza consigliato:

- Profilo C: se hai Docker già installato o sei comunque disposto ad installarlo (ne vale veramente la pena, è uno strumento molto utile e versatile)
- Profilo B: se vuoi un setup più leggero senza bisogno di Docker, ma con un editor completo e operare anche in visuale con i repository git
- Profilo A: se vuoi un setup il più minimale possibile, lavorando esclusivamente da terminale

Cosa puoi fare con ciascun profilo:

- **A — terminale puro:** tutti gli esercizi del corso: è l'esperienza più "vicina al ferro" e didatticamente la più formativa.
- **B — aggiunge VS Code + Git Graph:** editor moderno e completo + **operatività visuale** sul repository tramite Git Graph.
- **C — aggiunge il dev container:** lavorare con tutto l'ambiente già configurato, identico a quello del docente.

## Mattoncini di installazione

Le guide per-software sono indipendenti dal profilo: ogni profilo è semplicemente un sottoinsieme dei mattoncini qui sotto.

| Mattoncino                                                                | Profilo A | Profilo B | Profilo C |
| ------------------------------------------------------------------------- | :-------: | :-------: | :-------: |
| [Git](setup-git.md)                                                       |     ✓     |     ✓     |     ✓     |
| [git-flow](setup-gitflow.md)                                              |     ✓     |     ✓     |     ✓     |
| [VS Code + `mhutchie.git-graph`](setup-vscode.md#setup-minimo-profilo-b)  |     —     |     ✓     |     ✓     |
| [Docker Engine](setup-docker.md)                                          |     —     |     —     |     ✓     |
| [VS Code + Dev Containers](setup-vscode.md#setup-dev-container-profilo-c) |     —     |     —     |     ✓     |

## Ordine consigliato per profilo

Dopo aver scelto il profilo, segui **in ordine** i passi qui sotto: ogni link porta direttamente alla guida del mattoncino da installare. Al termine di ciascun passo c'è un comando di verifica per controllare che tutto sia a posto prima di proseguire.

### Profilo A — Base

1. [Installa Git](setup-git.md)
2. [Installa git-flow](setup-gitflow.md)

### Profilo B — Intermedio

1. [Installa Git](setup-git.md)
2. [Installa git-flow](setup-gitflow.md)
3. [Installa VS Code + estensione `mhutchie.git-graph`](setup-vscode.md#setup-minimo-profilo-b)

### Profilo C — Completo

1. [Installa Git](setup-git.md)
2. [Installa git-flow](setup-gitflow.md)
3. [Installa Docker Engine](setup-docker.md)
4. [Installa VS Code + estensione Dev Containers](setup-vscode.md#setup-dev-container-profilo-c)

Quando tutti i passi del tuo profilo sono completati e verificati, l'ambiente è pronto per il corso.
