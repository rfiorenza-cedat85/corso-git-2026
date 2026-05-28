# Installazione di Visual Studio Code (profili B e C)

Guida per l'installazione di **VS Code** su **Linux** (Debian/Ubuntu) e **Windows** (10/11)
e delle estensioni necessarie a seconda del profilo scelto in [docs/setup/README.md](README.md):

- **Profilo B (intermedio):** VS Code + estensione `mhutchie.git-graph`
- **Profilo C (completo):** VS Code + estensione **Dev Containers** (richiede Docker)

## Prerequisiti

- **Linux:** accesso a un terminale con `sudo`, connessione a Internet
- **Windows:** Windows 10 (21H2+) o Windows 11, privilegi di amministratore, connessione a Internet
- **Solo per profilo C:** Docker già installato e funzionante (vedi [setup-docker.md](setup-docker.md))

## Installazione di VS Code su Linux — repository ufficiale Microsoft

Questo passo è comune ai profili B e C.

```bash
# Pacchetti di supporto
sudo apt update
sudo apt install -y wget gpg apt-transport-https

# Chiave GPG ufficiale Microsoft
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
rm packages.microsoft.gpg

# Aggiunta del repository
echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null

# Installazione
sudo apt update
sudo apt install -y code
```

VS Code si aggiornerà automaticamente alle nuove release tramite `apt upgrade`.

Verifica:

```bash
code --version
```

## Installazione alternativa via snap (Ubuntu)

Se si preferisce gestire VS Code tramite snap (su Ubuntu desktop):

```bash
sudo snap install code --classic
```

Verifica:

```bash
code --version
```

## Installazione di VS Code su Windows

Da **PowerShell** (anche non amministratore: `winget` chiederà l'elevazione):

```powershell
winget install --id Microsoft.VisualStudioCode -e --source winget
```

In alternativa, scaricare ed eseguire l'installer ufficiale da <https://code.visualstudio.com/download> mantenendo le opzioni di default (lasciare attiva l'opzione *Add to PATH*, che permette di lanciare `code` da qualsiasi terminale).

> Chiudere e riaprire il terminale (PowerShell o Git Bash) dopo l'installazione, in modo che il `PATH` aggiornato venga caricato.

Verifica (in una nuova PowerShell o Git Bash):

```powershell
code --version
```

## Setup minimo (profilo B)

Per il profilo **B** è sufficiente installare l'estensione **Git Graph** di `mhutchie`,
che aggiunge a VS Code una vista grafica dello storico e dei branch.

ID estensione: `mhutchie.git-graph`.

Da terminale:

```bash
code --install-extension mhutchie.git-graph
```

In alternativa dal Marketplace integrato in VS Code: aprire la vista *Extensions* (`Ctrl+Shift+X`),
cercare "Git Graph" e installare l'estensione pubblicata da `mhutchie`.

> Estensioni opzionali utili (non richieste dal corso) per il profilo B:
> `eamodio.gitlens`, `davidanson.vscode-markdownlint`.

## Setup dev container (profilo C)

Per il profilo **C** serve l'estensione **Dev Containers** (ID `ms-vscode-remote.remote-containers`), che permette
di aprire il repository nel container definito in `.devcontainer/devcontainer.json`. **Richiede Docker già installato e funzionante.**

Da terminale:

```bash
# Estensione Git Graph (utile anche in profilo C)
code --install-extension mhutchie.git-graph

# Estensione Dev Containers
code --install-extension ms-vscode-remote.remote-containers
```

In alternativa dal Marketplace integrato in VS Code: aprire la vista *Extensions* (`Ctrl+Shift+X`), cercare "Dev Containers" e installare l'estensione pubblicata da Microsoft.

## Disinstallazione

Disinstallare prima le estensioni installate da questa guida (opzionale, su qualsiasi OS):

```bash
code --uninstall-extension mhutchie.git-graph
code --uninstall-extension ms-vscode-remote.remote-containers
```

Su Linux — VS Code installato via apt:

```bash
sudo apt remove --purge code
sudo rm /etc/apt/sources.list.d/vscode.list /etc/apt/keyrings/packages.microsoft.gpg
```

Su Linux — VS Code installato via snap:

```bash
sudo snap remove code
```

Su Windows:

```powershell
winget uninstall --id Microsoft.VisualStudioCode -e
```

In alternativa, dal pannello *Impostazioni → App → App installate → Visual Studio Code*.

## Riferimenti

- Installazione su Linux: <https://code.visualstudio.com/docs/setup/linux>
- Installazione su Windows: <https://code.visualstudio.com/docs/setup/windows>
- Estensione Git Graph: <https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph>
- Estensione Dev Containers: <https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers>
- Documentazione Dev Containers: <https://code.visualstudio.com/docs/devcontainers/containers>
