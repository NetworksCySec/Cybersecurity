# 🧠 Projet cybersécurité – ConnectHub

Bienvenue dans ce dossier consacré à **ConnectHub**, un projet complet de développement sécurisé mené en collaboration avec **2PLTS**, autour de la création d’un environnement numérique professionnel, interactif et résilient.

Ce projet visait à sécuriser l’ensemble de la chaîne de production : architecture applicative, infrastructure système, données, livraison, et gestion des accès.

---

## 🧩 Objectif du projet

**ConnectHub** est une plateforme web dédiée au partage d’articles, de projets, et à la mise en relation entre utilisateurs autour de thématiques professionnelles ou académiques.

L’ensemble du développement a été accompagné d’une démarche sécurité rigoureuse :

- Implémentation de bonnes pratiques de développement sécurisé
- Sécurisation de l’infrastructure Linux (lockdown)
- Mise en place de politiques de chiffrement et de livraison sécurisée
- Audit, durcissement, et tests de pénétration

---

## 🛠️ Fonctionnalités principales

| Composant | Détails |
|----------|---------|
| 🧑‍💻 Authentification | Système avec **MFA**, vérification par email |
| 📚 Publication de contenu | Articles publics, privés ou ciblés par groupe |
| 🌍 Données interactives | Visualisation de masters par région via carte + diagrammes |
| 🔍 Recherche avancée | Écoles filtrées par ville, région, accessibilité, coût de la vie |
| 💬 Chat en ligne | Contact direct entre utilisateurs et institutions |
| 🛡️ Interface admin | Publication de contenus et annonces officielles |

---

## 🔐 Cybersécurité : composante centrale

### 🔹 Verrouillage système (lockdown)

- Vérification complète des VM : ressources, performances, logs
- Nettoyage des données sensibles et désinstallation des outils non critiques
- **Transmission sécurisée** : ZIP chiffré, mot de passe via canal distinct (Privnote)
- Contrôle d’intégrité : SHA256, instructions de vérification incluses

> Une version PGP plus sécurisée était envisagée, avec chiffrement asymétrique + signature

### 🔹 Sécurité système

- 🔄 Mises à jour automatiques via `unattended-upgrades`
- 🔥 Pare-feu UFW configuré strictement (ports web + SSH custom)
- 🧑‍🔧 Droits sudo restreints + journalisation avancée (`/var/log/sudo.log`)
- 🔒 Connexion SSH par clés RSA uniquement (port déplacé 6969)
- 🚫 Fermeture des ports non nécessaires (IPP/CUPS, etc.)
- 🛡️ Fail2Ban et HTTPS auto-signé activés

### 🔹 Sécurité applicative

- 🔍 Tests d’injection SQL, XSS, session hijack
- 🧪 Fonctions sécurisées : `prepare()`, `htmlspecialchars()`, `password_hash()` et `verify()`
- ✅ Validation des entrées (`filter_input`), contrôle des champs obligatoires
- 🗂️ Sécurisation des formulaires (connexion, contact, déconnexion…)

---

## 🧬 Stack technique

| Élément      | Technologie |
|--------------|-------------|
| Frontend     | React.js    |
| Backend      | Django      |
| Base de données | PostgreSQL |
| Tests sécu   | OWASP ZAP, SonarQube, Nessus, SQLMap, BurpSuite |
| Supervision  | Nagios, Grafana, ELK Stack, Wazuh |
| Déploiement  | VM Linux + SSH + UFW + Fail2Ban |

---

## 👥 Équipe technique (2PLTS)

- **Kilian** – Exper Cyber & réponse à incident  
- **Gaëtan** – Pentest & sécurité applicative  
- **Étienne** – Gouvernance et architecture sécurité  
- **Safa** – DevOps, CI/CD & automatisation  
- **Corentin** – Administration systèmes & virtualisation

---

## 🧾 Notes complémentaires

- Tous les tests de sécurité ont été documentés (logs, hash, captures).
- Le serveur a été livré via une VM préconfigurée, **accompagnée d’un hash SHA256 et d’un chiffrement ZIP**, mot de passe transmis de manière séparée.
- Le projet aurait pu bénéficier d’un **chiffrement PGP complet**, mais a été adapté à la réalité du contexte de livraison.

---
<!-- Hashtags pour référencement -->
#Cybersecurity #DevSecOps #SecureDevelopment #Authentication #AccessControl #Lockdown #OWASP #MFA #Encryption #DeliverySecurity
