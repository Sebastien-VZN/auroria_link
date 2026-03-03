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

## 🎥 Preview

<details>
<summary align="center"><strong>🔴 Click here to watch the demo video (Real-time Messaging)</strong></summary>

<div align="center">
  <br>
  
  <a href="https://github.com/Sebastien-VZN/auroria_link/raw/main/image/output_auroria.mp4">
    <img src="image/desktop_1.jpg" alt="Watch the demo video" width="300">
  </a>

  <p><sub><em>See AuroriaLink's real-time capabilities in action</em></sub></p>
</div>

</details>

## 📋 Table of Contents

- [⚠️ Project Status](#️-project-status-beta-version)
- [✨ Key Features](#-key-features)
- [🛠️ Tech Stack](#️-tech-stack)
- [💻 Supported Platforms](#-supported-platforms)
- [🚀 Installation](#-installation)
- [🤖 Bot API](#-bot-api)
- [🌐 About Axomind](#-about-axomind)
- [🎨 Gallery](#-gallery)
- [🤝 Contributing & Feedback](#-contributing--feedback)
- [👤 Author](#-author)
- [🇫🇷 Version Française](#-version-française)

---

### ⚠️ Project Status: Beta Version

> This project is currently in active development. Bugs and unexpected behaviors are therefore likely. All feedback is welcome.

> **📧 Email limitation:** Microsoft email addresses (Outlook, Hotmail, Live) are currently blocked due to Microsoft blacklisting my server IP. Please use Gmail or other email providers for registration and 2FA. Also check your spam folder if you don't receive the verification email.

---

### ✨ Key Features

-   **⚡ Real-Time Communication**: Architecture based on a **WebSocket (Node.js)** server for instant, full-duplex exchanges with heartbeat monitoring (30s) and automatic reconnection.
-   **🔒 Absolute Privacy & Encryption**: The messaging is **100% private**. All messages and files are **encrypted at rest on the server** with **AES-256-GCM** (streaming chunks 8MB). Communications transit via **HTTPS** and **WSS (WebSocket Secure)**, ensuring end-to-end maximum security.
-   **🚀 High-Performance Backend**: 4-level RAM cache architecture (OPcache → APCu → Ramdisk → Redis) delivering **-80% CPU decrypt load**, **+150% throughput**, and **×2 bandwidth**. Persistent database connections and 11 critical indexes ensure ultra-fast queries.
-   **⏱️ Optimized Message Retention**: Messages are retained for 6 months on the server and 1 year on the client (integrated local database), with an option for automatic deletion after 24 hours for maximum confidentiality. Daily cleanup at midnight to limit server load and optimize storage costs.
-   **📱 Multi-Device Support**: Switch seamlessly between your devices (desktop or mobile) with automatic session management. **Maximum 2 simultaneous connections** per user for optimal security and resource management.
-   **🔄 Smart Reconnection**: Automatic reconnection with exponential backoff in case of network loss, with 2FA validation when necessary to ensure your session security.
-   **🛡️ 5-Layer Security**: Route validation, brute force protection with IP tracking, 2FA via email (PIN 6-digit), AES-256-GCM encryption, and intelligent multi-device management.
-   **👥 Private Discussion Channels**: Create partitioned channels for specific teams, projects, or topics, accessible only to authorized members.
-   **🎤 Sequential Audio Messaging**: Record and send encrypted audio clips to create a fluid vocal conversation thread.
-   **📎 Comprehensive File Sharing**: Share encrypted documents, images, videos, and audio files (up to 10 files per message, 10 MB per file) directly within your contextual conversations.
-   **📌 Smart File Management**: Files are retained for 1 month on the server. Pinning a file resets its retention to 3 months from the pin date — each user who pins it extends its lifespan, allowing important files to remain accessible for less frequent users.
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

---

## 🚀 Installation

Choose your platform for detailed installation instructions:

- **[Android Installation Guide](INSTALL_ANDROID.md)** - APK installation for all Android versions
- **[Windows Installation Guide](INSTALL_WINDOWS.md)** - ZIP installation for Windows 10+
- **[Linux Installation Guide](INSTALL_LINUX.md)** - Binary installation for Debian 13

---

## 🤖 Bot API

<div align="center">
  <table>
    <tr>
      <td align="center">
        <a href="API_BOT.md">
          <img src="https://img.shields.io/badge/Bot_API-Documentation-green?style=for-the-badge&logo=robot&logoColor=white" alt="Bot API Documentation"/>
        </a>
        <br/>
        <sub>Integrate automated messaging into your workflows</sub>
      </td>
    </tr>
  </table>
</div>

The **Bot API** allows third-party applications to send automated messages to AuroriaLink conversations. Perfect for:

- **CI/CD pipelines** - Build status notifications
- **Monitoring systems** - Real-time alerts
- **Workflow automation** - n8n, Zapier, Make integrations
- **Custom applications** - Your own integrations

<details>
<summary>⚡ <strong>n8n Integration Example</strong> - Connect 400+ apps to your team chat</summary>

<br/>

Use an **HTTP Request** node in n8n to send messages:

| Setting | Value |
|---------|-------|
| **Method** | `POST` |
| **URL** | `https://quantive-studio.xyz/app/bot_api.php?route=api_messenger` |
| **Body Type** | `Form URL Encoded` |
| **Parameters** | `key_access`: Your bot token |
| | `id_bot`: Your bot ID |
| | `type_action`: `add_message` |
| | `content_message`: `{{$json["message"]}}` |

**Use cases:**
- GitHub webhook → New PR notification to team
- Stripe webhook → Payment alerts
- Monitoring → Server down alerts
- CRM → New lead notifications
- Calendar → Meeting reminders

</details>

**Quick Example (cURL):**
```bash
curl -X POST "https://quantive-studio.xyz/app/bot_api.php?route=api_messenger" \
  -d "key_access=YOUR_BOT_TOKEN" \
  -d "id_bot=YOUR_BOT_ID" \
  -d "type_action=add_message" \
  -d "content_message=Hello from my bot!"
```

See the **[complete Bot API documentation](API_BOT.md)** for setup instructions, code examples (Python, Node.js, PHP), and API reference.

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
  <p><strong>Une messagerie d'équipe temps réel.</strong></p>
</div>

**AuroriaLink** est une plateforme de messagerie d'équipe temps réel construite avec Flutter, conçue pour une collaboration fluide via des groupes de discussion et le partage sécurisé de fichiers.

Conçue avec une philosophie d'**optimisation intelligente**, AuroriaLink minimise les coûts serveur grâce à une gestion intelligente des ressources, tout en maintenant performance et sécurité.

### ⚠️ Statut du projet : Version Beta

> Ce projet est actuellement en phase de développement actif. Des bugs et des comportements inattendus sont donc probables. Les contributions et retours d'expérience sont les bienvenus.

> **📧 Limitation email :** Les adresses Microsoft (Outlook, Hotmail, Live) sont actuellement bloquées car Microsoft a blacklisté l'IP de mon serveur. Veuillez utiliser Gmail ou un autre fournisseur email pour l'inscription et la 2FA. Pensez également à vérifier vos spams si vous ne recevez pas l'email de vérification.

---

## 🚀 Télécharger la dernière version

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
-   **⏱️ Rétention des Messages Optimisée** : Les messages sont conservés 6 mois sur le serveur et 1 an sur le client (base de données locale intégrée), avec option de suppression automatique après 24h pour une confidentialité maximale. Nettoyage quotidien à minuit pour limiter la charge serveur et optimiser les coûts de stockage.
-   **📱 Support Multi-Device** : Basculez facilement entre vos appareils (desktop ou mobile) avec gestion automatique des sessions. **Maximum 2 connexions simultanées** par utilisateur pour une sécurité et gestion des ressources optimales.
-   **🔄 Reconnexion Intelligente** : Reconnexion automatique avec backoff exponentiel en cas de perte de réseau, avec validation 2FA si nécessaire pour garantir la sécurité de votre session.
-   **🛡️ Sécurité 5 Couches** : Validation des routes, protection brute force avec tracking IP, 2FA par email (PIN 6 chiffres), chiffrement AES-256-GCM, et gestion intelligente multi-device.
-   **👥 Canaux de Discussion Privés** : Créez des canaux cloisonnés pour des équipes, projets ou sujets spécifiques, accessibles uniquement aux membres autorisés.
-   **🎤 Messagerie Audio Séquentielle** : Enregistrez et envoyez des clips audio chiffrés pour créer un fil de conversation vocal fluide.
-   **📎 Partage de Fichiers Complet** : Partagez documents, images, vidéos et fichiers audio chiffrés (jusqu'à 10 fichiers par message, 10 Mo par fichier), directement dans vos conversations contextuelles.
-   **📌 Gestion Intelligente des Fichiers** : Les fichiers sont conservés 1 mois sur le serveur. Épingler un fichier remet son compteur à 3 mois depuis la date d'épinglage — chaque utilisateur qui l'épingle prolonge sa durée de vie, permettant aux utilisateurs peu fréquents de garder leurs fichiers importants accessibles.
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

L'**API Bot** permet aux applications tierces d'envoyer des messages automatisés dans les conversations AuroriaLink. Idéal pour :

- **Pipelines CI/CD** - Notifications de statut de build
- **Systèmes de monitoring** - Alertes en temps réel
- **Automatisation de workflows** - Intégrations n8n, Zapier, Make
- **Applications personnalisées** - Vos propres intégrations

<details>
<summary>⚡ <strong>Exemple d'intégration n8n</strong> - Connectez 400+ apps à votre chat d'équipe</summary>

<br/>

Utilisez un nœud **HTTP Request** dans n8n :

| Paramètre | Valeur |
|-----------|--------|
| **Méthode** | `POST` |
| **URL** | `https://quantive-studio.xyz/app/bot_api.php?route=api_messenger` |
| **Type Body** | `Form URL Encoded` |
| **Paramètres** | `key_access`: Votre token bot |
| | `id_bot`: Votre ID bot |
| | `type_action`: `add_message` |
| | `content_message`: `{{$json["message"]}}` |

**Cas d'usage :**
- Webhook GitHub → Notification nouvelle PR à l'équipe
- Webhook Stripe → Alertes de paiement
- Monitoring → Alertes serveur down
- CRM → Notifications nouveaux leads
- Calendrier → Rappels de réunions

</details>

**Exemple rapide (cURL) :**
```bash
curl -X POST "https://quantive-studio.xyz/app/bot_api.php?route=api_messenger" \
  -d "key_access=VOTRE_TOKEN_BOT" \
  -d "id_bot=VOTRE_ID_BOT" \
  -d "type_action=add_message" \
  -d "content_message=Bonjour depuis mon bot !"
```

Consultez la **[documentation complète de l'API Bot](API_BOT.md)** pour les instructions de configuration, exemples de code (Python, Node.js, PHP) et référence API.

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

## 🎨 Gallery

<div align="center">
  <h3>✨ Discover AuroriaLink in action</h3>
  <p>Explore the real-time team messaging platform through these screenshots showcasing both mobile and desktop experiences.</p>
</div>


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

<div align="center">
  <p><em>Join us in building the future of contextual team collaboration! 🚀</em></p>
</div>
