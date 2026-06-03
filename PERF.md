<div align="center">
  <img src="image/auroria_link_256.png" alt="AuroriaLink Logo" width="150"/>
  <h1>Performance & Real Cost</h1>
  <p><strong>Messaging benchmarks and shared infrastructure</strong></p>
  <p><sub>All numbers measured on production server on 2026-05-12</sub></p>
</div>

---

## Shared Infrastructure

AuroriaLink and Axomind run on the **same server** and share the same backend, database, WebSocket server, and cache layer. The full performance analysis — hardware specs, load tests, cost comparison, encryption at rest, and test coverage — is documented in the Axomind repository:

→ **[Full performance analysis → Axomind PERF.md](https://github.com/Sebastien-VZN/axomind/blob/main/PERF.md)**

The sections below cover what is specific to AuroriaLink: the messaging benchmarks.

---

## Messaging Benchmarks

### Messaging — 3,691 requests, 200 concurrent users in burst

| Metric | Value |
|---|---|
| Failures | 0 |
| Median (p50) | 109 ms |
| 95th percentile | 196 ms |
| 99th percentile | 240 ms |
| Total duration | 120 s |

CPU peaked around 80 % per core during the burst; memory and disk usage remained well within limits.

---

## Reproducibility and Observability

- The load tests are scripted and can be re-run on demand against the production server.
- Server health is monitored live (CPU, memory, cache hit rate).
- The codebase includes 847 automated tests (680 client-side + 167 server-side across 106 test files) and a CI/CD pipeline with format check, static analysis, unit tests, integration tests and multi-platform builds that run on every change, plus benchmark scripts for server-side load and DevTools-based profiling on the client side (CPU, GPU, memory).

> The cost is a realistic estimate based on the hardware's measured power draw; the latencies are what the load tests produced. Full details in the [Axomind PERF.md](https://github.com/Sebastien-VZN/axomind/blob/main/PERF.md).

---

## Version Française

<details>
<summary>Cliquez pour lire en français</summary>

---

<div align="center">
  <img src="image/auroria_link_256.png" alt="Logo AuroriaLink" width="150"/>
  <h1>Performance & Coût Réel</h1>
  <p><strong>Benchmarks messagerie et infrastructure partagée</strong></p>
  <p><sub>Tous les chiffres mesurés sur le serveur de production le 2026-05-12</sub></p>
</div>

---

## Infrastructure Partagée

AuroriaLink et Axomind tournent sur le **même serveur** et partagent le même backend, la même base de données, le même serveur WebSocket et la même couche de cache. L'analyse complète des performances — spécifications matériel, tests de charge, comparaison de coûts, chiffrement au repos et couverture de tests — est documentée dans le dépôt Axomind :

→ **[Analyse complète → PERF.md d'Axomind](https://github.com/Sebastien-VZN/axomind/blob/main/PERF.md)**

Les sections ci-dessous couvrent ce qui est spécifique à AuroriaLink : les benchmarks messagerie.

---

## Benchmarks Messagerie

### Messagerie — 3 691 requêtes, 200 utilisateurs simultanés en burst

| Métrique | Valeur |
|---|---|
| Échecs | 0 |
| Médiane (p50) | 109 ms |
| 95e percentile | 196 ms |
| 99e percentile | 240 ms |
| Durée totale | 120 s |

Le CPU a culminé à environ 80 % par cœur pendant le burst ; mémoire et disque sont restés largement sous leurs limites.

---

## Reproductibilité et Observabilité

- Les tests de charge sont scriptés et peuvent être rejoués à la demande contre le serveur de production.
- La santé du serveur est surveillée en direct (CPU, mémoire, taux de hit du cache).
- Le code embarque 847 tests automatisés (680 côté client + 167 côté serveur dans 106 fichiers de test) et un pipeline CI/CD avec vérification de format, analyse statique, tests unitaires, tests d'intégration et builds multi-plateforme qui tournent à chaque changement, plus des scripts de benchmark côté serveur et du profiling via DevTools côté client (CPU, GPU, mémoire).

> Le coût est une estimation réaliste basée sur la consommation électrique mesurée du matériel ; les latences sont les valeurs produites par les tests de charge. Détails complets dans le [PERF.md d'Axomind](https://github.com/Sebastien-VZN/axomind/blob/main/PERF.md).

</details>

---

**Last updated:** 2026-06-03