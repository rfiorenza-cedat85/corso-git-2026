# Installazione di git-flow

[**git-flow**](https://github.com/petervanderdoes/gitflow-avh) è un'estensione di Git che aggiunge i comandi `git flow <...>` per applicare il workflow GitFlow in modo guidato.

Serve a partire dalla **sessione 4** del corso; per le sessioni precedenti non è necessario. È comunque consigliato installarlo insieme a Git durante il setup iniziale, così da non doverci pensare più avanti.

## Prerequisiti

- **Git** già installato e funzionante (vedi [setup-git.md](setup-git.md))
- **Linux:** accesso a un terminale con `sudo`, connessione a Internet
- **Windows:** Git for Windows installato (include già git-flow, vedi sotto)

## Installazione su Linux

Su Debian/Ubuntu il pacchetto `git-flow` corrisponde alla *AVH edition* (quella attualmente mantenuta):

```bash
sudo apt update
sudo apt install -y git-flow
```

Verifica:

```bash
git flow version
```

## Installazione su Windows

**git-flow (AVH edition) è già incluso in Git for Windows**: non serve installare nulla in più.

Verifica (in PowerShell o Git Bash):

```powershell
git flow version
```

## Disinstallazione

Su Linux:

```bash
sudo apt remove --purge git-flow
sudo apt autoremove
```

Su Windows: git-flow non è disinstallabile separatamente, fa parte di Git for Windows. Per rimuoverlo occorre disinstallare Git stesso (vedi [setup-git.md](setup-git.md#disinstallazione)).

## Riferimenti

- git-flow (AVH edition): <https://github.com/petervanderdoes/gitflow-avh>
- Pacchetto Debian `git-flow`: <https://packages.debian.org/stable/git-flow>
