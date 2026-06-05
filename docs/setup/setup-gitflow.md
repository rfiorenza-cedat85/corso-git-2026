# Installazione di git-flow

[**git-flow**](https://github.com/gittower/git-flow-next) è un'estensione di Git che aggiunge i comandi `git flow <...>` per applicare il workflow GitFlow in modo guidato.

Serve a partire dalla **sessione 4** del corso; per le sessioni precedenti non è necessario. È comunque consigliato installarlo insieme a Git durante il setup iniziale, così da non doverci pensare più avanti.

> **Nota sull'implementazione usata**
>
> Il progetto storico [`gitflow-avh`](https://github.com/petervanderdoes/gitflow-avh) non è più mantenuto (ultima release del 2019, repository archiviata nel 2023) e dal 2024 non è più incluso nel pacchetto di Git for Windows.  
> Su Windows si usa quindi [`git-flow-next`](https://github.com/gittower/git-flow-next), una reimplementazione moderna e attivamente mantenuta. I comandi `git flow ...` restano gli stessi.

## Prerequisiti

- **Git** già installato e funzionante (vedi [setup-git.md](setup-git.md))
- **Linux:** accesso a un terminale con `sudo`, connessione a Internet
- **Windows:** Git for Windows installato; permessi di amministratore per copiare il file nella cartella di Git

## Installazione su Linux

Su Debian/Ubuntu il pacchetto `git-flow` corrisponde alla *AVH edition*:

```bash
sudo apt update
sudo apt install -y git-flow
```

Verifica:

```bash
git flow version
```

## Installazione su Windows

Il metodo consigliato è copiare manualmente il binario nella cartella di Git for Windows:

1. Apri la [pagina delle release di git-flow-next](https://github.com/gittower/git-flow-next/releases/latest) e scarica l'asset `git-flow-next-vX.Y.Z-windows-amd64.zip`.
2. Estrai dallo ZIP il file `git-flow-vX.Y.Z-windows-amd64.exe`.
3. Rinominalo in `git-flow.exe`.
4. Copialo in `C:\Program Files\Git\mingw64\bin` (servono i permessi di amministratore). È la cartella dei binari di Git, già presente nel `PATH`.
5. Apri (o riapri) Git Bash o PowerShell e verifica:

   ```powershell
   git flow version
   ```

   L'output atteso è simile a `git-flow-next version 1.0.0`.

### Alternativa: installazione con winget

`git-flow-next` è disponibile anche come pacchetto winget (`GitTower.GitFlowNext`), ma con due limiti:

- il pacchetto è di tipo *portable* e il link `git-flow.exe` viene creato in `%LOCALAPPDATA%\Microsoft\WinGet\Links` solo se PowerShell viene eseguito **come amministratore** (oppure se è attiva la *Modalità sviluppatore* di Windows). Senza questi requisiti l'installazione termina senza errori ma `git flow` non funziona;
- la versione disponibile su winget è spesso **più vecchia** dell'ultima release ufficiale.

Se accetti questi limiti, da una PowerShell aperta come amministratore:

```powershell
winget install GitTower.GitFlowNext
```

Chiudi e riapri la shell, poi verifica con `git flow version`. In caso contrario, usa il metodo manuale descritto sopra.

## Disinstallazione

Su Linux:

```bash
sudo apt remove --purge git-flow
sudo apt autoremove
```

Su Windows: elimina il file `git-flow.exe` da `C:\Program Files\Git\mingw64\bin` (se hai usato il metodo manuale) oppure esegui `winget uninstall GitTower.GitFlowNext` (se hai usato winget).

## Riferimenti

- git-flow-next (mantenuto): <https://github.com/gittower/git-flow-next>
- gitflow-avh (archiviato, solo storico): <https://github.com/petervanderdoes/gitflow-avh>
- Pacchetto Debian `git-flow`: <https://packages.debian.org/stable/git-flow>
