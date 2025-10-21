<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Logo" width="150"/>
  <h1>AuroriaLink</h1>
  <p><strong>A contextual, real-time team messaging solution.</strong></p>
  
  <p>
    <img src="https://img.shields.io/badge/status-alpha-orange?style=for-the-badge" alt="Project Status: Alpha"/>
    <img src="https://img.shields.io/badge/license-Proprietary-red?style=for-the-badge" alt="License: Proprietary"/>
  </p>
</div>

**AuroriaLink** is a contextual, real-time team messaging solution designed to solve the desynchronization between communication and production tools.

The fundamental architectural principle is the **contextual link**: each discussion thread is intrinsically linked to a specific production element. The conversation is no longer an isolated entity but dynamic metadata of the object to which it relates, whether it is **a node in a project tree (mindmap `🧠`)** or **a task in a timeline planner (`🗓️`)**.

This approach ensures absolute traceability and anchors communication directly within the workflow, eliminating the informational noise of general-purpose channels.

---

## 🚀 Get the Latest Version

- version 0.0.3

<div align="center">
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases/download/alpha_0.0.3/app-android.apk">
    <img src="https://img.shields.io/badge/Download%20for-Android-3DDC84?style=for-the-badge&logo=android" alt="Download for Android"/>
  </a>
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases/download/alpha_0.0.3/windows.zip">
    <img src="https://img.shields.io/badge/Download%20for-Windows-0078D6?style=for-the-badge&logo=windows" alt="Download for Windows"/>
  </a>
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases/download/alpha_0.0.3/linux.tar.gz">
    <img src="https://img.shields.io/badge/Download%20for-Linux-FCC624?style=for-the-badge&logo=linux" alt="Download for Linux"/>
  </a>
</div>

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
> Please note: Microsoft email addresses do not work. Only Gmail addresses work at this time.

---

### ✨ Key Features

-   **⚡ Real-Time Communication**: Architecture based on a **WebSocket (Node.js)** server for instant, full-duplex exchanges.
-   **🔒 Absolute Privacy & Encryption**: The messaging is **100% private**. All messages and files are **fully encrypted**, both in transit and at rest on the server, ensuring maximum security.
-   **👥 Private Discussion Channels**: Create partitioned channels for specific teams, projects, or topics, accessible only to authorized members.
-   **🎤 Sequential Audio Messaging**: Record and send encrypted audio clips to create a fluid vocal conversation thread.
-   **🧩 Modularity & Integration**: Designed as a standalone module that can be integrated as a service via its API.
-   **💪 Robust Backend**: A **PHP 8.4 / PostgreSQL** backend ensures data persistence, user management, and permissions.
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

<details>
<summary>Click to see installation instructions</summary>

### 📱 Android Installation

> **Important:** Our application is not (yet) on the Google Play Store. Installation requires a few manual steps to allow external sources. This is a standard and secure procedure.

#### Step 1: Allow Unknown Sources
1.  **Download the `app-android.apk` file** from the [latest release](https://github.com/Sebastien-VZN/auroria_link/releases/tag/).
2.  Open the downloaded file (from your notification bar or file manager).
3.  A security prompt will appear: *"For your security, your phone is not allowed to install unknown apps from this source."*
4.  Tap on the **Settings** button.
5.  Enable the **Allow from this source** (or *Unknown sources*) option.
6.  Go back using the navigation arrow; the installation should now begin.

#### Step 2: Bypass Google Play Protect
1.  After Step 1, another window may open, titled **"Blocked by Play Protect"**.
2.  Do not tap "OK". Look for and tap on **Details** or **More details** (often a small link at the bottom).
3.  A new button will appear. Tap on **Install anyway**.

And that's it, the application is installed!

---

### 💻 Windows Installation

> **Warning:** Your antivirus software (including Windows Defender) may show an alert. This is normal behavior for applications that are not certified by Microsoft. Our file is safe.

1.  **Download the `windows.tar.gz` archive** from the [latest release](https://github.com/Sebastien-VZN/auroria_link/releases/tag/).
2.  **Decompress the archive.**
3.  **Run the `.exe` file** located inside the extracted folder.
4.  If a blue "Windows protected your PC" screen appears:
    * Click on the **More info** link.
    * Then, click the **Run anyway** button.
5.  If your antivirus quarantines the file, open your antivirus settings and create an exception to allow the file.

---

### 🐧 Linux Installation

> For Linux, you just need to make the file executable before running it.

1.  **Download the `linux.tar.gz` archive** from the [latest release](https://github.com/Sebastien-VZN/auroria_link/releases/tag/) and decompress it.
2.  **Make the application file executable.** You have two options:
    * **Via GUI (Graphical User Interface):**
        1.  Right-click on the application file.
        2.  Go to **Properties** → **Permissions** tab.
        3.  Check the box **"Allow executing file as program"**.
    * **Via Terminal:**
        ```bash
        chmod +x file-name
        ```
        *(Replace `file-name` with the actual name of the executable file)*
3.  **Launch the application** by double-clicking it or by running it from the terminal:
    ```bash
    ./file-name
    ```

If you encounter any issues, feel free to contact us or open an issue.

</details>

---

## 🎨 Gallery

<details>
<summary>🖼️ Light Theme Screenshots</summary>

| Desktop | Mobile | Mobile | Mobile |
| :---: | :---: | :---: | :---: |
| ![img05](image/aurorialink_desktop_06.jpg) | ![img06](image/aurorialink_mobile_06.jpg) | ![img07](image/aurorialink_mobile_01.jpg) | ![img08](image/aurorialink_mobile_03.jpg) |

</details>

<details>
<summary>🌙 Dark Theme Screenshots</summary>

| Desktop | Mobile | Mobile | Mobile |
| :---: | :---: | :---: | :---: |
| ![img01](image/aurorialink_desktop_01b.jpg) | ![img02](image/aurorialink_mobile_01dark.jpg) | ![img03](image/aurorialink_mobile_02.jpg) | ![img04](image/aurorialink_mobile_05.jpg) |

</details>

---

## 🌱 Origins: Axomind & Custom Framework

<div align="center">
  <img src="image/logo_axomind.png" alt="Axomind Logo" width="150"/>
</div>

AuroriaLink was born from the ongoing development project **Axomind**, an all-in-one team management application based on three interconnected modules: task scheduling (`🗓️`), idea structuring (`🧠`), and communication (`💬`).

This project is built upon a **personal modular Flutter framework**, designed around these strict principles:
* **Modularity**: Each block (UI, logic, services) is independent.
* **Interoperability**: Components interact dynamically without rigid dependencies.
* **Adaptability**: The application's behavior adjusts to the context (user, platform).
* **Separation of Concerns**: Strict partitioning between business logic, UI, data, and configuration.

<details>
<summary>👁️ Axomind App Preview</summary>

**Light Theme**
<p>
<img src="image/image_light.png" alt="Axomind Light 1" width="32%"/>
<img src="image/image_light_2.png" alt="Axomind Light 2" width="32%"/>
<img src="image/activity_light.png" alt="Axomind Light 3" width="32%"/>
</p>

**Dark Theme**
<p>
<img src="image/image.png" alt="Axomind Dark 1" width="32%"/>
<img src="image/image2.png" alt="Axomind Dark 2" width="32%"/>
<img src="image/activity.png" alt="Axomind Dark 3" width="32%"/>
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
  <p><strong>Une messagerie d'équipe contextuelle et temps réel.</strong></p>
</div>

**AuroriaLink** est une messagerie d'équipe contextuelle et temps réel, conçue pour résoudre la désynchronisation entre les outils de communication et les outils de production.

Le principe architectural fondamental est le **lien contextuel** : chaque fil de discussion est intrinsèquement lié à un élément de production précis. La conversation n'est plus une entité isolée, mais une métadonnée dynamique de l'objet auquel elle se rapporte, que ce soit **un nœud dans une arborescence de projet (mindmap `🧠`)** ou **une tâche dans un planificateur temporel (`🗓️`)**.

Cette approche garantit une traçabilité absolue et ancre la communication directement dans le flux de travail, supprimant le bruit informationnel des canaux généralistes.

### ⚠️ Statut du projet : Version Alpha

> Ce projet est actuellement en phase de développement actif. Des bugs et des comportements inattendus sont donc probables. Toute contribution ou retour d'expérience est le bienvenu.
> Attention : les adresses e-mail Microsoft ne fonctionnent pas. Seules les adresses Gmail fonctionnent pour le moment.

---

## 🚀 Télécharger la dernière version

<div align="center">
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases/download/alpha_0.0.3/app-android.apk">
    <img src="https://img.shields.io/badge/Download%20for-Android-3DDC84?style=for-the-badge&logo=android" alt="Android"/>
  </a>
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases/download/alpha_0.0.3/windows.zip">
    <img src="https://img.shields.io/badge/Download%20for-Windows-0078D6?style=for-the-badge&logo=windows" alt="Windows"/>
  </a>
  <a href="https://github.com/Sebastien-VZN/auroria_link/releases/download/alpha_0.0.3/linux.tar.gz">
    <img src="https://img.shields.io/badge/Download%20for-Linux-FCC624?style=for-the-badge&logo=linux" alt="Linux"/>
  </a>
</div>

---

### ✨ Fonctionnalités Clés

-   **⚡ Communication Temps Réel** : Architecture basée sur un serveur **WebSocket (Node.js)** pour des échanges full-duplex instantanés.
-   **🔒 Confidentialité & Cryptage Absolu** : La messagerie est **100% privée**. Tous les messages et fichiers sont **entièrement cryptés**, que ce soit durant leur transit ou lors de leur stockage sur le serveur, garantissant une sécurité maximale.
-   **👥 Canaux de Discussion Privés** : Créez des canaux cloisonnés pour des équipes, projets ou sujets spécifiques, accessibles uniquement aux membres autorisés.
-   **🎤 Messagerie Audio Séquentielle** : Enregistrez et envoyez des clips audio cryptés pour créer un fil de conversation vocal fluide.
-   **🧩 Modularité & Intégration** : Conçu comme un module autonome pouvant être intégré comme service via son API.
-   **💪 Backend Robuste** : Un backend en **PHP 8.4 / PostgreSQL** assure la persistance des données, la gestion des utilisateurs et des droits.
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

---
## 💻 Plateformes supportées

| Plateforme | Statut                       |
|:----------:|:-----------------------------|
| Android    | ✅ Supporté                  |
| Windows    | ✅ Supporté                  |
| Linux      | ✅ Supporté                  |
| macOS      | ❌ Non supporté pour le moment |
| iOS        | ❌ Non supporté pour le moment |

---
## 🚀 Instructions d'Installation

<details>
<summary>Cliquez pour voir les instructions d'installation</summary>

### 📱 Installation sur Android

> **Important :** Notre application n'est pas (encore) sur le Google Play Store. L'installation nécessite quelques étapes manuelles pour autoriser les sources externes. C'est une procédure standard et sécurisée.

#### Étape 1 : Autoriser les sources inconnues
1.  **Téléchargez le fichier `app-android.apk`** depuis le lien des [dernières versions](https://github.com/Sebastien-VZN/auroria_link/releases/tag/).
2.  Ouvrez le fichier téléchargé (depuis votre barre de notifications ou votre gestionnaire de fichiers).
3.  Un message de sécurité va apparaître : *"Pour votre sécurité, votre téléphone n'est pas autorisé à installer des applications inconnues de cette source."*
4.  Cliquez sur le bouton **Paramètres**.
5.  Activez l'option **Autoriser pour cette source** (ou *Sources inconnues*).
6.  Revenez en arrière avec la flèche de navigation ; l'installation devrait maintenant commencer.

#### Étape 2 : Contourner Google Play Protect
1.  Après l'étape 1, une autre fenêtre peut s'ouvrir, intitulée **"Application bloquée par Play Protect"**.
2.  Ne cliquez pas sur "OK". Cherchez et cliquez sur **Détails** ou **Plus de détails** (souvent un petit lien en bas).
3.  Un nouveau bouton apparaîtra. Cliquez sur **Installer quand même**.

Et voilà, l'application est installée !

---
### 💻 Installation sur Windows

> **Avertissement :** Votre antivirus (y compris Windows Defender) peut afficher une alerte. C'est un comportement normal pour les applications qui ne sont pas certifiées par Microsoft. Notre fichier est sûr.

1.  **Téléchargez l'archive `windows.tar.gz`** depuis le lien des [dernières versions](https://github.com/Sebastien-VZN/auroria_link/releases/tag/).
2.  **Décompressez l'archive.**
3.  **Exécutez le fichier `.exe`** qui se trouve dans le dossier décompressé.
4.  Si une fenêtre bleue "Windows a protégé votre ordinateur" apparaît :
    * Cliquez sur le lien **Informations complémentaires**.
    * Cliquez ensuite sur le bouton **Exécuter quand même**.
5.  Si votre antivirus met le fichier en quarantaine, ouvrez les paramètres de votre antivirus et créez une exception pour autoriser le fichier.

---

### 🐧 Installation sur Linux

> Pour Linux, il suffit de rendre le fichier exécutable avant de le lancer.

1.  **Téléchargez l'archive `linux.tar.gz`** depuis le lien des [dernières versions](https://github.com/Sebastien-VZN/auroria_link/releases/tag/) et décompressez-la.
2.  **Rendez le fichier de l'application exécutable.** Vous avez deux options :
    * **Via l'interface graphique :**
        1.  Faites un clic droit sur le fichier de l'application.
        2.  Allez dans **Propriétés** → onglet **Permissions**.
        3.  Cochez la case **"Autoriser l'exécution du fichier comme un programme"**.
    * **Via le terminal :**
        ```bash
        chmod +x nom-du-fichier
        ```
        *(Remplacez `nom-du-fichier` par le nom réel du fichier exécutable)*
3.  **Lancez l'application** en double-cliquant dessus ou en exécutant la commande suivante dans le terminal :
    ```bash
    ./nom-du-fichier
    ```
Si vous rencontrez des problèmes, n'hésitez pas à nous contacter ou à ouvrir une "issue".

</details>

</details>