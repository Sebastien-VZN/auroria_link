<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Logo" width="150"/>
  <h1>AuroriaLink</h1>
  <p><strong>A real-time team messaging solution.</strong></p>
  
  <p>
    <img src="https://img.shields.io/badge/status-beta-blue?style=for-the-badge" alt="Project Status: Beta"/>
    <img src="https://img.shields.io/badge/license-Proprietary-red?style=for-the-badge" alt="License: Proprietary"/>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Version-0.8.4%20(26)-blueviolet?style=flat-square&logo=github" alt="Version"/>
    <img src="https://img.shields.io/badge/Release%20Date-2026--03--03-blue?style=flat-square&logo=calendar" alt="Release Date"/>
  </p>
</div>

**AuroriaLink** — private encrypted messaging for teams. Group channels, file sharing, zero tracking.

---

## 🚀 Get the Latest Version

<div align="center">
  <table>
    <tr>
      <td align="center" width="33%">
        <a href="INSTALL_ANDROID.md">
          <img src="https://img.shields.io/badge/Android-Install-2E7D32?style=for-the-badge&logo=android&logoColor=white" alt="Install for Android"/>
        </a>
        <br/>
        <sub>APK • <a href="INSTALL_ANDROID.md">Installation guide</a></sub>
      </td>
      <td align="center" width="33%">
        <a href="INSTALL_WINDOWS.md">
          <img src="https://img.shields.io/badge/Windows-Install-3A6DF0?style=for-the-badge&logo=windows11&logoColor=white" alt="Install for Windows"/>
        </a>
        <br/>
        <sub>ZIP • <a href="INSTALL_WINDOWS.md">Installation guide</a></sub>
      </td>
      <td align="center" width="33%">
        <a href="INSTALL_LINUX.md">
          <img src="https://img.shields.io/badge/Linux-Install-8A6DF0?style=for-the-badge&logo=linux&logoColor=white" alt="Install for Linux"/>
        </a>
        <br/>
        <sub>Debian 13 • <a href="INSTALL_LINUX.md">Installation guide</a></sub>
      </td>
    </tr>
  </table>
</div>

<p align="center">
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases">
    <img src="https://img.shields.io/badge/View_All-Releases-gray?style=flat&logo=github" alt="All Releases"/>
  </a>
</p>

## 🎥 Preview

<div align="center">
  <a href="https://github.com/Sebastien-VZN/auroria_link/raw/main/image/output_auroria.mp4">
    <img src="image/desktop_1.jpg" alt="Watch the demo video" width="500">
  </a>
  <p><sub><em>▶ Click to watch the demo — real-time messaging in action</em></sub></p>
</div>

## 📋 Table of Contents

- [⚠️ Project Status](#️-project-status-beta-version)
- [✨ Key Features](#-key-features)
- [💻 Supported Platforms](#-supported-platforms)
- [🚀 Installation](#-installation)
- [🎨 Gallery](#-gallery)
- [🤖 Bot API](#-bot-api)
- [🌐 About Axomind](#-about-axomind)
- [🤝 Contributing & Feedback](#-contributing--feedback)
- [👤 Author](#-author)
- [🇫🇷 Version Française](#-version-française)

---

### ⚠️ Project Status: Beta Version

> This project is currently in active development. Bugs and unexpected behaviors are therefore likely. All feedback is welcome.

> **📧 Email limitation:** Microsoft email addresses (Outlook, Hotmail, Live) are currently blocked due to Microsoft blacklisting my server IP. Please use Gmail or other email providers for registration and 2FA. Also check your spam folder if you don't receive the verification email.

---

### ✨ Key Features

**🔒 Privacy & Security**
- 🔒 **Full Encryption** — Messages and files are encrypted on the server and in transit. Your conversations stay private.
- 🛡️ **2FA Protection** — Email-based two-factor authentication (6-digit PIN) with brute force and IP tracking protection
- 🔐 **Access Control** — Each member only accesses what they're authorized to, with role-based permissions

**⚡ Real-Time**
- ⚡ **Instant Delivery** — Messages arrive in real-time, with automatic reconnection if you lose network
- 📱 **Multi-Device** — Stay connected from desktop and mobile at the same time (up to 2 devices)

**💬 Messaging**
- 👥 **Private Channels** — Dedicated spaces for your teams, projects, or topics
- 🎤 **Audio Messages** — Record and send voice clips in your conversations
- 📎 **File Sharing** — Up to 10 files per message (documents, images, videos, audio — 10 MB each)
- ⏱️ **Smart Retention** — Messages kept 6 months on server / 1 year locally, with optional 24h auto-delete · Files kept 1 month (3 months if pinned)

**🧩 Integrations**
- 🤖 **Bot API** — Connect your tools: CI/CD, monitoring, automation platforms (n8n, Make, Zapier...)
- 🔗 **Contextual Linking** — Attach conversations to your projects, tasks, or any external resource

---

<details>
<summary>🛠️ <strong>Tech Stack</strong> — for the curious</summary>

<br/>

<p align="center">
  <a href="https://www.php.net/" target="_blank"><img src="https://img.shields.io/badge/PHP-8.4-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP 8.4"/></a>
  <a href="https://flutter.dev/" target="_blank"><img src="https://img.shields.io/badge/Flutter-Stable-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter"/></a>
  <a href="https://nodejs.org/" target="_blank"><img src="https://img.shields.io/badge/Node.js-LTS-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/></a>
  <a href="https://www.postgresql.org/" target="_blank"><img src="https://img.shields.io/badge/PostgreSQL-Latest-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/></a>
  <a href="https://www.nginx.com/" target="_blank"><img src="https://img.shields.io/badge/Nginx-Stable-269539?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx"/></a>
  <a href="https://www.debian.org/" target="_blank"><img src="https://img.shields.io/badge/Debian-13-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt="Debian 13"/></a>
</p>

**How it works:**
1. **Client** connects via HTTPS for auth/data and WSS for real-time messaging
2. **WebSocket Server** handles instant bidirectional communication with heartbeat (30s) and multi-device support (max 2 connections)
3. **Backend** manages 5 security layers (route validation, brute force, 2FA, AES-256-GCM, multi-device), with 4-level RAM cache for optimal performance
4. **Database** stores encrypted data with intelligent retention policies and optimized indexes for fast queries

</details>

---

## 💻 Supported Platforms

| Platform | Status                 |
|:--------:|:-----------------------|
| Android  | ✅ Supported           |
| Windows  | ✅ Supported           |
| Linux    | ✅ Supported           |
| macOS    | ❌ Not yet supported   |
| iOS      | ❌ Not yet supported   |

---

## 🚀 Installation

Choose your platform for detailed installation instructions:

- **[Android Installation Guide](INSTALL_ANDROID.md)** - APK installation for all Android versions
- **[Windows Installation Guide](INSTALL_WINDOWS.md)** - ZIP installation for Windows 10+
- **[Linux Installation Guide](INSTALL_LINUX.md)** - Binary installation for Debian 13

---

## 🎨 Gallery

### 💻 Desktop Experience

<p align="center">
  <img src="image/desktop_1.jpg" alt="Desktop Screenshot 1" width="49%"/>
  <img src="image/desktop_2.jpg" alt="Desktop Screenshot 2" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_3.jpg" alt="Desktop Screenshot 3" width="49%"/>
  <img src="image/desktop_4.jpg" alt="Desktop Screenshot 4" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_5.jpg" alt="Desktop Screenshot 5" width="49%"/>
  <img src="image/desktop_6.jpg" alt="Desktop Screenshot 6" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_7.jpg" alt="Desktop Screenshot 7" width="49%"/>
  <img src="image/desktop_8.jpg" alt="Desktop Screenshot 8" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_9.jpg" alt="Desktop Screenshot 9" width="49%"/>
  <img src="image/desktop_10.jpg" alt="Desktop Screenshot 10" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_11.jpg" alt="Desktop Screenshot 11" width="49%"/>
  <img src="image/desktop_12.jpg" alt="Desktop Screenshot 12" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_13.jpg" alt="Desktop Screenshot 13" width="49%"/>
  <img src="image/desktop_14.jpg" alt="Desktop Screenshot 14" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_15.jpg" alt="Desktop Screenshot 15" width="49%"/>
</p>

### 📱 Mobile Experience

<p align="center">
  <img src="image/mobil_0.jpg" alt="Mobile Screenshot 0" width="19%"/>
  <img src="image/mobil_1.jpg" alt="Mobile Screenshot 1" width="19%"/>
  <img src="image/mobil_2.jpg" alt="Mobile Screenshot 2" width="19%"/>
  <img src="image/mobil_3.jpg" alt="Mobile Screenshot 3" width="19%"/>
  <img src="image/mobil_4.jpg" alt="Mobile Screenshot 4" width="19%"/>
</p>

<p align="center">
  <img src="image/mobil_5.jpg" alt="Mobile Screenshot 5" width="19%"/>
  <img src="image/mobil_5.png" alt="Mobile Screenshot 5 (alt)" width="19%"/>
  <img src="image/mobil_6.jpg" alt="Mobile Screenshot 6" width="19%"/>
  <img src="image/mobil_7.jpg" alt="Mobile Screenshot 7" width="19%"/>
  <img src="image/mobil_8.jpg" alt="Mobile Screenshot 8" width="19%"/>
</p>

<p align="center">
  <img src="image/mobil_9.jpg" alt="Mobile Screenshot 9" width="19%"/>
  <img src="image/mobil_10.jpg" alt="Mobile Screenshot 10" width="19%"/>
  <img src="image/mobil_11.jpg" alt="Mobile Screenshot 11" width="19%"/>
  <img src="image/mobil_12.jpg" alt="Mobile Screenshot 12" width="19%"/>
  <img src="image/mobil_13.jpg" alt="Mobile Screenshot 13" width="19%"/>
</p>

---

## 🤖 Bot API

<div align="center">
  <a href="API_BOT.md">
    <img src="https://img.shields.io/badge/Bot_API-Documentation-green?style=for-the-badge&logo=robot&logoColor=white" alt="Bot API Documentation"/>
  </a>
</div>

Send automated messages into any conversation from your CI/CD, monitoring, or automation tools (n8n, Zapier, Make...). → **[Full documentation](API_BOT.md)**

---

## 🌐 About Axomind

<div align="center">
  <img src="image/logo_axomind.png" alt="Axomind Logo" width="150"/>
</div>

**Axomind** is the **next evolution** of the AuroriaLink project, currently **under active development**. It will be an all-in-one contextual team management ecosystem integrating three interconnected modules:
- **🗓️ Task Scheduling** - Timeline-based project planning
- **🧠 Idea Structuring** - Mindmap-based knowledge organization
- **💬 Communication** - Real-time team messaging

The fundamental principle of Axomind is **contextual linking**: each conversation will be intrinsically linked to tasks, mindmap nodes, or other production elements. AuroriaLink will be integrated as the communication module, enabling this contextual approach to solve the desynchronization between communication and production tools by unifying all aspects of team collaboration into a single workflow.

AuroriaLink is currently released as a **standalone messaging application** while Axomind is being developed.

### Custom Modular Framework

Both AuroriaLink and Axomind are built upon a **custom modular Flutter framework**, designed around these strict principles:
* **Modularity**: Each component (UI, logic, services) is independent
* **Interoperability**: Components interact dynamically without rigid dependencies
* **Adaptability**: Behavior adjusts based on context (user, platform)
* **Separation of Concerns**: Strict partitioning between business logic, UI, data, and configuration

<details>
<summary>👁️ Axomind App Preview (Work in Progress)</summary>

**Light Theme**
<p>
<img src="image/axomind_light.png" alt="Axomind Light 1" width="32%"/>
<img src="image/axomind_light_2.png" alt="Axomind Light 2" width="32%"/>
<img src="image/axomind_light_3.png" alt="Axomind Light 3" width="32%"/>
</p>

**Dark Theme**
<p>
<img src="image/axomind_dark.png" alt="Axomind Dark 1" width="32%"/>
<img src="image/axomind_dark_2.png" alt="Axomind Dark 2" width="32%"/>
<img src="image/axomind_dark_3.png" alt="Axomind Dark 3" width="32%"/>
</p>

</details>

---

## 🤝 Contributing & Feedback

As a beta version, this project thrives on community feedback. If you encounter a bug, have a feature request, or want to contribute, please feel free to open an issue on the repository.

---

## 👤 Author

<div align="center">
  <a href="https://sebastien-vezzani.xyz/" target="_blank"><img src="https://img.shields.io/badge/Portfolio-3423A6?style=for-the-badge&logo=firefox-browser&logoColor=white" alt="Link to Portfolio"/></a>
</div>

---

## 🇫🇷 Version Française

<details>
<summary>Cliquez pour lire en français</summary>

<div align="center">
  <img src="image/auroria_link_256.png" alt="Logo AuroriaLink" width="150"/>
  <h1>AuroriaLink</h1>
  <p><strong>Une messagerie d'équipe privée et chiffrée.</strong></p>
</div>

**AuroriaLink** — messagerie chiffrée et privée pour les équipes. Canaux de groupe, partage de fichiers, zéro tracking.

### ⚠️ Statut du projet : Version Beta

> Ce projet est actuellement en phase de développement actif. Des bugs et des comportements inattendus sont donc probables. Les contributions et retours d'expérience sont les bienvenus.

> **📧 Limitation email :** Les adresses Microsoft (Outlook, Hotmail, Live) sont actuellement bloquées car Microsoft a blacklisté l'IP de mon serveur. Veuillez utiliser Gmail ou un autre fournisseur email pour l'inscription et la 2FA. Pensez également à vérifier vos spams si vous ne recevez pas l'email de vérification.

---

## 🚀 Télécharger la dernière version

<div align="center">
  <table>
    <tr>
      <td align="center" width="33%">
        <a href="INSTALL_ANDROID.md">
          <img src="https://img.shields.io/badge/Android-Installer-2E7D32?style=for-the-badge&logo=android&logoColor=white" alt="Installer pour Android"/>
        </a>
        <br/>
        <sub>APK • <a href="INSTALL_ANDROID.md">Guide d'installation</a></sub>
      </td>
      <td align="center" width="33%">
        <a href="INSTALL_WINDOWS.md">
          <img src="https://img.shields.io/badge/Windows-Installer-3A6DF0?style=for-the-badge&logo=windows11&logoColor=white" alt="Installer pour Windows"/>
        </a>
        <br/>
        <sub>ZIP • <a href="INSTALL_WINDOWS.md">Guide d'installation</a></sub>
      </td>
      <td align="center" width="33%">
        <a href="INSTALL_LINUX.md">
          <img src="https://img.shields.io/badge/Linux-Installer-8A6DF0?style=for-the-badge&logo=linux&logoColor=white" alt="Installer pour Linux"/>
        </a>
        <br/>
        <sub>Debian 13 • <a href="INSTALL_LINUX.md">Guide d'installation</a></sub>
      </td>
    </tr>
  </table>
</div>

<p align="center">
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases">
    <img src="https://img.shields.io/badge/Voir_toutes_les-Versions-gray?style=flat&logo=github" alt="Toutes les versions"/>
  </a>
</p>

---

### ✨ Fonctionnalités Clés

**🔒 Confidentialité & Sécurité**
- 🔒 **Chiffrement Complet** — Messages et fichiers chiffrés sur le serveur et en transit. Vos conversations restent privées.
- 🛡️ **Protection 2FA** — Authentification à deux facteurs par email (code PIN 6 chiffres), avec protection contre le brute force et le tracking IP
- 🔐 **Contrôle d'Accès** — Chaque membre n'accède qu'à ce à quoi il est autorisé, avec des permissions par rôle

**⚡ Temps Réel**
- ⚡ **Livraison Instantanée** — Les messages arrivent en temps réel, avec reconnexion automatique en cas de coupure réseau
- 📱 **Multi-Appareils** — Restez connecté depuis votre bureau et votre mobile en même temps (jusqu'à 2 appareils)

**💬 Messagerie**
- 👥 **Canaux Privés** — Des espaces dédiés pour vos équipes, projets ou sujets
- 🎤 **Messages Audio** — Enregistrez et envoyez des clips vocaux dans vos conversations
- 📎 **Partage de Fichiers** — Jusqu'à 10 fichiers par message (documents, images, vidéos, audio — 10 Mo chacun)
- ⏱️ **Rétention Intelligente** — Messages conservés 6 mois sur le serveur / 1 an en local, avec suppression automatique optionnelle après 24h · Fichiers conservés 1 mois (3 mois si épinglé)

**🧩 Intégrations**
- 🤖 **API Bot** — Connectez vos outils : CI/CD, monitoring, plateformes d'automatisation (n8n, Make, Zapier...)
- 🔗 **Lien Contextuel** — Associez des conversations à vos projets, tâches ou ressources externes

---

<details>
<summary>🛠️ <strong>Stack Technologique</strong> — pour les curieux</summary>

<br/>

<p align="center">
  <a href="https://www.php.net/" target="_blank"><img src="https://img.shields.io/badge/PHP-8.4-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP 8.4"/></a>
  <a href="https://flutter.dev/" target="_blank"><img src="https://img.shields.io/badge/Flutter-Stable-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter"/></a>
  <a href="https://nodejs.org/" target="_blank"><img src="https://img.shields.io/badge/Node.js-LTS-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/></a>
  <a href="https://www.postgresql.org/" target="_blank"><img src="https://img.shields.io/badge/PostgreSQL-Latest-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/></a>
  <a href="https://www.nginx.com/" target="_blank"><img src="https://img.shields.io/badge/Nginx-Stable-269539?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx"/></a>
  <a href="https://www.debian.org/" target="_blank"><img src="https://img.shields.io/badge/Debian-13-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt="Debian 13"/></a>
</p>

**Fonctionnement :**
1. Le **Client** se connecte via HTTPS pour auth/données et WSS pour la messagerie temps réel
2. Le **Serveur WebSocket** gère la communication bidirectionnelle instantanée avec heartbeat (30s) et support multi-device (max 2 connexions)
3. Le **Backend** gère 5 couches de sécurité (validation routes, brute force, 2FA, AES-256-GCM, multi-device), avec cache RAM 4 niveaux pour des performances optimales
4. La **Base de données** stocke les données chiffrées avec politiques de rétention intelligentes et index optimisés pour des requêtes rapides

</details>

---

## 💻 Plateformes supportées

| Plateforme | Statut                         |
|:----------:|:-------------------------------|
| Android    | ✅ Supporté                    |
| Windows    | ✅ Supporté                    |
| Linux      | ✅ Supporté                    |
| macOS      | ❌ Non supporté pour le moment |
| iOS        | ❌ Non supporté pour le moment |

---

## 🚀 Instructions d'Installation

Choisissez votre plateforme pour des instructions détaillées :

- **[Guide d'Installation Android](INSTALL_ANDROID.md)** - Installation APK pour toutes les versions Android
- **[Guide d'Installation Windows](INSTALL_WINDOWS.md)** - Installation ZIP pour Windows 10+
- **[Guide d'Installation Linux](INSTALL_LINUX.md)** - Installation binaire pour Debian 13

---

## 🤖 API Bot

<div align="center">
  <a href="API_BOT.md">
    <img src="https://img.shields.io/badge/API_Bot-Documentation-green?style=for-the-badge&logo=robot&logoColor=white" alt="Documentation API Bot"/>
  </a>
</div>

Envoyez des messages automatisés dans vos conversations depuis vos outils CI/CD, monitoring ou plateformes d'automatisation (n8n, Zapier, Make...). → **[Documentation complète](API_BOT.md)**

---

## 🌐 À propos d'Axomind

<div align="center">
  <img src="image/logo_axomind.png" alt="Logo Axomind" width="150"/>
</div>

**Axomind** est **l'évolution future** du projet AuroriaLink, actuellement **en développement actif**. Ce sera un écosystème de gestion d'équipe contextuel tout-en-un intégrant trois modules interconnectés :
- **🗓️ Planification de tâches** - Gestion de projets basée sur une chronologie
- **🧠 Structuration d'idées** - Organisation des connaissances par mindmap
- **💬 Communication** - Messagerie d'équipe temps réel

Le principe fondamental d'Axomind est le **lien contextuel** : chaque conversation sera intrinsèquement liée aux tâches, nœuds de mindmap, ou autres éléments de production. AuroriaLink sera intégré comme module de communication, permettant cette approche contextuelle pour résoudre la désynchronisation entre les outils de communication et de production en unifiant tous les aspects de la collaboration d'équipe dans un flux de travail unique.

AuroriaLink est actuellement publié comme **application de messagerie autonome** pendant le développement d'Axomind.

### Framework Modulaire Personnalisé

AuroriaLink et Axomind sont construits sur un **framework Flutter modulaire personnalisé**, conçu selon ces principes stricts :
* **Modularité** : Chaque composant (UI, logique, services) est indépendant
* **Interopérabilité** : Les composants interagissent dynamiquement sans dépendances rigides
* **Adaptabilité** : Le comportement s'ajuste en fonction du contexte (utilisateur, plateforme)
* **Séparation des responsabilités** : Cloisonnement strict entre logique métier, UI, données et configuration

<details>
<summary>👁️ Aperçu d'Axomind (En cours de développement)</summary>

**Thème Clair**
<p>
<img src="image/axomind_light.png" alt="Axomind Clair 1" width="32%"/>
<img src="image/axomind_light_2.png" alt="Axomind Clair 2" width="32%"/>
<img src="image/axomind_light_3.png" alt="Axomind Clair 3" width="32%"/>
</p>

**Thème Sombre**
<p>
<img src="image/axomind_dark.png" alt="Axomind Sombre 1" width="32%"/>
<img src="image/axomind_dark_2.png" alt="Axomind Sombre 2" width="32%"/>
<img src="image/axomind_dark_3.png" alt="Axomind Sombre 3" width="32%"/>
</p>

</details>

</details>

---

