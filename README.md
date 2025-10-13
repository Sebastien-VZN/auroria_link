<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Banner" style="width: 256px; height: 256px"/>
  <p style="font-size: 30px"><strong>AuroriaLink</strong></p>
</div>

**AuroriaLink** is a contextual, real-time team messaging solution designed to solve the desynchronization between communication and production tools.

The fundamental architectural principle is the **contextual link**: each discussion thread is intrinsically linked to a reference object (a task, a project, a document). The conversation is no longer an isolated entity but metadata of the object to which it relates. This approach ensures absolute traceability and eliminates the informational noise of general-purpose channels.

### ⚠️ Project Status: Alpha Version

> This project is currently in active development. Bugs and unexpected behaviors are therefore likely. All feedback is welcome.

---

### ✨ Key Features

* **Real-Time Communication**: Architecture based on a **WebSocket (Node.js)** server for instant, full-duplex exchanges and immediate synchronization across all connected clients.
* **Modularity & Integration**: Designed as a standalone module, AuroriaLink can operate as an independent application or be integrated as a service into a third-party application via its API.
* **Robust Backend**: A **PHP 8.4 / PostgreSQL** backend ensures message persistence, user management, permissions, and discussion channels.
* **Cross-Platform Client**: The client, developed in **Flutter**, offers a unified, high-performance, and native user experience on desktop (Windows, macOS, Linux) and mobile (Android, iOS).
* **Contextual API**: The API not only allows sending and receiving messages but also dynamically creating and linking conversations to external object identifiers.
* **Security**: Role-based rights management and channel partitioning ensure secure, context-aware access to conversations.

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

| Platform  | Status                   |
|-----------|--------------------------|
| Android   | ✅ Supported             |
| Windows   | ✅ Supported             |
| Linux     | ✅ Supported             |
| macOS     | ❌ Not yet supported     |
| iOS       | ❌ Not yet supported     |

--- 
# 🚀 Installation Instructions

This guide explains how to install the application on different operating systems.

---

## 📱 Android Installation

> **Important:** Our application is not (yet) on the Google Play Store. Installation requires a few manual steps to allow external sources. This is a standard and secure procedure.

### Step 1: Allow Unknown Sources

1.  **Download the `.apk` file** from our official link.
2.  Open the downloaded file (from your notification bar or file manager).
3.  A security prompt will appear: *"For your security, your phone is not allowed to install unknown apps from this source."*
4.  Tap on the **Settings** button.
5.  Enable the **Allow from this source** (or *Unknown sources*) option.
6.  Go back using the navigation arrow; the installation should now begin.

### Step 2: Bypass Google Play Protect

1.  After Step 1, another window may open, titled **"Blocked by Play Protect"**.
2.  Do not tap "OK". Look for and tap on **Details** or **More details** (often a small link at the bottom).
3.  A new button will appear. Tap on **Install anyway**.

And that's it, the application is installed!

---

## 💻 Windows Installation

> **Warning:** Your antivirus software (including Windows Defender) may show an alert. This is normal behavior for applications that are not certified by Microsoft. Our file is safe.

1.  **Download the `.exe` installer file**.
2.  **Run only this `.exe` file**.
3.  If a blue "Windows protected your PC" screen appears:
    * Click on the **More info** link.
    * Then, click the **Run anyway** button.
4.  If your antivirus quarantines the file, open your antivirus settings and create an exception to allow the file.

---

## 🐧 Linux Installation

> For Linux, you just need to make the file executable before running it.

1.  **Download the application file** (e.g., `file-name.AppImage` or a binary).

2.  **Make the file executable.** You have two options:

    * **Via GUI (Graphical User Interface):**
        1.  Right-click on the file.
        2.  Go to **Properties** → **Permissions** tab.
        3.  Check the box **"Allow executing file as program"**.

    * **Via Terminal:**
        Open a terminal, navigate to the folder containing the file, and type the following command:
        ```bash
        chmod +x file-name
        ```
        *(Replace `file-name` with the actual name of the file)*

3.  **Launch the application** by double-clicking it or by running the following command in the terminal:
    ```bash
    ./file-name
    ```

If you encounter any issues, feel free to contact us.

---
## Light Theme
![img05](image/aurorialink_desktop_06.jpg)
![img06](image/aurorialink_mobile_06.jpg)
![img07](image/aurorialink_mobile_01.jpg)
![img08](image/aurorialink_mobile_03.jpg)

## Dark Theme
![img01](image/aurorialink_desktop_01b.jpg)
![img02](image/aurorialink_mobile_01dark.jpg)
![img03](image/aurorialink_mobile_02.jpg)
![img04](image/aurorialink_mobile_05.jpg)

---
# Axomind & Custom Framework

<div align="center">
  <img src="image/logo_axomind.png" alt="Axomind Banner" style="width: 256px; height: 256px"/>
</div>

AuroriaLink was born from the ongoing development project **Axomind**, an all-in-one team management application based on three interconnected modules: task scheduling over time (`🗓️`), idea structuring (`🧠`), and communication (`💬`).

All of these projects are built upon a **personal modular Flutter framework**, designed around strict principles:
* **Modularity**: Each block (UI, logic, services) is independent.
* **Interoperability**: Components interact dynamically without rigid dependencies.
* **Adaptability**: The application's behavior adjusts to the context (user, platform).
* **Separation of Concerns**: Strict partitioning between business logic, UI, data, and configuration.

## Light Theme
![img09](image/image_light.png)
![img10](image/image_light_2.png)
![img11](image/activity_light.png)

## Dark Theme
![img13](image/image.png)
![img14](image/image2.png)
![img15](image/activity.png)

---
<div align="center">
<a href="https://materiaeobscurataelab.xyz/" target="_blank"><img src="https://img.shields.io/badge/Portfolio-3423A6?style=for-the-badge&logo=firefox-browser&logoColor=white" alt="Link to Portfolio"/></a>
</div>

---
# En Français
**AuroriaLink** est une messagerie d'équipe contextuelle et temps réel, conçue pour résoudre la désynchronisation entre les outils de communication et les outils de production.

Le principe architectural fondamental est le **lien contextuel** : chaque fil de discussion est intrinsèquement lié à un objet de référence (une tâche, un projet, un document). La conversation n'est plus une entité isolée, mais une métadonnée de l'objet auquel elle se rapporte. Cette approche garantit une traçabilité absolue et supprime le bruit informationnel des canaux généralistes.

### ⚠️ Statut du projet : Version Alpha

> Ce projet est actuellement en phase de développement actif. Des bugs et des comportements inattendus sont donc probables. Toute contribution ou retour d'expérience est le bienvenu.

---

### ✨ Fonctionnalités Clés

* **Communication Temps Réel** : Architecture basée sur un serveur **WebSocket (Node.js)** pour des échanges full-duplex instantanés et une synchronisation immédiate entre tous les clients.
* **Modularité & Intégration** : Conçu comme un module autonome, AuroriaLink peut fonctionner en application indépendante ou être intégré comme un service dans une application tierce via son API.
* **Backend Robuste** : Un backend en **PHP 8.4 / PostgreSQL** assure la persistance des messages, la gestion des utilisateurs, des droits et des canaux.
* **Client Multiplateforme** : Le client, développé en **Flutter**, offre une expérience utilisateur unifiée, performante et native sur desktop (Windows, macOS, Linux) et mobile (Android, iOS).
* **API Contextuelle** : L'API permet non seulement d'envoyer et recevoir des messages, mais aussi de créer et lier dynamiquement des conversations à des identifiants d'objets externes.
* **Sécurité** : Gestion des droits et cloisonnement des canaux basés sur les rôles pour un accès sécurisé et contextuel aux conversations.

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

| Plateforme | Support |
|------------|---------|
| Android    | ✅ |
| Windows    | ✅ |
| Linux      | ✅ | 
| macOS      | ❌ non supporté pour le moment |
| iOS        | ❌ non supporté pour le moment |

---
# 🚀 Instructions d'Installation

Ce guide vous explique comment installer l'application sur différents systèmes d'exploitation.

---
## 📱 Installation sur Android

> **Important :** Notre application n'est pas (encore) sur le Google Play Store. L'installation nécessite quelques étapes manuelles pour autoriser les sources externes. C'est une procédure standard et sécurisée.

### Étape 1 : Autoriser les sources inconnues

1.  **Téléchargez le fichier `.apk`** depuis notre lien officiel.
2.  Ouvrez le fichier téléchargé (depuis votre barre de notifications ou votre gestionnaire de fichiers).
3.  Un message de sécurité va apparaître : *"Pour votre sécurité, votre téléphone n'est pas autorisé à installer des applications inconnues de cette source."*
4.  Cliquez sur le bouton **Paramètres**.
5.  Activez l'option **Autoriser pour cette source** (ou *Sources inconnues*).
6.  Revenez en arrière avec la flèche de navigation ; l'installation devrait maintenant commencer.

### Étape 2 : Contourner Google Play Protect

1.  Après l'étape 1, une autre fenêtre peut s'ouvrir, intitulée **"Application bloquée par Play Protect"**.
2.  Ne cliquez pas sur "OK". Cherchez et cliquez sur **Détails** ou **Plus de détails** (souvent un petit lien en bas).
3.  Un nouveau bouton apparaîtra. Cliquez sur **Installer quand même**.

Et voilà, l'application est installée !

---
## 💻 Installation sur Windows

> **Avertissement :** Votre antivirus (y compris Windows Defender) peut afficher une alerte. C'est un comportement normal pour les applications qui ne sont pas certifiées par Microsoft. Notre fichier est sûr.

1.  **Téléchargez le fichier d'installation `.exe`**.
2.  **Exécutez uniquement ce fichier `.exe`**.
3.  Si une fenêtre bleue "Windows a protégé votre ordinateur" apparaît :
    * Cliquez sur le lien **Informations complémentaires**.
    * Cliquez ensuite sur le bouton **Exécuter quand même**.
4.  Si votre antivirus met le fichier en quarantaine, ouvrez les paramètres de votre antivirus et créez une exception pour autoriser le fichier.

---

## 🐧 Installation sur Linux

> Pour Linux, il suffit de rendre le fichier exécutable avant de le lancer.

1.  **Téléchargez le fichier de l'application** (par exemple, `nom-du-fichier.AppImage` ou un binaire).

2.  **Rendez le fichier exécutable.** Vous avez deux options :

    * **Via l'interface graphique :**
        1.  Faites un clic droit sur le fichier.
        2.  Allez dans **Propriétés** → onglet **Permissions**.
        3.  Cochez la case **"Autoriser l'exécution du fichier comme un programme"**.

    * **Via le terminal :**
        Ouvrez un terminal, naviguez jusqu'au dossier contenant le fichier et tapez la commande suivante :
        ```bash
        chmod +x nom-du-fichier
        ```
        *(Remplacez `nom-du-fichier` par le nom réel du fichier)*

3.  **Lancez l'application** en double-cliquant dessus ou en exécutant la commande suivante dans le terminal :
    ```bash
    ./nom-du-fichier
    ```

Si vous rencontrez des problèmes, n'hésitez pas à nous contacter.
---
#  Axomind & Framework Maison

<div align="center">
  <img src="image/logo_axomind.png" alt="AuroriaLink Banner" style="width: 256px; height: 256px"/>
</div>

AuroriaLink est né du projet en cours de developpement **Axomind**, une application tout-en-un de pilotage d'équipe reposant sur trois modules interconnectés : la planification de tâches sur le temps (`🗓️`), la structuration d'idées (`🧠`) et la communication (`💬`).

L'ensemble de ces projets s'appuie sur un **framework Flutter modulaire personnel**, conçu autour de principes stricts :
* **Modularité** : Chaque bloc (UI, logique, services) est indépendant.
* **Interopérabilité** : Les composants interagissent dynamiquement sans dépendances rigides.
* **Adaptabilité** : Le comportement s'ajuste selon le contexte (utilisateur, plateforme).
* **Séparation des responsabilités** : Cloisonnement strict entre logique métier, UI, données et configuration.

---

<div align="center">
<a href="https://materiaeobscurataelab.xyz/" target="_blank"><img src="https://img.shields.io/badge/Portfolio-3423A6?style=for-the-badge&logo=firefox-browser&logoColor=white" alt="Lien vers le Portfolio"/></a>
</div>
