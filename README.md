<div align="center">

# 🪨 Rocky Linux Docker GUI

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Rocky Linux](https://img.shields.io/badge/Rocky_Linux-10B981?style=for-the-badge&logo=rockylinux&logoColor=white)](https://rockylinux.org/)
[![KasmVNC](https://img.shields.io/badge/KasmVNC-FF6B35?style=for-the-badge&logo=vnc&logoColor=white)](https://kasmweb.com/kasmvnc)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

**🇫🇷 Français** | [🇬🇧 English](#-english-version)

</div>

---

> [!WARNING]
> **DISCLAIMER** — Le fichier `docker-compose.yml` a été généré via **Claude Sonnet 4.6** (Anthropic).
> Ce projet est destiné à un usage éducatif et légal uniquement. Toute utilisation malveillante est strictement interdite.

---

## 📋 Prérequis

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installé et lancé
- Un navigateur **Chrome ou Edge** (recommandé pour le copier-coller seamless)

---

## 🚀 Installation

### 1. Télécharger le dossier `rocky-lab` depuis GitHub et extraire le dossier

### 2. Ouvrir un terminal et accéder au dossier `rocky-lab`

```bash
cd /chemin/vers/rocky-lab
```

### 3. Configurer le mot de passe dans le fichier `.env`

```bash
# Éditer le fichier .env
VNC_PW=Changeme!   # ← remplacer par ton mot de passe
```

## ▶️ Lancer le conteneur

```bash
# Démarrer en arrière-plan
docker compose up -d
```

Puis ouvrir dans le navigateur :

```
https://localhost:6901
```

> [!NOTE]
> Accepter l'avertissement de certificat auto-signé dans le navigateur.

Le bureau Rocky Linux 9 (GNOME) doit apparaître après authentification :

```
Utilisateur : kasm_user
Mot de passe : (valeur de VNC_PW dans .env)
```

---

## 📋 Copier-Coller

| Navigateur | Comportement |
|------------|-------------|
| **Chrome / Edge** | Seamless — fonctionne directement comme en local |
| **Firefox** | Cliquer sur l'icône presse-papier 📋 en haut à gauche de l'interface |

---

## ⌨️ Commandes essentielles

### Gestion du conteneur

| Commande | Description |
|----------|-------------|
| `docker compose up -d` | Démarrer le conteneur |
| `docker compose down` | Arrêter le conteneur |
| `docker compose down -v` | Arrêter le conteneur et supprimer les volumes |
| `docker rm -f rocky-linux` | Supprimer le conteneur de force |
| `docker rm rocky-linux` | Supprimer le conteneur (arrêté uniquement) |

### Accès shell direct (sans GUI)

| Commande | Description |
|----------|-------------|
| `docker exec -it rocky-linux bash` | Ouvrir un shell dans le conteneur |
| `docker logs rocky-linux` | Voir les logs du conteneur |
| `exit` | Quitter le shell |

---

## 🛠️ Post-déploiement

```bash
# Ouvrir un shell dans le conteneur
docker exec -it rocky-linux bash

# Mettre à jour les paquets
dnf update -y

# Installer des outils courants
dnf install -y vim curl wget git net-tools

# Installer des groupes de paquets
dnf groupinstall -y "Development Tools"
```

---

## 📁 Structure du projet

```
rocky_linux/
├── docker-compose.yml   # Configuration Docker
├── .env                 # Mot de passe VNC (ne pas commiter)
├── shared/              # Dossier partagé hôte ↔ conteneur
```

---

---

## 🇬🇧 English Version

<div align="center">

**[🇫🇷 Français](#-prérequis)** | 🇬🇧 English

</div>

---

> [!WARNING]
> **DISCLAIMER** — The `docker-compose.yml` file was generated using **Claude Sonnet 4.6** (Anthropic).
> This project is intended for educational and legal use only. Any malicious use is strictly prohibited.

---

## 📋 Requirements

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running
- A **Chrome or Edge** browser (recommended for seamless clipboard support)

---

## 🚀 Installation

### 1. Download the `rocky-lab` folder from GitHub and extract it

### 2. Open a terminal and navigate to the `rocky-lab` folder

```bash
cd /path/to/rocky-lab
```

### 3. Set your password in the `.env` file

```bash
# Edit the .env file
VNC_PW=Changeme!   # ← replace with your password
```

---

## ▶️ Start the container

```bash
# Start in background
docker compose up -d
```

Then open your browser at:

```
https://localhost:6901
```

> [!NOTE]
> Accept the self-signed certificate warning in your browser.

The Rocky Linux 9 desktop (GNOME) will appear after authentication:

```
Username : kasm_user
Password : (value of VNC_PW in .env)
```

---

## 📋 Copy-Paste

| Browser | Behavior |
|---------|----------|
| **Chrome / Edge** | Seamless — works directly like a local desktop |
| **Firefox** | Click the clipboard icon 📋 in the top-left of the interface |

---

## ⌨️ Essential commands

### Container management

| Command | Description |
|---------|-------------|
| `docker compose up -d` | Start the container |
| `docker compose down` | Stop the container |
| `docker compose down -v` | Stop the container and delete volumes |
| `docker rm -f rocky-linux` | Force delete the container |
| `docker rm rocky-linux` | Delete the container (stopped only) |

### Direct shell access (without GUI)

| Command | Description |
|---------|-------------|
| `docker exec -it rocky-linux bash` | Open a shell inside the container |
| `docker logs rocky-linux` | View container logs |
| `exit` | Exit the shell |

---

## 🛠️ Post-deployment

```bash
# Open a shell inside the container
docker exec -it rocky-linux bash

# Update packages
dnf update -y

# Install common tools
dnf install -y vim curl wget git net-tools

# Install package groups
dnf groupinstall -y "Development Tools"
```

---

## 📁 Project structure

```
rocky_linux/
├── docker-compose.yml   # Docker configuration
├── .env                 # VNC password (do not commit)
├── shared/              # Shared folder host ↔ container
```

---

<div align="center">

Made with ❤️ — Powered by [Rocky Linux](https://rockylinux.org/) & [Docker](https://www.docker.com/)

</div>
