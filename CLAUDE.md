# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Context

**IMPORTANT**: This is the **public documentation and release repository** for AuroriaLink, not the main application codebase. However, this file documents the full architecture for reference purposes.

The repository contains:
- Public-facing README with project description, features, and installation instructions
- Detailed installation guides for supported platforms (Android, Windows, Linux)
- Marketing materials and screenshots in the `image/` directory
- LICENSE file

## Project Overview

**AuroriaLink** is a contextual real-time team messaging platform built with Flutter. The core architectural principle is **contextual linking**: each conversation thread is intrinsically linked to a reference object (task, project, document). This ensures absolute traceability and eliminates noise from generic channels.

---

## AuroriaLink Ecosystem Overview

**AuroriaLink** is a complete ecosystem for contextual team collaboration, composed of three interconnected components:

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│               AuroriaLink (Flutter Client)                          │
│         Android / Windows / Linux - Alpha Version                   │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │ Framework Architecture:                                        │  │
│  │ • GetX routing (AppPages.ctrlDataRoute())                      │  │
│  │ • Provider theme management (light/dark)                       │  │
│  │ • Global singletons: gstData, httpService, webSocketService    │  │
│  │ • Contextual linking: chaque conversation → objet référence    │  │
│  │ • Naming: Gst*** (gestionnaires), Ctrl*** (contrôleurs)        │  │
│  │ • Code & comments in French (author's native language)         │  │
│  └───────────────────────────────────────────────────────────────┘  │
└────────────┬─────────────────────────────────┬──────────────────────┘
             │ HTTP (auth/data)                │ WebSocket
             │ CtrlHttpClientService           │ WebSocketService
             │ ?rt=amxqtv_nx_01_*              │ Headers: x-ws-token,
             │                                 │          x-user-id,
             ↓                                 │          x-plateforme
┌─────────────────────────────┐               ↓
│   Axomind Server (PHP 8.4)  │    ┌──────────────────────────────────┐
│   Custom Framework Backend  │    │  quantive-ws (Node.js)           │
│  ┌───────────────────────┐  │    │  WebSocket Real-time Server      │
│  │ Security Layers:      │  │    │  ┌────────────────────────────┐  │
│  │ 1. Route validation   │  │    │  │ AuthServer (EventEmitter)  │  │
│  │    (regex + whitelist)│  │    │  │ • Port 8080 (clients)      │  │
│  │ 2. Brute force ctrl   │  │    │  │ • Validates via PHP        │  │
│  │    (IP tracking + ban)│  │    │  │ • Emits authenticated evt  │  │
│  │ 3. 2FA flow           │  │    │  └──────────┬─────────────────┘  │
│  │    (PIN email → token)│  │    │             ↓                    │
│  │ 4. AES-256-GCM        │  │    │  ┌────────────────────────────┐  │
│  │    (encrypted fields) │  │    │  │ WSServer (extends Auth)    │  │
│  │                       │  │    │  │ • Singleton pattern        │  │
│  │ Core Services:        │  │    │  │ • Map<userId, connections[]>│ │
│  │ • AuthProcess         │  │    │  │ • Heartbeat 30s ping/pong  │  │
│  │ • AuthRepository      │  │    │  │ • Multi-device support     │  │
│  │ • CryptoService       │  │    │  │ • Connection cleanup       │  │
│  │ • Security            │  │    │  │ • Status updates every 2min│  │
│  │ • DBService           │  │    │  └────────────────────────────┘  │
│  │ • Messenger           │  │    │                                  │
│  │ • Users, Mail, etc.   │  │    │  Internal HTTP API:              │
│  └───────────────────────┘  │    │  • Port 8081 (localhost only)    │
│                              │←───│  • POST /notify (trigger push)   │
│  Route System:               │    │  • GET /status (debug info)      │
│  • Prefix: amxqtv_nx_01_*   │    └──────────────────────────────────┘
│  • Format: ?rt={route_name}  │
│  • Auth: KEY_PASS or uuid    │
│  • ROUTE_INCLUDES_FILES map  │
└──────────────┬───────────────┘
               │ PDO
               ↓
    ┌──────────────────────┐
    │  PostgreSQL Database │
    │  (or MySQL)          │
    │  • Plaintext tokens  │
    │  • Encrypted PII     │
    │  • security_ban_list │
    │  • translate, users  │
    └──────────────────────┘
```

### Tech Stack
- **Client**: Flutter 3.35.7+ (Dart 3.9.2+)
- **Backend**: PHP 8.4 / PostgreSQL
- **Real-time**: Node.js WebSocket server
- **Web Server**: Nginx
- **Deployment**: Debian 13
- **Platforms**: Android, Windows, Linux (macOS and iOS not currently supported)

### Project Status
- **Alpha version 0.0.5** (as of 28/10/2025)
- Active development with expected bugs
- Community feedback encouraged
- Known limitation: Only Gmail addresses work (Microsoft email addresses currently unsupported)

## Common Commands

### Development Setup
```bash
# Install dependencies
flutter pub get

# Clean Flutter build artifacts and caches
.\_script\"netoyage de flutter.bat"

# Run on specific platforms
flutter run -d windows
flutter run -d linux
flutter run -d android

# Build for specific platforms
flutter build windows
flutter build linux
flutter build apk
```

### Testing & Debugging
```bash
# Run tests
flutter test

# Analyze code
flutter analyze
```

### Configuration Flags (lib/app/config/constante_framework.dart)
- `activePageDev`: Enable dev/test page (default: false)
- `forcedOnlineConnectionDebug`: Force debug mode for external server connection
- `activeLogClientServeur`: Enable client/server logging (default: true)
- `activeLogEditor`: Enable text editor logging (default: false)

## Architecture

### Modular Framework Philosophy
AuroriaLink is built on a **custom modular Flutter framework** with strict architectural principles:
- **Modularity**: Each component (UI, logic, services) is independent
- **Interoperability**: Components interact dynamically without rigid dependencies
- **Adaptability**: Behavior adjusts based on context (user, platform)
- **Separation of responsibilities**: Strict boundaries between business logic, UI, data, and configuration

### Directory Structure

```
lib/app/
├── config/                    # Application configuration
│   ├── constante_framework.dart   # Global framework constants & initialization
│   ├── constante_app.dart         # Application-specific constants
│   ├── routes/                    # Routing configuration (GetX)
│   ├── themes/                    # Theme management (light/dark)
│   └── parametre_app/             # App parameters
├── shared_core/               # Core shared services (framework layer)
│   ├── network/
│   │   ├── realtime_sync/         # WebSocket service
│   │   └── http_client/           # HTTP client
│   ├── model_data/                # Data models
│   ├── services/                  # Core services (ctrl_* pattern)
│   ├── security/                  # Authentication & security
│   ├── translate/                 # i18n management
│   ├── files/                     # File management
│   ├── users/                     # User management
│   ├── maps_geolocation/          # Geolocation services
│   └── native_fonction/           # Platform-specific functions
├── shared_widgets/            # Reusable UI components
│   ├── forms/                     # Form components
│   ├── button/                    # Button components
│   ├── texte/                     # Text components
│   └── security/                  # Security UI components
├── libs_messenger/            # Messenger module (main feature)
│   ├── data/                      # Conversation data layer
│   ├── model/                     # Messenger models
│   ├── processing/                # Business logic
│   ├── forms/                     # Messenger forms
│   ├── pages/                     # Messenger pages
│   └── ux/                        # Messenger UX components
├── libs_medias/               # Media handling module
│   ├── model/                     # Media models
│   ├── processing/                # Media processing
│   └── ux/                        # Media UI
├── pages/                     # Application pages
│   └── dashboard/                 # Main dashboard
└── test_dev_tools/            # Development testing tools
```

### Key Architectural Patterns

#### 1. Naming Conventions
- **Gst*** classes: Data gestionnaires (managers) - handle data persistence and retrieval
  - `GstData`: Base file operations
  - `GstAuth`: Authentication management
  - `GstUsers`: User data management
  - `GstDataTranslateApp`: Translation data
  - `GstDataSecurity`: Security data

- **Ctrl*** classes: Controllers - handle business logic and orchestration
  - `CtrlAppTheme`: Theme controller
  - `CtrlHttpClientService`: HTTP service controller
  - `CtrlMediaUser`: Media controller
  - `CtrlBusyInfoActivity`: Loading states controller

#### 2. Global State Management
The framework uses **global singleton instances** initialized in `constante_framework.dart`:
- Initialized via `initParametreApp()` called in `main.dart`
- Key globals: `gstData`, `httpService`, `webSocketService`, `ctrlAppTheme`, `gstTranslate`, `gstAuth`, `gstUsers`
- State management combines GetX for routing and Provider for theme

#### 3. WebSocket Real-time Communication

**Architecture complète en 3 couches:**
1. **Client Flutter** (ce projet) - `lib/app/shared_core/network/realtime_sync/websocket.dart`
2. **Serveur Node.js WebSocket** - Port 8080 (connexions clients) + Port 8081 (API interne)
3. **Backend PHP** - Authentification et logique métier

##### Client Flutter (`WebSocketService`)

**Caractéristiques:**
- Singleton pattern (`factory WebSocketService()`)
- Connexion via `IOWebSocketChannel` de `web_socket_channel`
- **Authentification par headers HTTP** (envoyés lors de l'upgrade WebSocket):
  - `x-ws-token`: Token d'authentification
  - `x-user-id`: ID utilisateur
  - `x-plateforme`: Plateforme (mobile, desktop, web)
- **Auto-reconnexion** avec backoff exponentiel (délai max: 32s)
- **Heartbeat ping/pong**: Géré automatiquement par `dart:io` - répond automatiquement aux pings du serveur
- **Message routing**: Via `WebsocketTransit` model et callback `configDataTransit()`

**États de connexion:**
- `_isConnected`: Booléen indiquant l'état de connexion
- `_isConnecting`: Booléen pour éviter les connexions multiples simultanées
- `_manualDisconnect`: Flag pour différencier déconnexion manuelle vs erreur

**Flow de connexion:**
```
connect() → IOWebSocketChannel.connect(uri, headers)
         → onDone (si erreur/déconnexion)
         → _attemptReconnect() (si non manuel)
```

**Reconnexion automatique:**
- Tentatives illimitées (jusqu'à `disconnect()` manuel)
- Délai: `min(2^n secondes, 32 secondes)` où n = nombre de tentatives
- Reset du compteur sur connexion réussie

##### Serveur Node.js WebSocket

**Architecture du serveur (3 classes principales):**

1. **AuthServer.js** (classe parente, extends EventEmitter)
   - Écoute sur port 8080 (0.0.0.0) pour les connexions WebSocket
   - Intercepte les requêtes d'upgrade WebSocket
   - Extrait les headers: `x-ws-token`, `x-user-id`, `x-plateforme`
   - **Valide l'authentification** via POST au backend PHP:
     - URL: `http://127.0.0.1/app/index.php?rt=amxqtv_nx_01_auth_action_websocket`
     - Payload: `{token_ws, id_user, plateforme, KEY_PASS}`
   - Si valide: émet l'événement `authenticatedConnection`
   - Si invalide: rejette avec HTTP 401/403

2. **WSServer.js** (extends AuthServer, singleton pattern)
   - Gère les connexions authentifiées dans une `Map<userId, Array<{ws, plateforme}>>`
   - **Support multi-device**: Plusieurs connexions par utilisateur (identifiées par plateforme)
   - **Heartbeat mechanism** (ping/pong):
     ```javascript
     let isAlive = true;
     setInterval(() => {
       if (!isAlive) ws.terminate(); // Connexion morte
       isAlive = false;
       ws.ping(); // Envoie ping au client
     }, 30000); // Toutes les 30 secondes

     ws.on('pong', () => { isAlive = true; }); // Client a répondu
     ```
   - **Critical**: Le ping/pong détecte les connexions zombies (mobiles qui perdent le réseau sans fermeture TCP)
   - Envoie l'état des connexions aux clients toutes les 2 minutes
   - Nettoie automatiquement les connexions mortes de la Map

3. **Logger.js**
   - Logs fichiers dans `app.log`
   - Actuellement désactivé par défaut (`ACTIVE_DEBUG = false`)

**API HTTP interne (Port 8081, localhost uniquement):**

- **POST /notify** - Envoyer des notifications aux clients connectés
  ```json
  {
    "target": "user" | "broadcast",
    "userId": "string|number",        // Requis si target = "user"
    "plateforme": "string",           // Optionnel: filtre par plateforme
    "service": "string",
    "message": "string",
    "data": {}
  }
  ```
  - `target: "user"`: Envoie à toutes les connexions d'un userId (ou filtré par plateforme)
  - `target: "broadcast"`: Envoie à tous les clients connectés

- **GET /status** - Informations de debug (utilisateurs connectés, plateformes, total connexions)

**Lifecycle du serveur:**
- Entry point: `server.js`
- Graceful shutdown sur SIGINT/SIGTERM
- Ferme toutes les connexions WebSocket avant exit
- Rapport d'état toutes les 12h (utilisateurs connectés, sessions)

##### Backend PHP (Authentification)

**Route WebSocket:** `amxqtv_nx_01_auth_action_websocket`

**Flow d'authentification:**
1. Node.js reçoit headers WebSocket (`x-ws-token`, `x-user-id`, `x-plateforme`)
2. Node.js POST au PHP avec `{token_ws, id_user, plateforme, KEY_PASS}`
3. PHP valide le token via `AuthRepository::isTokenValid()`
4. PHP retourne `{user_id, plateforme}` si valide
5. Node.js complète l'upgrade WebSocket

**Tokens par plateforme (colonnes DB):**
- Web: `token_auth_web`
- Mobile: `token_auth_mobile`
- Desktop: `token_auth_desktop`

**Sécurité:**
- Tokens stockés en clair dans la DB (chiffrés pour le client via AES-256-GCM)
- TTL token: 7 jours (configurable via `NB_DAYS_AUTH_TOKEN`)
- KEY_PASS partagé entre Node.js et PHP (doit correspondre)

##### Flux complet de communication temps réel

**1. Connexion initiale:**
```
Client Flutter → WebSocket upgrade (port 8080) avec headers
              → Node.js AuthServer → POST PHP backend
              → PHP valide token
              → Node.js accepte connexion
              → WSServer stocke dans Map
              → Client reçoit confirmation
```

**2. Envoi de notification (exemple: nouveau message):**
```
Utilisateur A envoie message → POST PHP backend (HTTP)
                            → PHP traite message
                            → PHP POST Node.js (http://127.0.0.1:8081/notify)
                            → Node.js route vers userId destinataire
                            → Destinataire reçoit via WebSocket en temps réel
```

**3. Heartbeat (détection connexions mortes):**
```
Toutes les 30s:
Node.js → ping → Client Flutter (dart:io répond automatiquement avec pong)
       → pong ←
Si pas de pong: Node.js termine la connexion et nettoie la Map
```

**4. Reconnexion automatique:**
```
Connexion perdue (réseau, serveur down, etc.)
→ onDone triggered dans Flutter
→ _attemptReconnect() avec backoff exponentiel
→ Retry jusqu'à succès
```

##### Configuration et ports

- **WebSocket client→serveur**: Port 8080 (défini dans `lib/app/config/parametre_app/websocket.dart`)
- **API HTTP interne (PHP→Node.js)**: Port 8081, localhost uniquement
- **Schéma WebSocket**: Configuré via `getSchemeWebsocket()`, `getUrlWebsocket()`, `getPortWs()`

##### Points importants

- **Client répond automatiquement aux pings**: Pas besoin de code explicite côté Flutter, `dart:io` gère ça
- **Multi-device supporté**: Un utilisateur peut avoir plusieurs connexions simultanées (mobile + desktop)
- **Stateless côté Node.js**: Le serveur WebSocket ne fait que router, toute la logique métier est dans PHP
- **Heartbeat critique pour mobile**: Détecte les connexions zombies quand le mobile perd le réseau sans fermeture TCP propre
- **Message routing**: Utilise le callback `configDataTransit()` enregistré via `setCallbackTransitDataWebSocket()`

#### 4. Routing System
- GetX-based routing in `lib/app/config/routes/`
- Initial route determined by `AppPages.ctrlDataRoute()`:
  - Checks network connectivity
  - Handles deep links (politique_confidentialite, redirect_share, info)
  - Dev mode routing via `activePageDev` flag
  - Default: loader page

#### 5. Data Persistence
- Local JSON files via `GstData.readJsonFile()` / `writeJsonFile()`
- Asset JSON loading via `readJsonFileLocalAsset()`
- Cached files in app-specific directories managed by `AssetsFolderCache`
- SharedPreferences for simple key-value storage

#### 6. Translation System
- Two-tier translation: `gstTranslate` (app text) and `gstTranslateConfig` (config)
- Offline-first: `gstTranslate.initOffLine()`
- Default locale: system locale (Platform.localeName)
- Assets: `assets/json/translate/`

## Messenger Module (libs_messenger)

This is the core feature of AuroriaLink:
- **ConversationRepository**: Data access layer for conversations
- **ConversationManager**: Business logic controller
- **UsersCollaboratorData**: Manages conversation participants
- Global conversation ID: `relIdConversation` (lib/app/config/constante_app.dart)

Key files:
- `lib/app/libs_messenger/ux/body_message.dart`: Message body UI
- `lib/app/libs_messenger/ux/info_user_respond.dart`: User response info

## Important Notes

### Development Practices
- Framework uses French variable names and comments (author's native language)
- Extensive use of global singletons for cross-cutting concerns
- GetX is used primarily for routing, not full reactive state management
- Theme switching uses Provider pattern with `ChangeNotifierProvider`

### Backend Integration
- HTTP requests via `CtrlHttpClientService` extending `BaseApi`
- WebSocket for real-time messaging
- Server parameters synced via `gstParametresGlobal.initData()`

### Platform-Specific Code
- Platform detection: `Platform.localeName`, platform-specific widgets in `native_fonction/`
- Geolocation: `lib/app/shared_core/maps_geolocation/`
- File handling varies by platform, managed through `path_provider` package

### Custom Framework Origin
This project is part of **Axomind**, a larger ecosystem with a custom modular Flutter framework designed for:
- Task planning (🗓️)
- Idea structuring (🧠)
- Communication (💬)

The framework emphasizes **polymorphic behaviors** and **dynamic interconnectivity** between independent components that can evolve and reconfigure based on context.

---

## Working with This Documentation Repository

### Documentation Updates
When updating documentation in this repo:
- Maintain **bilingual format** (English first, French in collapsible section at bottom)
- Keep version numbers and release links synchronized
- Update both README.md and installation_instructions.md if installation process changes
- Preserve existing markdown formatting and badge styles

### Release Information
- Downloads hosted on GitHub Releases
- Release naming format: `alpha_X.X.X`
- Assets: `app-android.apk`, `windows.zip`, `linux.tar.gz`
- Update version number in README when new releases are published

### Image Assets
- Logo: `image/auroria_link_256.png` (256x256)
- Axomind logo: `image/logo_axomind.png`
- Screenshots organized by theme (light/dark) and platform (desktop/mobile)
- Naming convention: `aurorialink_{platform}_{number}[dark].jpg`

### Repository Context
1. This is a **documentation repository only** - no application code exists here
2. The actual application codebase is in a separate, private repository
3. This repo serves as the public face for the project on GitHub
4. All content is bilingual (English/French) with French in collapsible sections
5. The project uses a **proprietary license**
