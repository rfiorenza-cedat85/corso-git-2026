# Installazione di Docker

Guida per l'installazione di **Docker** su **Linux** (Debian/Ubuntu, tramite **Docker Engine** dal repository APT ufficiale) e **Windows** (10/11, tramite **Docker Desktop** con backend WSL2).

## Prerequisiti

- **Linux:** distribuzione Debian/Ubuntu supportata, accesso a un terminale con `sudo`, connessione a Internet
- **Windows:** Windows 10 64-bit (versione 22H2 o successiva) oppure Windows 11, virtualizzazione abilitata da BIOS/UEFI, privilegi di amministratore, connessione a Internet

> **Nota licenza Docker Desktop su Windows.** Docker Desktop è gratuito per uso personale, scopi educativi e per aziende piccole; per le organizzazioni più grandi è richiesta una sottoscrizione **Pro/Team/Business**. Verificare con il proprio reparto IT prima dell'installazione in contesto aziendale. Riferimento: <https://docs.docker.com/subscription/>.

## Installazione su Linux — Docker Engine

### Rimozione di eventuali versioni vecchie

Prima di installare la versione ufficiale, rimuovere pacchetti obsoleti che potrebbero creare conflitti:

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do
    sudo apt remove -y "$pkg" || true
done
```

### Aggiunta del repository ufficiale Docker (APT)

Pacchetti comuni necessari per gestire repository HTTPS e chiavi GPG:

```bash
sudo apt update
sudo apt install -y ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
```

Eseguire **solo il blocco corrispondente alla propria distribuzione**.

#### Debian

```bash
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] \
  https://download.docker.com/linux/debian $(. /etc/os-release && echo \"$VERSION_CODENAME\") stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### Ubuntu

```bash
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] \
  https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo \"$VERSION_CODENAME\") stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Installazione dei pacchetti Docker

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Avvio e abilitazione del servizio

```bash
sudo systemctl enable --now docker
```

### (Opzionale) Uso di Docker senza `sudo`

Aggiungere il proprio utente al gruppo `docker`:

```bash
sudo usermod -aG docker "$USER"
```

> Effettuare **logout e login** (o riavviare la sessione) affinché il nuovo gruppo diventi effettivo.
> Da quel momento sarà possibile eseguire `docker ...` senza `sudo`.
> Attenzione: l'appartenenza al gruppo `docker` equivale di fatto a privilegi root sulla macchina.

### Verifica

```bash
docker --version
docker compose version
sudo docker run --rm hello-world
```

L'ultimo comando scarica un'immagine di test, avvia un container e stampa un messaggio: se completa correttamente, il daemon Docker è funzionante.

## Installazione su Windows — Docker Desktop

### Abilitazione di WSL2

Docker Desktop su Windows usa **WSL2** come backend. Su Windows 10/11 aggiornati, aprire **PowerShell come amministratore** ed eseguire:

```powershell
wsl --install
```

Il comando abilita le funzionalità Windows necessarie, installa WSL2 e una distribuzione Linux di default (Ubuntu). Al termine, **riavviare il computer**.

Se WSL è già installato, assicurarsi di usare la versione 2 come default:

```powershell
wsl --set-default-version 2
wsl --update
```

### Installazione di Docker Desktop

Da **PowerShell** (anche non amministratore: `winget` chiederà l'elevazione):

```powershell
winget install --id Docker.DockerDesktop -e
```

In alternativa, scaricare l'installer ufficiale da <https://www.docker.com/products/docker-desktop/> ed eseguirlo mantenendo le opzioni di default (lasciare selezionata l'opzione *Use WSL 2 instead of Hyper-V*).

Dopo l'installazione, **riavviare il computer** se richiesto, quindi avviare **Docker Desktop** dal menu Start e attendere che l'icona nella system tray diventi verde (daemon attivo).

### Verifica

In una nuova PowerShell:

```powershell
docker --version
docker compose version
docker run --rm hello-world
```

Su Windows non serve `sudo`: Docker Desktop espone già il comando `docker` all'utente corrente.

## Disinstallazione

Su Linux:

```bash
sudo apt remove --purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo rm -rf /var/lib/docker /var/lib/containerd
sudo rm /etc/apt/sources.list.d/docker.list /etc/apt/keyrings/docker.asc
```

Su Windows:

```powershell
winget uninstall --id Docker.DockerDesktop -e
```

In alternativa, dal pannello *Impostazioni → App → App installate → Docker Desktop*.

## Riferimenti

- Installazione su Debian: <https://docs.docker.com/engine/install/debian/>
- Installazione su Ubuntu: <https://docs.docker.com/engine/install/ubuntu/>
- Post-installazione Linux: <https://docs.docker.com/engine/install/linux-postinstall/>
- Docker Desktop per Windows: <https://docs.docker.com/desktop/install/windows-install/>
- WSL2 (Microsoft): <https://learn.microsoft.com/windows/wsl/install>
- Sottoscrizioni Docker: <https://docs.docker.com/subscription/>
