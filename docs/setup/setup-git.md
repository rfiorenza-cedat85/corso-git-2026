# Installazione di Git

Guida per l'installazione di **Git** su **Linux** (Debian/Ubuntu) e **Windows** (10/11).

## Prerequisiti

- **Linux:** distribuzione Debian/Ubuntu supportata, accesso a un terminale con `sudo`, connessione a Internet
- **Windows:** Windows 10 (21H2+) o Windows 11, account con privilegi di amministratore, connessione a Internet

## Installazione su Linux — repository APT (consigliata)

```bash
sudo apt update
sudo apt install -y git
```

Questo metodo installa la versione di Git distribuita dalla propria release di Debian/Ubuntu.  
È il metodo standard e sufficiente per il corso.

Verifica:

```bash
git --version
```

## Installazione su Linux — versione più recente (PPA, solo Ubuntu)

Se serve una versione più aggiornata di Git rispetto a quella nei repository ufficiali (es. per funzionalità recenti):

```bash
# Su immagini Ubuntu minimali, 'add-apt-repository' non è preinstallato
sudo apt update
sudo apt install -y software-properties-common

sudo add-apt-repository -y ppa:git-core/ppa
sudo apt update
sudo apt install -y git
```

Il PPA `git-core/ppa` è mantenuto dagli sviluppatori di Git e fornisce le release stabili più recenti per le versioni LTS di Ubuntu. Su Debian non è disponibile: usare l'installazione da repository APT standard descritta sopra.

Verifica:

```bash
git --version
```

## Installazione su Windows — Git for Windows

Aprire **PowerShell** (anche senza privilegi di amministratore: `winget` chiederà l'elevazione se necessario) ed eseguire:

```powershell
winget install --id Git.Git -e --source winget
```

In alternativa, scaricare ed eseguire l'installer ufficiale da <https://git-scm.com/download/win> mantenendo le opzioni di default.

Git for Windows installa anche **Git Bash**, una shell Bash utilizzabile durante il corso al posto di PowerShell se si preferisce un ambiente simile a Linux.

> Chiudere e riaprire il terminale (PowerShell o Git Bash) dopo l'installazione, in modo che il `PATH` aggiornato venga caricato.

Verifica (in una nuova PowerShell o Git Bash):

```powershell
git --version
```

## Disinstallazione

Su Linux:

```bash
sudo apt remove --purge git
sudo apt autoremove
```

Su Windows:

```powershell
winget uninstall --id Git.Git -e
```

In alternativa, dal pannello *Impostazioni → App → App installate → Git*.

## Riferimenti

- Git — sito ufficiale: <https://git-scm.com/download>
- Git su Linux: <https://git-scm.com/download/linux>
- Git for Windows: <https://gitforwindows.org/>
- PPA git-core: <https://launchpad.net/~git-core/+archive/ubuntu/ppa>
