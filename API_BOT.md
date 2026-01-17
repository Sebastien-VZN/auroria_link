<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Logo" width="100"/>
  <h1>AuroriaLink Bot API</h1>
  <p><strong>Integrate automated messaging into your workflows</strong></p>

  <p>
    <img src="https://img.shields.io/badge/API-v1.0-green?style=for-the-badge" alt="API Version"/>
    <img src="https://img.shields.io/badge/Method-POST-blue?style=for-the-badge" alt="HTTP Method"/>
  </p>
</div>

---

## Overview

The AuroriaLink Bot API allows third-party applications to send automated messages to group conversations. This enables powerful integrations such as:

- **Monitoring alerts** - Send system notifications to your team
- **CI/CD pipelines** - Notify about build statuses and deployments
- **Scheduled reports** - Automate daily/weekly updates
- **n8n/Zapier workflows** - Connect AuroriaLink to hundreds of services
- **Custom applications** - Build your own integrations

---

## Table of Contents

- [Quick Start](#-quick-start)
- [Complete Workflow](#-complete-workflow)
- [API Reference](#-api-reference)
- [Code Examples](#-code-examples)
- [Security](#-security)
- [Rate Limiting](#-rate-limiting)
- [Error Handling](#-error-handling)
- [Real-Time Delivery](#-real-time-delivery)
- [FAQ](#-faq)
- [Version Fran&ccedil;aise](#-version-française)

---

## Quick Start

### Prerequisites

1. An AuroriaLink account
2. At least one group conversation where you have admin rights
3. Your bot's `key_access` token (obtained via the app)

### Send Your First Message

```bash
curl -X POST "https://quantive-studio.xyz/app/bot_api.php?route=api_messenger" \
  -d "key_access=YOUR_BOT_TOKEN" \
  -d "type_action=add_message" \
  -d "content_message=Hello from my bot!"
```

**Success Response:**
```json
{"return_code": 0}
```

---

## Complete Workflow

The Bot API follows a simple 4-step workflow:

```
┌─────────────────────────────────────────────────────────────────────┐
│                        Bot API Workflow                              │
└─────────────────────────────────────────────────────────────────────┘

   ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
   │   1. CREATE  │ ──▸  │  2. ASSIGN   │ ──▸  │   3. SEND    │
   │     BOT      │      │   TO GROUPS  │      │   MESSAGES   │
   └──────────────┘      └──────────────┘      └──────────────┘
         │                     │                     │
         ▼                     ▼                     ▼
   ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
   │ Get token    │      │ Select conv. │      │ POST to API  │
   │ (one-time)   │      │ in app       │      │ endpoint     │
   └──────────────┘      └──────────────┘      └──────────────┘
                                                     │
                                                     ▼
                                              ┌──────────────┐
                                              │ 4. RECEIVE   │
                                              │ (WebSocket)  │
                                              └──────────────┘
```

### Step 1: Create a Bot

In the AuroriaLink application:

1. Navigate to **Settings** > **Bots Management**
2. Click **"Create New Bot"**
3. Fill in the bot details:
   - **Name**: Display name for your bot
   - **Avatar**: Profile picture URL
   - **Description**: What the bot does
4. Click **"Create"**

**Important:** The `key_access` token is displayed **only once** at creation. Copy and store it securely!

### Step 2: Assign Bot to Conversations

1. Open a group conversation where you are an admin
2. Go to **Conversation Settings** > **Bots**
3. Select your bot from the list
4. Click **"Add Bot"**

The bot can now send messages to this conversation.

### Step 3: Send Messages via API

Make a POST request to the Bot API endpoint:

```bash
POST https://quantive-studio.xyz/app/bot_api.php?route=api_messenger
```

### Step 4: Real-Time Delivery

Messages are delivered instantly to all connected clients via WebSocket. No polling required!

---

## API Reference

### Endpoint

```
POST https://quantive-studio.xyz/app/bot_api.php?route=api_messenger
```

### Headers

| Header | Value | Required |
|--------|-------|----------|
| `Content-Type` | `application/x-www-form-urlencoded` | Recommended |

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `key_access` | string | **Yes** | Your bot's authentication token (encrypted) |
| `type_action` | string | **Yes** | Action to perform. Currently: `add_message` |
| `content_message` | string | **Yes** | The message content to send |

### Response

**Success (HTTP 200):**
```json
{
  "return_code": 0
}
```

**Bot not assigned to any conversation (HTTP 200):**
```json
{
  "return_info": "your key access is not affected"
}
```

**Rate limit exceeded (HTTP 200):**
```json
{
  "return_info": "Please respect the imposed usage limit of 10 requests per minute"
}
```

**Authentication failed (HTTP 404):**
```
(empty response)
```

---

## Code Examples

### cURL

```bash
curl -X POST "https://quantive-studio.xyz/app/bot_api.php?route=api_messenger" \
  -d "key_access=TUlOREZDSyqlLtCi..." \
  -d "type_action=add_message" \
  -d "content_message=Server status: All systems operational"
```

### Python

```python
import requests

def send_bot_message(token: str, message: str) -> dict:
    """Send a message via AuroriaLink Bot API."""
    url = "https://quantive-studio.xyz/app/bot_api.php"

    payload = {
        "key_access": token,
        "type_action": "add_message",
        "content_message": message
    }

    response = requests.post(
        url,
        params={"route": "api_messenger"},
        data=payload
    )

    return response.json()

# Usage
result = send_bot_message(
    token="YOUR_BOT_TOKEN",
    message="Daily report: 150 orders processed"
)
print(result)  # {"return_code": 0}
```

### JavaScript (Node.js)

```javascript
const https = require('https');
const querystring = require('querystring');

function sendBotMessage(token, message) {
  return new Promise((resolve, reject) => {
    const postData = querystring.stringify({
      key_access: token,
      type_action: 'add_message',
      content_message: message
    });

    const options = {
      hostname: 'quantive-studio.xyz',
      port: 443,
      path: '/app/bot_api.php?route=api_messenger',
      method: 'POST',
      headers: {
        'Content-Type': 'application/x-www-form-urlencoded',
        'Content-Length': Buffer.byteLength(postData)
      }
    };

    const req = https.request(options, (res) => {
      let data = '';
      res.on('data', chunk => data += chunk);
      res.on('end', () => resolve(JSON.parse(data)));
    });

    req.on('error', reject);
    req.write(postData);
    req.end();
  });
}

// Usage
sendBotMessage('YOUR_BOT_TOKEN', 'Build #1234 completed successfully!')
  .then(result => console.log(result))
  .catch(error => console.error(error));
```

### PHP

```php
<?php

function sendBotMessage(string $token, string $message): array
{
    $url = 'https://quantive-studio.xyz/app/bot_api.php?route=api_messenger';

    $postData = [
        'key_access' => $token,
        'type_action' => 'add_message',
        'content_message' => $message
    ];

    $ch = curl_init($url);
    curl_setopt($ch, CURLOPT_POST, true);
    curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($postData));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_HTTPHEADER, [
        'Content-Type: application/x-www-form-urlencoded'
    ]);

    $response = curl_exec($ch);
    $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
    curl_close($ch);

    if ($httpCode === 404) {
        return ['error' => 'Authentication failed'];
    }

    return json_decode($response, true) ?? ['error' => 'Invalid response'];
}

// Usage
$result = sendBotMessage(
    'YOUR_BOT_TOKEN',
    'New user registered: john.doe@example.com'
);
print_r($result);
```

### n8n Workflow

In n8n, use an **HTTP Request** node:

| Setting | Value |
|---------|-------|
| Method | POST |
| URL | `https://quantive-studio.xyz/app/bot_api.php?route=api_messenger` |
| Body Content Type | Form URL Encoded |
| Body Parameters | `key_access`: `{{$credentials.auroriaToken}}` |
| | `type_action`: `add_message` |
| | `content_message`: `{{$node["Previous"].json["message"]}}` |

---

## Security

### Token Security

- **Encrypted in transit**: Tokens are encrypted with AES-256-GCM when transmitted
- **HTTPS required**: All API calls must use HTTPS (HTTP requests are rejected)
- **One-time visibility**: Tokens are only shown once at creation - store them securely
- **No expiration**: Tokens don't expire, but can be regenerated if compromised

### Regenerating a Compromised Token

If your token is compromised:

1. Open AuroriaLink app
2. Go to **Settings** > **Bots Management**
3. Select your bot
4. Click **"Regenerate Token"**

The old token is immediately invalidated.

### Best Practices

| Practice | Description |
|----------|-------------|
| Use environment variables | Store tokens in `$ENV` variables, never in code |
| Rotate periodically | Regenerate tokens every 90 days |
| Limit bot scope | Assign bots only to necessary conversations |
| Monitor usage | Watch for unusual activity patterns |

---

## Rate Limiting

To protect the service, rate limiting is enforced:

| Limit | Value |
|-------|-------|
| Requests per token | **10 requests per 60 seconds** |
| Ban threshold | **15 failed auth attempts** |
| Ban duration | **10 minutes** |

### Rate Limit Response

When rate limit is exceeded:

```json
{
  "return_info": "Please respect the imposed usage limit of 10 requests per minute"
}
```

### Recommendations

- Implement exponential backoff on errors
- Queue messages and send in batches if needed
- Cache responses when appropriate

---

## Error Handling

### Response Codes

| Scenario | HTTP Code | Response Body | Action |
|----------|-----------|---------------|--------|
| Success | 200 | `{"return_code": 0}` | Message sent |
| Bot not assigned | 200 | `{"return_info": "..."}` | Assign bot to conversations |
| Rate limit | 200 | `{"return_info": "..."}` | Wait 60 seconds |
| Invalid token | 404 | *(empty)* | Check/regenerate token |
| Invalid route | 404 | *(empty)* | Check URL format |
| Missing params | 404 | *(empty)* | Verify all required parameters |

### Common Issues

#### "return_info" Response

Your bot isn't assigned to any conversation.

**Solution:**
1. Open a group conversation in AuroriaLink
2. Add your bot via conversation settings

#### Empty 404 Response

Authentication failed or invalid request.

**Checklist:**
- [ ] Token is correct and not regenerated
- [ ] URL is `https://quantive-studio.xyz/app/bot_api.php?route=api_messenger`
- [ ] Method is POST (not GET)
- [ ] `type_action` is `add_message`
- [ ] `content_message` is not empty

#### Rate Limit Exceeded

Too many requests in a short period.

**Solution:** Wait 60 seconds before retrying.

---

## Real-Time Delivery

### WebSocket Architecture

Messages sent via the Bot API are delivered in real-time to all connected clients:

```
Bot API ──▸ PHP Backend ──▸ Node.js WebSocket Server ──▸ Connected Clients
                                      │
                                      ├──▸ Mobile (Android)
                                      ├──▸ Desktop (Windows/Linux)
                                      └──▸ Other sessions
```

### Delivery Guarantees

| Feature | Description |
|---------|-------------|
| **Instant delivery** | Messages pushed via WebSocket within milliseconds |
| **Multi-device** | Delivered to all connected devices (max 2 per user) |
| **Offline handling** | Messages stored and synced when user reconnects |
| **Broadcast** | Sent to all participants in assigned conversations |

### What Clients Receive

When your bot sends a message, clients receive a WebSocket notification:

```json
{
  "service": "messenger",
  "message": "new_message",
  "data": {
    "id": 12345,
    "rel_id_conversations": 789,
    "sender_rel_bot_id": 2,
    "message": "Your bot message content",
    "created_datetime": "2026-01-17 14:30:00"
  }
}
```

---

## FAQ

### Can I send messages to specific conversations?

Yes! Targeting is done through **bot assignment**. A bot only sends messages to conversations where it has been assigned. For granular control, create dedicated bots for specific conversations or channels.

### Can I send files or media?

File attachments are not yet supported via the Bot API. Only text messages are currently available.

### Is there a message size limit?

Messages should be kept under **10,000 characters**. Longer messages may be truncated.

### Can I read messages or conversation history?

No, the Bot API is **write-only**. Bots can send messages but cannot read conversation content.

### How do I format messages?

Basic markdown formatting is supported:
- `**bold**` for **bold**
- `*italic*` for *italic*
- `` `code` `` for `code`
- Code blocks with triple backticks

### Can multiple bots post to the same conversation?

Yes, you can assign multiple bots to a single conversation. Each bot uses its own token.

---

## Version Fran&ccedil;aise

<details>
<summary>Cliquez pour lire en fran&ccedil;ais</summary>

<div align="center">
  <img src="image/auroria_link_256.png" alt="Logo AuroriaLink" width="100"/>
  <h1>API Bot AuroriaLink</h1>
  <p><strong>Int&eacute;grez la messagerie automatis&eacute;e dans vos workflows</strong></p>
</div>

---

## Aper&ccedil;u

L'API Bot AuroriaLink permet aux applications tierces d'envoyer des messages automatis&eacute;s dans les conversations de groupe. Cela permet des int&eacute;grations puissantes :

- **Alertes de monitoring** - Envoyez des notifications syst&egrave;me &agrave; votre &eacute;quipe
- **Pipelines CI/CD** - Notifiez les statuts de build et d&eacute;ploiements
- **Rapports planifi&eacute;s** - Automatisez les mises &agrave; jour quotidiennes/hebdomadaires
- **Workflows n8n/Zapier** - Connectez AuroriaLink &agrave; des centaines de services
- **Applications personnalis&eacute;es** - Construisez vos propres int&eacute;grations

---

## D&eacute;marrage Rapide

### Pr&eacute;requis

1. Un compte AuroriaLink
2. Au moins une conversation de groupe o&ugrave; vous &ecirc;tes admin
3. Le token `key_access` de votre bot (obtenu via l'app)

### Envoyez votre premier message

```bash
curl -X POST "https://quantive-studio.xyz/app/bot_api.php?route=api_messenger" \
  -d "key_access=VOTRE_TOKEN_BOT" \
  -d "type_action=add_message" \
  -d "content_message=Bonjour depuis mon bot !"
```

---

## Workflow Complet

### &Eacute;tape 1 : Cr&eacute;er un Bot

Dans l'application AuroriaLink :

1. Allez dans **Param&egrave;tres** > **Gestion des Bots**
2. Cliquez sur **"Cr&eacute;er un nouveau bot"**
3. Remplissez les informations :
   - **Nom** : Nom d'affichage du bot
   - **Avatar** : URL de la photo de profil
   - **Description** : Ce que fait le bot
4. Cliquez sur **"Cr&eacute;er"**

**Important :** Le token `key_access` est affich&eacute; **une seule fois** &agrave; la cr&eacute;ation. Copiez-le et stockez-le en s&eacute;curit&eacute; !

### &Eacute;tape 2 : Affecter le Bot aux Conversations

1. Ouvrez une conversation de groupe o&ugrave; vous &ecirc;tes admin
2. Allez dans **Param&egrave;tres de conversation** > **Bots**
3. S&eacute;lectionnez votre bot dans la liste
4. Cliquez sur **"Ajouter le bot"**

### &Eacute;tape 3 : Envoyer des Messages via l'API

Faites une requ&ecirc;te POST vers l'endpoint de l'API Bot :

```bash
POST https://quantive-studio.xyz/app/bot_api.php?route=api_messenger
```

### &Eacute;tape 4 : Livraison en Temps R&eacute;el

Les messages sont livr&eacute;s instantan&eacute;ment &agrave; tous les clients connect&eacute;s via WebSocket.

---

## R&eacute;f&eacute;rence API

### Endpoint

```
POST https://quantive-studio.xyz/app/bot_api.php?route=api_messenger
```

### Param&egrave;tres de Requ&ecirc;te

| Param&egrave;tre | Type | Requis | Description |
|------------------|------|--------|-------------|
| `key_access` | string | **Oui** | Token d'authentification du bot |
| `type_action` | string | **Oui** | Action &agrave; effectuer : `add_message` |
| `content_message` | string | **Oui** | Contenu du message &agrave; envoyer |

### R&eacute;ponses

**Succ&egrave;s (HTTP 200) :**
```json
{"return_code": 0}
```

**Bot non affect&eacute; (HTTP 200) :**
```json
{"return_info": "your key access is not affected"}
```

**Limite de d&eacute;bit d&eacute;pass&eacute;e (HTTP 200) :**
```json
{"return_info": "Please respect the imposed usage limit of 10 requests per minute"}
```

**&Eacute;chec d'authentification (HTTP 404) :**
```
(r&eacute;ponse vide)
```

---

## S&eacute;curit&eacute;

### S&eacute;curit&eacute; des Tokens

- **Chiffr&eacute;s en transit** : Les tokens sont chiffr&eacute;s avec AES-256-GCM
- **HTTPS obligatoire** : Tous les appels API doivent utiliser HTTPS
- **Visibilit&eacute; unique** : Les tokens ne sont affich&eacute;s qu'une fois &agrave; la cr&eacute;ation
- **Pas d'expiration** : Les tokens n'expirent pas mais peuvent &ecirc;tre r&eacute;g&eacute;n&eacute;r&eacute;s

### R&eacute;g&eacute;n&eacute;rer un Token Compromis

1. Ouvrez l'application AuroriaLink
2. Allez dans **Param&egrave;tres** > **Gestion des Bots**
3. S&eacute;lectionnez votre bot
4. Cliquez sur **"R&eacute;g&eacute;n&eacute;rer le token"**

---

## Limitation de D&eacute;bit

| Limite | Valeur |
|--------|--------|
| Requ&ecirc;tes par token | **10 requ&ecirc;tes par 60 secondes** |
| Seuil de ban | **15 tentatives d'auth &eacute;chou&eacute;es** |
| Dur&eacute;e du ban | **10 minutes** |

---

## Gestion des Erreurs

| Sc&eacute;nario | Code HTTP | Corps de r&eacute;ponse | Action |
|-----------------|-----------|-------------------------|--------|
| Succ&egrave;s | 200 | `{"return_code": 0}` | Message envoy&eacute; |
| Bot non affect&eacute; | 200 | `{"return_info": "..."}` | Affecter le bot |
| Limite d&eacute;bit | 200 | `{"return_info": "..."}` | Attendre 60 sec |
| Token invalide | 404 | *(vide)* | V&eacute;rifier le token |

---

## Livraison en Temps R&eacute;el

Les messages envoy&eacute;s via l'API Bot sont livr&eacute;s en temps r&eacute;el &agrave; tous les clients connect&eacute;s :

```
API Bot ──▸ Backend PHP ──▸ Serveur WebSocket Node.js ──▸ Clients Connect&eacute;s
```

### Garanties de Livraison

| Fonctionnalit&eacute; | Description |
|-----------------------|-------------|
| **Livraison instantan&eacute;e** | Messages pouss&eacute;s via WebSocket en millisecondes |
| **Multi-device** | Livr&eacute; &agrave; tous les appareils connect&eacute;s (max 2 par user) |
| **Gestion hors ligne** | Messages stock&eacute;s et synchronis&eacute;s &agrave; la reconnexion |

---

## FAQ

### Puis-je envoyer des messages &agrave; des conversations sp&eacute;cifiques ?

Oui ! Le ciblage se fait via **l'affectation du bot**. Un bot n'envoie des messages qu'aux conversations o&ugrave; il a &eacute;t&eacute; affect&eacute;. Pour un contr&ocirc;le granulaire, cr&eacute;ez des bots d&eacute;di&eacute;s pour des conversations ou canaux sp&eacute;cifiques.

### Puis-je envoyer des fichiers ou m&eacute;dias ?

Les pi&egrave;ces jointes ne sont pas encore support&eacute;es via l'API Bot. Seuls les messages texte sont disponibles.

### Y a-t-il une limite de taille de message ?

Les messages doivent rester sous **10 000 caract&egrave;res**.

### Puis-je lire les messages ou l'historique ?

Non, l'API Bot est **en &eacute;criture seule**. Les bots peuvent envoyer mais pas lire.

</details>

---

<div align="center">
  <p><sub><strong>Guide version:</strong> 2026-01-17 | <strong>API version:</strong> 1.0</sub></p>
  <p><a href="README.md">← Back to main documentation</a></p>
</div>
