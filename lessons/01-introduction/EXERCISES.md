# Sessione 1 — Introduzione a Git (Esercizi)

## Premessa

Gli esercizi proposti hanno lo scopo di consolidare i concetti introdotti durante la prima sessione e di preparare l'ambiente di lavoro per gli incontri successivi.

Si consiglia di eseguire personalmente tutti i comandi e di osservare con attenzione gli output prodotti da Git.

## Esercizio 1: Verifica dell'ambiente di lavoro

Assicurati che Git sia correttamente installato sul tuo computer.

Verifica eventualmente anche la presenza di Git Flow.

Prova ad eseguire i seguenti comandi:

```bash
git version
git flow version
```

> Nota: su Windows, se hai installato Git Flow tramite Git for Windows, potresti dover eseguire `git flow version` da Git Bash per ottenere l'output corretto.

Verifica inoltre che il tuo nome utente e il tuo indirizzo email siano configurati correttamente:

```bash
git config --global --list
```

> Obiettivo: arrivare alla prossima sessione con Git (e Git Flow) installati e configurati correttamente.

## Esercizio 2: Inizializzazione di un repository esistente

Crea una copia locale di un tuo progetto personale (o di una cartella contenente alcuni file) su cui vorresti utilizzare Git.

Posizionati nella directory del progetto ed esegui:

```bash
git init
git status
```

Osserva con attenzione l'output prodotto da Git e verifica:

* la presenza della directory `.git`;
* lo stato dei file presenti nella cartella.

> Obiettivo: prendere confidenza con la creazione di un repository Git e con il comando `git status`.
