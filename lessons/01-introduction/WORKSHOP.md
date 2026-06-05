# Sessione 1 — Introduzione a Git (Workshop)

## Premessa

Questa pagina raccoglie i comandi eseguiti durante il workshop, gli output ottenuti e alcune note utili per approfondire gli argomenti trattati durante la sessione.

Gli output riportati sono stati generati nell'ambiente utilizzato durante il corso e potrebbero differire leggermente in base al sistema operativo, alla versione di Git e alla configurazione locale.

> **Nota**  
> I comandi sono riportati nell'ordine in cui sono stati eseguiti durante il workshop. Alcuni output sono stati abbreviati o adattati per migliorarne la leggibilità.

## Setup dell'ambiente di lavoro

```bash
git version
```

```text
git version 2.54.0
```

```bash
git flow version
git-flow version # Con questo comando si ottiene lo stesso output del precedente
```

```text
1.12.3 (AVH Edition)
```

## Configurazione globale di Git

In questa sezione vengono configurati alcuni parametri globali di Git.  
Le impostazioni salvate a livello globale vengono applicate a tutti i repository dell'utente corrente.

```bash
git config --global --list
```

```bash
cat ~/.gitconfig
```

```bash
git config --global user.name "Mario Rossi"
git config --global user.email "mario.rossi@example.com"
```

```bash
# git config --global core.editor "vi"
# git config --global core.editor "nano"
git config --global core.editor "code --wait"
```

```bash
git config --global init.defaultBranch main
```

## Creazione del primo repository Git

Il comando `git init` crea una nuova directory nascosta `.git`, che contiene tutte le informazioni necessarie a Git per tracciare la cronologia del repository.

```bash
mkdir my-first-repo
cd my-first-repo
git init
```

```text
Initialized empty Git repository in /workspaces/corso-git-2026-examples/my-first-repo/.git/
```

```bash
git status
```

```text
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

Le sottodirectory e i file presenti all'interno di `.git` costituiscono il database interno del repository e verranno approfonditi nelle sessioni successive.

```bash
ls -la .git
```

```text
total 36
drwxr-xr-x 6 mario staff 4096 Jun  4 21:53 .
drwxr-xr-x 3 mario staff 4096 Jun  4 21:52 ..
-rw-r--r-- 1 mario staff   92 Jun  4 21:52 config
-rw-r--r-- 1 mario staff   73 Jun  4 21:52 description
-rw-r--r-- 1 mario staff   21 Jun  4 21:52 HEAD
drwxr-xr-x 2 mario staff 4096 Jun  4 21:52 hooks
drwxr-xr-x 2 mario staff 4096 Jun  4 21:52 info
drwxr-xr-x 4 mario staff 4096 Jun  4 21:52 objects
drwxr-xr-x 4 mario staff 4096 Jun  4 21:52 refs
```

## Configurazione locale di Git

```bash
cat .git/config     # Indica il file di configurazione locale del repository
```

```text
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
```

```bash
git config --local --list
```

```text
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
```

## Configurazione di Git (system, global, local)

Git gestisce la configurazione su tre livelli distinti, con precedenza crescente:

1. **system** → valida per tutti gli utenti del sistema;
2. **global** → valida per l'utente corrente;
3. **local** → valida soltanto per il repository corrente.

```bash
git config --system --list
```

```text
credential.helper=!f() { /home/vscode/.vscode-server/bin/6a44c352bd24569c417e530095901b649960f9f8/node /tmp/vscode-remote-containers-d110fc51-6087-4314-b5be-8376df596543.js git-credential-helper $*; }; f
```

```bash
git config --global --list
```

```text
user.name=Riccardo Fiorenza
user.email=r.fiorenza@cedat85.com
color.ui=auto
core.autocrlf=false
core.editor=vi
credential.helper=!f() { /home/vscode/.vscode-server/bin/6a44c352bd24569c417e530095901b649960f9f8/node /tmp/vscode-remote-containers-d110fc51-6087-4314-b5be-8376df596543.js git-credential-helper $*; }; f
init.defaultbranch=main
```

```bash
echo $HOME            # su Linux/macOS
echo %USERPROFILE%    # su Windows (cmd)
```

```bash
git config --list
```

```text
user.name=Riccardo Fiorenza
user.email=r.fiorenza@cedat85.com
color.ui=auto
core.autocrlf=false
core.editor=vi
init.defaultbranch=main
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
```

```bash
git config --local user.name "Carlo Bianchi"
git config --local user.email "carlo.bianchi@example.com"
```

```bash
git config --list --show-origin
```

```text
file:/etc/gitconfig     credential.helper=!f() { /home/vscode/.vscode-server/bin/6a44c352bd24569c417e530095901b649960f9f8/node /tmp/vscode-remote-containers-d110fc51-6087-4314-b5be-8376df596543.js git-credential-helper $*; }; f
file:/home/vscode/.gitconfig    user.name=Riccardo Fiorenza
file:/home/vscode/.gitconfig    user.email=r.fiorenza@cedat85.com
file:/home/vscode/.gitconfig    color.ui=auto
file:/home/vscode/.gitconfig    core.autocrlf=false
file:/home/vscode/.gitconfig    core.editor=vi
file:/home/vscode/.gitconfig    credential.helper=!f() { /home/vscode/.vscode-server/bin/6a44c352bd24569c417e530095901b649960f9f8/node /tmp/vscode-remote-containers-d110fc51-6087-4314-b5be-8376df596543.js git-credential-helper $*; }; f
file:/home/vscode/.gitconfig    init.defaultbranch=main
file:.git/config        core.repositoryformatversion=0
file:.git/config        core.filemode=true
file:.git/config        core.bare=false
file:.git/config        core.logallrefupdates=true
file:.git/config        user.name=Carlo Bianchi
file:.git/config        user.email=carlo.bianchi@example.com
```

L'opzione `--show-origin` consente di identificare il file da cui proviene ogni impostazione, facilitando l'analisi delle precedenze tra configurazioni system, global e local.
