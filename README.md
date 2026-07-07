<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Logo" width="150"/>
  <h1>AuroriaLink</h1>
  <p><strong>A real-time team messaging solution.</strong></p>
  
  <p>
    <img src="https://img.shields.io/badge/status-beta-blue?style=for-the-badge" alt="Project Status: Beta"/>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Version-0.11.0%20(39)-blueviolet?style=flat-square&logo=github" alt="Version"/>
    <img src="https://img.shields.io/badge/Release%20Date-2026--07--07-blue?style=flat-square&logo=calendar" alt="Release Date"/>
  </p>

  <p align="center">
    <a href="#-version-française"><img src="https://img.shields.io/badge/🇫🇷-Lire_en_français-blue?style=flat-square" alt="Lire en français"/></a>
  </p>
</div>

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
- [🎨 Gallery](#-gallery)
- [📊 Performance & Real Cost](#-performance--real-cost)
- [🤖 Bot API](#-bot-api)
- [🌐 About Axomind](#-about-axomind)
- [🤝 Bug Reports & Feedback](#-bug-reports--feedback)
- [👤 Author](#-author)
- [🇫🇷 Version Française](#-version-française)

---

## ⚠️ Project Status: Beta Version

> This project is in active development. Bugs and unexpected behaviors are likely. Feedback is welcome.

> **📧 About emails**
> Outbound mail from the self-hosted server is blocked at the ISP level, and alternative relays haven't given reliable delivery for this setup. So **everything that would normally rely on email is switched off for now** — account verification, password reset, and two-factor authentication. Accounts work without any email step.
> The email layer is built in and decoupled from the regular login flow. It will be turned back on once the platform moves to a hosting provider with reliable outbound mail — nothing else will change for you.

---

## ✨ Key Features

**🔒 Privacy & Security**
- 🔒 **Strong Encryption** — Messages and files are encrypted with AES-256-GCM, both when stored on the server and while being sent. Your conversations stay private.
- 🛡️ **Two-factor authentication** — Email-code 2FA at login with anti-spam and bad-attempt detection (currently off — see the email notice above).
- 🔐 **Access Control** — Each member only sees what they're allowed to, with role-based permissions

**⚡ Real-Time**
- ⚡ **Instant Delivery** — Messages arrive instantly, with automatic reconnection if the link drops
- 📱 **Multi-Device** — Stay signed in on **up to 2 devices for AuroriaLink** (1 desktop + 1 mobile). If you also use Axomind, you get **2 more sessions in parallel** — up to 4 active sessions in total per account, by design

**🎨 Interface**
- 🎨 **26 Themes** — Each with a light and a dark variant, switchable on the fly, with Aurora animations and glassmorphism (same theme set as Axomind)

**💬 Messaging**
- 👥 **Private Channels** — Dedicated spaces for your teams, projects, or topics
- 🎤 **Audio Messages** — Record and send voice clips in your conversations
- 📎 **File Sharing** — Up to 10 files per message (documents, images, videos, audio — 10 MB each)
- ⏱️ **Retention** — Messages kept 1 year on the server / 2 years locally, with optional 24h auto-delete · Files kept 1 month (3 months if pinned)

**🧩 Integrations**
- 🤖 **Bot API** — Send messages from CI/CD, monitoring, or automation tools (n8n, Make, Zapier...)
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

**How it works (in plain words):**
1. **The app** talks to the server over a secure connection (HTTPS), and a separate live channel keeps everything in sync in real time
2. **The live channel** can keep 2 sessions open at once for AuroriaLink (1 desktop + 1 mobile). The same design supports 2 extra sessions for Axomind in parallel — 4 active sessions total per account
3. **The server** protects accounts on several layers: route checks, attack protection, AES-256-GCM encryption, and a unique token per session
4. **The database** stores everything encrypted, keeps data only as long as needed, and is tuned for fast reads on conversations and messages

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

## 📊 Performance & Real Cost

Hardware specs, load test results (200 users burst, 0 failures) and infrastructure cost analysis.

→ **[Read detailed analysis](PERF.md)**

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

**Axomind** is a broader project that builds on AuroriaLink. It brings together three connected modules:
- **🗓️ Project planning** — Timeline-based Gantt
- **🧠 Mind maps** — For ideas and knowledge
- **💬 Messaging** — AuroriaLink, integrated as the communication layer

The core idea behind Axomind is **contextual linking**: each conversation is attached to a task or a mind map node, so the discussion and the work it relates to stay in the same place. AuroriaLink remains available as a **standalone messaging app** for people who only need the chat side.

### Custom Modular Framework

Both AuroriaLink and Axomind run on a **custom modular framework** built around a few simple rules:
* **Modular** — the interface, the logic, and the services stay independent of one another
* **Flexible** — pieces work together without being tied together
* **Context-aware** — the app adapts to the user and the device
* **Clean layers** — interface, logic, data, and settings each live in their own layer

<div align="center">
  <a href="https://github.com/Sebastien-VZN/axomind"><img src="https://img.shields.io/badge/Axomind-Repository-3423A6?style=for-the-badge&logo=github&logoColor=white" alt="Axomind Repository"/></a>
</div>

---

## 🤝 Bug Reports & Feedback

AuroriaLink is in beta. Bug reports, feature ideas and general feedback are welcome — open an issue on the repository, every entry is read and considered.

The application source code is proprietary and kept private as a deliberate security choice. This public repository contains the documentation, install guides and release builds — not the codebase. External code contributions aren't part of the project model.

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

## ⚠️ Statut du projet : Version Beta

> Ce projet est en développement actif. Des bugs et comportements inattendus sont probables. Les retours sont bienvenus.

> **📧 À propos des emails**
> L'envoi de mails sortants depuis le serveur autohébergé est bloqué au niveau du FAI, et les relais alternatifs n'ont pas donné de livraison fiable dans cette configuration. **Tout ce qui dépend de l'email est donc désactivé pour le moment** — vérification de compte, réinitialisation de mot de passe et double authentification. Les comptes fonctionnent sans étape email.
> La couche email est intégrée et découplée du flux de connexion normal. Elle sera réactivée quand la plateforme passera chez un provider d'hébergement où l'envoi sortant est fiable — rien d'autre ne changera pour vous.

---

## 🎥 Aperçu

<div align="center">
  <a href="https://github.com/Sebastien-VZN/auroria_link/raw/main/image/output_auroria.mp4">
    <img src="image/desktop_1.jpg" alt="Regarder la vidéo de démonstration" width="500">
  </a>
  <p><sub><em>▶ Cliquez pour regarder la démo — messagerie en temps réel en action</em></sub></p>
</div>

---

## ✨ Fonctionnalités Clés

**🔒 Confidentialité & Sécurité**
- 🔒 **Chiffrement fort** — Messages et fichiers chiffrés en AES-256-GCM, à la fois sur le serveur et lors de l'envoi. Vos conversations restent privées.
- 🛡️ **Double authentification** — 2FA par code email à la connexion avec détection des tentatives suspectes (actuellement désactivée — voir le bloc email ci-dessus).
- 🔐 **Contrôle d'Accès** — Chaque membre ne voit que ce à quoi il est autorisé, avec des permissions par rôle

**⚡ Temps Réel**
- ⚡ **Livraison Instantanée** — Les messages arrivent en direct, avec reconnexion automatique en cas de coupure
- 📱 **Multi-Appareils** — Restez connecté sur **2 appareils pour AuroriaLink** (1 desktop + 1 mobile). Si vous utilisez aussi Axomind, vous disposez de **2 sessions supplémentaires en parallèle** — jusqu'à 4 sessions actives au total par compte, par design

**🎨 Interface**
- 🎨 **26 Thèmes** — Chacun avec une variante claire et une sombre, interchangeables à la volée, avec animations Aurora et glassmorphism (le même set de thèmes qu'Axomind)

**💬 Messagerie**
- 👥 **Canaux Privés** — Des espaces dédiés pour vos équipes, projets ou sujets
- 🎤 **Messages Audio** — Enregistrez et envoyez des clips vocaux dans vos conversations
- 📎 **Partage de Fichiers** — Jusqu'à 10 fichiers par message (documents, images, vidéos, audio — 10 Mo chacun)
- ⏱️ **Rétention** — Messages conservés 1 an sur le serveur / 2 ans en local, avec suppression automatique optionnelle après 24h · Fichiers conservés 1 mois (3 mois si épinglé)

**🧩 Intégrations**
- 🤖 **API Bot** — Envoyez des messages depuis vos outils CI/CD, monitoring ou plateformes d'automatisation (n8n, Make, Zapier...)
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

**Fonctionnement (en clair) :**
1. **L'application** dialogue avec le serveur via une connexion sécurisée (HTTPS), et un canal temps réel séparé garde tout synchronisé en direct
2. **Le canal temps réel** peut maintenir 2 sessions ouvertes pour AuroriaLink (1 desktop + 1 mobile). Le même design supporte 2 sessions supplémentaires pour Axomind en parallèle — 4 sessions actives au total par compte
3. **Le serveur** protège les comptes sur plusieurs niveaux : vérifications des accès, protection contre les attaques, chiffrement AES-256-GCM, et un jeton unique par session
4. **La base de données** stocke tout de façon chiffrée, ne conserve les données que le temps utile, et est optimisée pour des lectures rapides sur les conversations et les messages

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

## 🎨 Galerie

### 💻 Expérience Desktop

<p align="center">
  <img src="image/desktop_1.jpg" alt="Capture desktop 1" width="49%"/>
  <img src="image/desktop_2.jpg" alt="Capture desktop 2" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_3.jpg" alt="Capture desktop 3" width="49%"/>
  <img src="image/desktop_4.jpg" alt="Capture desktop 4" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_5.jpg" alt="Capture desktop 5" width="49%"/>
  <img src="image/desktop_6.jpg" alt="Capture desktop 6" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_7.jpg" alt="Capture desktop 7" width="49%"/>
  <img src="image/desktop_8.jpg" alt="Capture desktop 8" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_9.jpg" alt="Capture desktop 9" width="49%"/>
  <img src="image/desktop_10.jpg" alt="Capture desktop 10" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_11.jpg" alt="Capture desktop 11" width="49%"/>
  <img src="image/desktop_12.jpg" alt="Capture desktop 12" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_13.jpg" alt="Capture desktop 13" width="49%"/>
  <img src="image/desktop_14.jpg" alt="Capture desktop 14" width="49%"/>
</p>

<p align="center">
  <img src="image/desktop_15.jpg" alt="Capture desktop 15" width="49%"/>
</p>

### 📱 Expérience Mobile

<p align="center">
  <img src="image/mobil_0.jpg" alt="Capture mobile 0" width="19%"/>
  <img src="image/mobil_1.jpg" alt="Capture mobile 1" width="19%"/>
  <img src="image/mobil_2.jpg" alt="Capture mobile 2" width="19%"/>
  <img src="image/mobil_3.jpg" alt="Capture mobile 3" width="19%"/>
  <img src="image/mobil_4.jpg" alt="Capture mobile 4" width="19%"/>
</p>

<p align="center">
  <img src="image/mobil_5.jpg" alt="Capture mobile 5" width="19%"/>
  <img src="image/mobil_5.png" alt="Capture mobile 5 (alt)" width="19%"/>
  <img src="image/mobil_6.jpg" alt="Capture mobile 6" width="19%"/>
  <img src="image/mobil_7.jpg" alt="Capture mobile 7" width="19%"/>
  <img src="image/mobil_8.jpg" alt="Capture mobile 8" width="19%"/>
</p>

<p align="center">
  <img src="image/mobil_9.jpg" alt="Capture mobile 9" width="19%"/>
  <img src="image/mobil_10.jpg" alt="Capture mobile 10" width="19%"/>
  <img src="image/mobil_11.jpg" alt="Capture mobile 11" width="19%"/>
  <img src="image/mobil_12.jpg" alt="Capture mobile 12" width="19%"/>
  <img src="image/mobil_13.jpg" alt="Capture mobile 13" width="19%"/>
</p>

---

## 📊 Performance & Coût Réel

Spécifications matériel, résultats des tests de charge (200 users burst, 0 échec) et analyse des coûts d'infrastructure.

→ **[Lire l'analyse détaillée](PERF.md)**

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

**Axomind** est un projet plus large qui s'appuie sur AuroriaLink. Il réunit trois modules connectés :
- **🗓️ Planification** — Diagramme Gantt sur une chronologie
- **🧠 Cartes mentales** — Pour les idées et les connaissances
- **💬 Messagerie** — AuroriaLink, intégré comme couche de communication

L'idée centrale d'Axomind est le **lien contextuel** : chaque conversation est rattachée à une tâche ou à un nœud de carte mentale, pour que la discussion et le travail qui s'y rapporte restent au même endroit. AuroriaLink reste disponible comme **application de messagerie autonome** pour celles et ceux qui n'ont besoin que de la partie chat.

### Framework Modulaire Personnalisé

AuroriaLink et Axomind reposent sur un **framework modulaire personnalisé**, conçu autour de quelques règles simples :
* **Modulaire** — l'interface, la logique et les services restent indépendants
* **Souple** — les éléments collaborent sans être figés ensemble
* **Adapté au contexte** — l'application s'ajuste à l'utilisateur et à l'appareil
* **Couches nettes** — interface, logique, données et réglages vivent chacun dans leur propre couche

<div align="center">
  <a href="https://github.com/Sebastien-VZN/axomind"><img src="https://img.shields.io/badge/Axomind-Dépôt-3423A6?style=for-the-badge&logo=github&logoColor=white" alt="Dépôt Axomind"/></a>
</div>

---

## 🤝 Bugs & Retours

AuroriaLink est en beta. Les remontées de bugs, suggestions et retours d'usage sont les bienvenus — ouvrez une issue sur le dépôt, chaque entrée est lue et étudiée.

Le code source de l'application est propriétaire et reste privé par choix de sécurité. Ce dépôt public contient la documentation, les guides d'installation et les builds de release — pas le code de l'application. Les contributions de code externes ne font pas partie du modèle du projet.

---

## 👤 Auteur

<div align="center">
  <a href="https://sebastien-vezzani.xyz/" target="_blank"><img src="https://img.shields.io/badge/Portfolio-3423A6?style=for-the-badge&logo=firefox-browser&logoColor=white" alt="Lien vers le Portfolio"/></a>
</div>

</details>

---

