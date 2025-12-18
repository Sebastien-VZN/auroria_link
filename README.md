<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Logo" width="150"/>
  <h1>AuroriaLink</h1>
  <p><strong>A real-time team messaging solution.</strong></p>
  
  <p>
    <img src="https://img.shields.io/badge/status-alpha-orange?style=for-the-badge" alt="Project Status: Alpha"/>
    <img src="https://img.shields.io/badge/license-Proprietary-red?style=for-the-badge" alt="License: Proprietary"/>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Version-0.5.2%20(14)-blueviolet?style=flat-square&logo=github" alt="Version"/>
    <img src="https://img.shields.io/badge/Release%20Date-2025--12--18-blue?style=flat-square&logo=calendar" alt="Release Date"/>
  </p>
</div>



**AuroriaLink** is a real-time team messaging platform built with Flutter, designed for seamless collaboration through group discussions and secure file sharing.

Built with a core philosophy of **intelligent optimization**, AuroriaLink minimizes server costs through smart resource management while maintaining performance and security.
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

## 📋 Table of Contents

- [⚠️ Project Status](#️-project-status-alpha-version)
- [✨ Key Features](#-key-features)
- [🛠️ Tech Stack](#️-tech-stack)
- [💻 Supported Platforms](#-supported-platforms)
- [🚀 Installation](#-installation)
- [🎨 Gallery](#-gallery)
- [🌱 Origins: Axomind & Custom Framework](#-origins-axomind--custom-framework)
- [🤝 Contributing & Feedback](#-contributing--feedback)
- [👤 Author](#-author)
- [🇫🇷 Version Française](#-version-française)

---

### ⚠️ Project Status: Alpha Version

> This project is currently in active development. Bugs and unexpected behaviors are therefore likely. All feedback is welcome.

---

### ✨ Key Features

-   **⚡ Real-Time Communication**: Architecture based on a **WebSocket (Node.js)** server for instant, full-duplex exchanges with heartbeat monitoring (30s) and automatic reconnection.
-   **🔒 Absolute Privacy & Encryption**: The messaging is **100% private**. All messages and files are **encrypted at rest on the server** with **AES-256-GCM** (streaming chunks 8MB). Communications transit via **HTTPS** and **WSS (WebSocket Secure)**, ensuring end-to-end maximum security.
-   **🚀 High-Performance Backend**: 4-level RAM cache architecture (OPcache → APCu → Ramdisk → Redis) delivering **-80% CPU decrypt load**, **+150% throughput**, and **×2 bandwidth**. Persistent database connections and 11 critical indexes ensure ultra-fast queries.
-   **⏱️ Optimized Message Retention**: Messages are retained for 15 days on the server and 1 year on the client (integrated database), with an option for automatic deletion after 24 hours for maximum confidentiality. Daily cleanup at midnight to limit server load and optimize storage costs.
-   **📱 Multi-Device Support**: Switch seamlessly between your devices (desktop or mobile) with automatic session management. **Maximum 2 simultaneous connections** per user for optimal security and resource management.
-   **🔄 Smart Reconnection**: Automatic reconnection with exponential backoff in case of network loss, with 2FA validation when necessary to ensure your session security.
-   **🛡️ 5-Layer Security**: Route validation, brute force protection with IP tracking, 2FA via email (PIN 6-digit), AES-256-GCM encryption, and intelligent multi-device management.
-   **👥 Private Discussion Channels**: Create partitioned channels for specific teams, projects, or topics, accessible only to authorized members.
-   **🎤 Sequential Audio Messaging**: Record and send encrypted audio clips to create a fluid vocal conversation thread.
-   **📎 Comprehensive File Sharing**: Share encrypted documents, images, videos, and audio files (up to 10 files per message, 10 MB per file) directly within your contextual conversations.
-   **📌 Smart File Management**: Files are retained for 15 days on the server, or 3 months if pinned. Each pin resets the 3-month timer, allowing only important files to be retained and optimizing server storage.
-   **🧩 Modularity & Integration**: Designed as a standalone module that can be integrated as a service via its API.
-   **💪 Robust Backend**: A **PHP 8.4 / PostgreSQL 17** backend with **PHP-FPM (80 workers)** ensures data persistence, user management, and permissions with enterprise-grade reliability.
-   **🔗 Contextual API**: Securely create and link conversations to external object identifiers.
-   **🔐 Access Control**: Role-based rights management for precise and context-aware access to conversations.

---

## 🛠️ Tech Stack

<p align="center">
  <a href="https://www.php.net/" target="_blank"><img src="https://img.shields.io/badge/PHP-8.4-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP 8.4"/></a>
  <a href="https://flutter.dev/" target="_blank"><img src="https://img.shields.io/badge/Flutter-Stable-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter"/></a>
  <a href="https://nodejs.org/" target="_blank"><img src="https://img.shields.io/badge/Node.js-LTS-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/></a>
  <a href="https://www.postgresql.org/" target="_blank"><img src="https://img.shields.io/badge/PostgreSQL-Latest-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/></a>
  <a href="https://www.nginx.com/" target="_blank"><img src="https://img.shields.io/badge/Nginx-Stable-269539?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx"/></a>
  <a href="https://www.debian.org/" target="_blank"><img src="https://img.shields.io/badge/Debian-13-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt="Debian 13"/></a>
</p>


```
╔═════════════════════════════════════════════════════════════╗
║                    Client Applications                      ║
║           Flutter (Android, Windows, Linux)                 ║
║                                                             ║
║  • Contextual messaging                                     ║
║  • Encrypted file sharing (AES-256-GCM)                     ║
║  • Audio messaging                                          ║
║  • Auto-reconnection (exponential backoff)                  ║
╚════════════╦═════════════════════════╦══════════════════════╝
             ║ HTTP/HTTPS              ║ WSS (WebSocket Secure)
             ║ (auth/data)             ║ (real-time messaging)
             ↓                         ↓
╔═════════════════════════╗   ╔════════════════════════════════╗
║   Backend Server        ║   ║   Real-Time WebSocket Server   ║
║   PHP 8.4 + Nginx       ║   ║   Node.js (quantive-ws)        ║
║   PHP-FPM (80 workers)  ║   ║                                ║
║                         ║   ║  • Port 8080 (clients)         ║
║  Security Layers:       ║   ║  • Port 8081 (internal API)    ║
║  1. Route validation    ║   ║  • Heartbeat 30s (ping/pong)   ║
║  2. Brute force ctrl    ║   ║  • Multi-device (max 2)        ║
║  3. 2FA (email PIN)     ║   ║  • Auth via PHP validation     ║
║  4. AES-256-GCM         ║←──║  • Session management          ║
║  5. Multi-device mgmt   ║   ╚════════════════════════════════╝
║                         ║
║  4-Level Cache:         ║
║  • OPcache (bytecode)   ║
║  • APCu (UUID→path)     ║
║  • Ramdisk (4GB)        ║
║  • Redis (2GB LRU)      ║
╚════════╦════════════════╝
         ║ Persistent PDO
         ║ 11 critical indexes
         ↓
╔═══════════════════════════════════════════════════════════════╗
║                 PostgreSQL 17 Database                        ║
║                                                               ║
║  • Encrypted messages (AES-256-GCM)                           ║
║  • Retention: 15 days server / 1 year client (integrated DB)  ║
║  • Smart file retention (pinning resets 3-month timer)        ║
║  • User management, permissions & roles                       ║
║  • Indexed: users (auth), security (IP), messages (JSONB)     ║
╚═══════════════════════════════════════════════════════════════╝
```

**How it works:**
1. **Client** connects via HTTPS for auth/data and WSS for real-time messaging
2. **WebSocket Server** handles instant bidirectional communication with heartbeat (30s) and multi-device support (max 2 connections)
3. **Backend** manages 5 security layers (route validation, brute force, 2FA, AES-256-GCM, multi-device), with 4-level RAM cache for optimal performance
4. **Database** stores encrypted data with intelligent retention policies and optimized indexes for fast queries

---

## 💻 Supported Platforms

| Platform | Status                 |
|:--------:|:-----------------------|
| Android  | ✅ Supported           |
| Windows  | ✅ Supported           |
| Linux    | ✅ Supported           |
| macOS    | ❌ Not yet supported   |
| iOS      | ❌ Not yet supported   |
| Web      | ❌ Not supported       |

---

## 🚀 Installation

Choose your platform for detailed installation instructions:

- **[Android Installation Guide](INSTALL_ANDROID.md)** - APK installation for all Android versions
- **[Windows Installation Guide](INSTALL_WINDOWS.md)** - ZIP installation for Windows 10+
- **[Linux Installation Guide](INSTALL_LINUX.md)** - Binary installation for Debian 13

---

## 🌐 About Axomind

<div align="center">
  <img src="image/logo_axomind.png" alt="Axomind Logo" width="150"/>
  <p><sub><em>Axomind ecosystem logos are available in the <code>image/</code> directory</em></sub></p>
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

As an alpha version, this project thrives on community feedback. If you encounter a bug, have a feature request, or want to contribute, please feel free to open an issue on the repository.

---

## 👤 Author

<div align="center">
  <a href="https://materiaeobscurataelab.xyz/" target="_blank"><img src="https://img.shields.io/badge/Portfolio-3423A6?style=for-the-badge&logo=firefox-browser&logoColor=white" alt="Link to Portfolio"/></a>
</div>

---

## 🇫🇷 Version Française

<details>
<summary>Cliquez pour lire en français</summary>

<div align="center">
  <img src="image/auroria_link_256.png" alt="Logo AuroriaLink" width="150"/>
  <h1>AuroriaLink</h1>
  <p><strong>Une messagerie d'équipe temps réel.</strong></p>
</div>

**AuroriaLink** est une plateforme de messagerie d'équipe temps réel construite avec Flutter, conçue pour une collaboration fluide via des groupes de discussion et le partage sécurisé de fichiers.

Conçue avec une philosophie d'**optimisation intelligente**, AuroriaLink minimise les coûts serveur grâce à une gestion intelligente des ressources, tout en maintenant performance et sécurité.

### ⚠️ Statut du projet : Version Alpha

> Ce projet est actuellement en phase de développement actif. Des bugs et des comportements inattendus sont donc probables. Les contributions et retours d'expérience sont les bienvenus.

---

## 🚀 Télécharger la dernière version

<p align="center">
  <img src="https://img.shields.io/badge/Version-0.5.1%20(13)-blueviolet?style=flat-square&logo=github" alt="Version"/>
  <img src="https://img.shields.io/badge/Date%20de%20sortie-2025--12--12-blue?style=flat-square&logo=calendar" alt="Date de sortie"/>
</p>

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
          <img src="https://img.shields.io/badge/Windows-Installer-3A6DF0?style=for-the-badge&logo=microsoftwindows&logoColor=white" alt="Installer pour Windows"/>
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

-   **⚡ Communication Temps Réel** : Architecture basée sur un serveur **WebSocket (Node.js)** pour des échanges full-duplex instantanés avec monitoring heartbeat (30s) et reconnexion automatique.
-   **🔒 Confidentialité & Chiffrement Absolu** : La messagerie est **100% privée**. Tous les messages et fichiers sont **chiffrés au repos sur le serveur** avec **AES-256-GCM** (streaming chunks 8MB). Les communications transitent via **HTTPS** et **WSS (WebSocket Secure)**, garantissant une sécurité maximale de bout en bout.
-   **🚀 Backend Haute Performance** : Architecture cache RAM 4 niveaux (OPcache → APCu → Ramdisk → Redis) offrant **-80% charge CPU déchiffrement**, **+150% throughput**, et **×2 bande passante**. Connexions base de données persistantes et 11 index critiques assurent des requêtes ultra-rapides.
-   **⏱️ Rétention des Messages Optimisée** : Les messages sont conservés 15 jours sur le serveur et 1 an sur le client (base de données intégrée), avec option de suppression automatique après 24h pour une confidentialité maximale. Nettoyage quotidien à minuit pour limiter la charge serveur et optimiser les coûts de stockage.
-   **📱 Support Multi-Device** : Basculez facilement entre vos appareils (desktop ou mobile) avec gestion automatique des sessions. **Maximum 2 connexions simultanées** par utilisateur pour une sécurité et gestion des ressources optimales.
-   **🔄 Reconnexion Intelligente** : Reconnexion automatique avec backoff exponentiel en cas de perte de réseau, avec validation 2FA si nécessaire pour garantir la sécurité de votre session.
-   **🛡️ Sécurité 5 Couches** : Validation des routes, protection brute force avec tracking IP, 2FA par email (PIN 6 chiffres), chiffrement AES-256-GCM, et gestion intelligente multi-device.
-   **👥 Canaux de Discussion Privés** : Créez des canaux cloisonnés pour des équipes, projets ou sujets spécifiques, accessibles uniquement aux membres autorisés.
-   **🎤 Messagerie Audio Séquentielle** : Enregistrez et envoyez des clips audio chiffrés pour créer un fil de conversation vocal fluide.
-   **📎 Partage de Fichiers Complet** : Partagez documents, images, vidéos et fichiers audio chiffrés (jusqu'à 10 fichiers par message, 10 Mo par fichier), directement dans vos conversations contextuelles.
-   **📌 Gestion Intelligente des Fichiers** : Les fichiers sont conservés 15 jours sur le serveur, ou 3 mois s'ils sont épinglés. Chaque épinglage réinitialise le compteur à 3 mois, permettant de conserver uniquement les fichiers importants et d'optimiser le stockage serveur.
-   **🧩 Modularité & Intégration** : Conçu comme un module autonome pouvant être intégré comme service via son API.
-   **💪 Backend Robuste** : Un backend en **PHP 8.4 / PostgreSQL 17** avec **PHP-FPM** assure la persistance des données, la gestion des utilisateurs et des droits avec une fiabilité de niveau entreprise.
-   **🔗 API Contextuelle** : Créez et liez dynamiquement des conversations à des identifiants d'objets externes de manière sécurisée.
-   **🔐 Contrôle d'Accès** : Gestion des droits basée sur les rôles pour un accès précis et contextuel aux conversations.

---

## 🛠️ Stack Technologique

<p align="center">
  <a href="https://www.php.net/" target="_blank"><img src="https://img.shields.io/badge/PHP-8.4-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP 8.4"/></a>
  <a href="https://flutter.dev/" target="_blank"><img src="https://img.shields.io/badge/Flutter-Stable-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter"/></a>
  <a href="https://nodejs.org/" target="_blank"><img src="https://img.shields.io/badge/Node.js-LTS-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/></a>
  <a href="https://www.postgresql.org/" target="_blank"><img src="https://img.shields.io/badge/PostgreSQL-Latest-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/></a>
  <a href="https://www.nginx.com/" target="_blank"><img src="https://img.shields.io/badge/Nginx-Stable-269539?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx"/></a>
  <a href="https://www.debian.org/" target="_blank"><img src="https://img.shields.io/badge/Debian-13-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt="Debian 13"/></a>
</p>

```
╔═════════════════════════════════════════════════════════════╗
║                  Applications Clientes                      ║
║           Flutter (Android, Windows, Linux)                 ║
║                                                             ║
║  • Messagerie contextuelle                                  ║
║  • Partage de fichiers chiffrés (AES-256-GCM)               ║
║  • Messagerie audio                                         ║
║  • Auto-reconnexion (backoff exponentiel)                   ║
╚════════════╦═════════════════════════╦══════════════════════╝
             ║ HTTP/HTTPS              ║ WSS (WebSocket Secure)
             ║ (auth/data)             ║ (messagerie temps réel)
             ↓                         ↓
╔═════════════════════════╗   ╔════════════════════════════════╗
║   Serveur Backend       ║   ║   Serveur WebSocket Temps Réel ║
║   PHP 8.4 + Nginx       ║   ║   Node.js (quantive-ws)        ║
║   PHP-FPM (80 workers)  ║   ║                                ║
║                         ║   ║  • Port 8080 (clients)         ║
║  Couches de sécurité :  ║   ║  • Port 8081 (API interne)     ║
║  1. Validation routes   ║   ║  • Heartbeat 30s (ping/pong)   ║
║  2. Contrôle brute force║   ║  • Multi-device (max 2)        ║
║  3. 2FA (PIN email)     ║   ║  • Auth via validation PHP     ║
║  4. AES-256-GCM         ║←──║  • Gestion des sessions        ║
║  5. Gestion multi-device║   ╚════════════════════════════════╝
║                         ║
║  Cache 4 niveaux :      ║
║  • OPcache (bytecode)   ║
║  • APCu (UUID→path)     ║
║  • Ramdisk (4GB)        ║
║  • Redis (2GB LRU)      ║
╚════════╦════════════════╝
         ║ PDO persistant
         ║ 11 index critiques
         ↓
╔═══════════════════════════════════════════════════════════════╗
║               Base de données PostgreSQL 17                   ║
║                                                               ║
║  • Messages chiffrés (AES-256-GCM)                            ║
║  • Rétention : 15 jours serveur / 1 an client (DB intégrée)  ║
║  • Rétention intelligente (épinglage réinitialise 3 mois)     ║
║  • Gestion utilisateurs, permissions & rôles                  ║
║  • Indexé : users (auth), security (IP), messages (JSONB)     ║
╚═══════════════════════════════════════════════════════════════╝
```

**Fonctionnement :**
1. Le **Client** se connecte via HTTPS pour auth/données et WSS pour la messagerie temps réel
2. Le **Serveur WebSocket** gère la communication bidirectionnelle instantanée avec heartbeat (30s) et support multi-device (max 2 connexions)
3. Le **Backend** gère 5 couches de sécurité (validation routes, brute force, 2FA, AES-256-GCM, multi-device), avec cache RAM 4 niveaux pour des performances optimales
4. La **Base de données** stocke les données chiffrées avec politiques de rétention intelligentes et index optimisés pour des requêtes rapides

---

## 💻 Plateformes supportées

| Plateforme | Statut                         |
|:----------:|:-------------------------------|
| Android    | ✅ Supporté                    |
| Windows    | ✅ Supporté                    |
| Linux      | ✅ Supporté                    |
| macOS      | ❌ Non supporté pour le moment |
| iOS        | ❌ Non supporté pour le moment |
| Web        | ❌ Non supporté                |

---

## 🚀 Instructions d'Installation

Choisissez votre plateforme pour des instructions détaillées :

- **[Guide d'Installation Android](INSTALL_ANDROID.md)** - Installation APK pour toutes les versions Android
- **[Guide d'Installation Windows](INSTALL_WINDOWS.md)** - Installation ZIP pour Windows 10+
- **[Guide d'Installation Linux](INSTALL_LINUX.md)** - Installation binaire pour Debian 13

---

## 🌐 À propos d'Axomind

<div align="center">
  <img src="image/logo_axomind.png" alt="Logo Axomind" width="150"/>
  <p><sub><em>Les logos de l'écosystème Axomind sont disponibles dans le répertoire <code>image/</code></em></sub></p>
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

## 🎨 Gallery

<div align="center">
  <h3>✨ Discover AuroriaLink in action</h3>
  <p>Explore the real-time team messaging platform through these screenshots showcasing both mobile and desktop experiences with light and dark themes.</p>
</div>

### 📱 Mobile - Dark Theme

<p align="center">
  <img src="image/screenshot_01.png" alt="Mobile Dark - Conversation" width="19%"/>
  <img src="image/screenshot_02.png" alt="Mobile Dark - File Sharing" width="19%"/>
  <img src="image/screenshot_03.jpg" alt="Mobile Dark - Theme Selection" width="19%"/>
  <img src="image/screenshot_04.png" alt="Mobile Dark - Settings" width="19%"/>
  <img src="image/screenshot_05.png" alt="Mobile Dark - Media Gallery" width="19%"/>
</p>

<p align="center">
  <img src="image/screenshot_09.png" alt="Mobile Dark - Files View" width="19%"/>
  <img src="image/screenshot_11.png" alt="Mobile Dark - Conversation Files" width="19%"/>
  <img src="image/screenshot_12.png" alt="Mobile Dark - Gallery View" width="19%"/>
  <img src="image/screenshot_13.png" alt="Mobile Dark - Images Thread" width="19%"/>
  <img src="image/screenshot_15.png" alt="Mobile Dark - Login Screen" width="19%"/>
</p>

### 📱 Mobile - Light Theme

<p align="center">
  <img src="image/screenshot_17.png" alt="Mobile Light - Settings" width="19%"/>
  <img src="image/screenshot_18.png" alt="Mobile Light - Settings Neutral" width="19%"/>
  <img src="image/screenshot_19.png" alt="Mobile Light - Settings Sepia" width="19%"/>
  <img src="image/screenshot_20.png" alt="Mobile Light - Settings Aurora" width="19%"/>
  <img src="image/screenshot_21.png" alt="Mobile Light - Settings Lavender" width="19%"/>
</p>

<p align="center">
  <img src="image/screenshot_22.png" alt="Mobile Light - Settings Slate" width="19%"/>
  <img src="image/screenshot_23.png" alt="Mobile Light - Gallery View" width="19%"/>
  <img src="image/screenshot_24.png" alt="Mobile Light - Conversation" width="19%"/>
</p>

### 💻 Desktop - Dark Theme

<p align="center">
  <img src="image/screenshot_06.png" alt="Desktop Dark - Conversation List" width="49%"/>
  <img src="image/screenshot_07.png" alt="Desktop Dark - Media Gallery" width="49%"/>
</p>

<p align="center">
  <img src="image/screenshot_08.png" alt="Desktop Dark - Orange Theme" width="49%"/>
  <img src="image/screenshot_10.png" alt="Desktop Dark - Images Thread" width="49%"/>
</p>

<p align="center">
  <img src="image/screenshot_14.png" alt="Desktop Dark - Login Screen" width="49%"/>
</p>

### 💻 Desktop - Light Theme

<p align="center">
  <img src="image/screenshot_16.png" alt="Desktop Light - Gallery View" width="49%"/>
  <img src="image/screenshot_25.png" alt="Desktop Light - Conversation" width="49%"/>
</p>

<p align="center">
  <img src="image/screenshot_26.png" alt="Desktop Light - Files Manager" width="49%"/>
</p>

---

<div align="center">
  <p><em>Join us in building the future of contextual team collaboration! 🚀</em></p>
</div>
