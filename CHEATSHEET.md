# Cheatsheet Git (Corso Git)

Riferimento rapido ai comandi Git introdotti nel corso, aggiornato lezione per lezione: contiene solo i comandi già visti in aula.

Ultimo aggiornamento:  
**Sessione 1 — Introduzione al corso** (05/06/2026)

---

## Verifica installazione

| Comando            | Descrizione                               |
| ------------------ | ----------------------------------------- |
| `git version`      | Mostra la versione di Git installata      |
| `git flow version` | Mostra la versione di Git Flow installata |

---

## Configurazione

Git gestisce la configurazione su tre livelli, con precedenza crescente:
`system` (intero sistema) → `global` (utente corrente) → `local` (singolo
repository). Le impostazioni più specifiche sovrascrivono quelle più generiche.

| Comando                                                      | Descrizione                                                |
| ------------------------------------------------------------ | ---------------------------------------------------------- |
| `git config --global user.name "Mario Rossi"`                | Imposta il nome utente a livello globale                   |
| `git config --global user.email "mario.rossi@example.com"`   | Imposta l'email a livello globale                          |
| `git config --global core.editor "code --wait"`              | Imposta l'editor predefinito (es. VS Code)                 |
| `git config --global init.defaultBranch main`                | Imposta `main` come branch di default dei nuovi repo       |
| `git config --local user.name "Carlo Bianchi"`               | Imposta il nome utente solo per il repository corrente     |
| `git config --local user.email "carlo.bianchi@example.com"`  | Imposta l'email solo per il repository corrente            |
| `git config --system --list`                                 | Elenca la configurazione a livello di sistema              |
| `git config --global --list`                                 | Elenca la configurazione globale dell'utente               |
| `git config --local --list`                                  | Elenca la configurazione del repository corrente           |
| `git config --list`                                          | Elenca la configurazione effettiva (somma dei tre livelli) |
| `git config --list --show-origin`                            | Elenca la configurazione mostrando il file di origine      |

---

## Creare un repository

| Comando      | Descrizione                                                 |
| ------------ | ----------------------------------------------------------- |
| `git init`   | Inizializza un nuovo repository nella cartella corrente     |
| `git status` | Mostra lo stato di working directory, staging area e branch |

---
