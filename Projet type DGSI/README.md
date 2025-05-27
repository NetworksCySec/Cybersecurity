# 🛡️ Projet cybersécurité – Infrastructure sécurisée type DGSI

Ce dépôt présente le projet de mise en place d’un **système d’information sécurisé**, réparti sur deux sites, destiné à des équipes de développement au sein d’une entité sensible. Le projet a été mené par **2PLTS**, société spécialisée en cybersécurité, et couvre la conception, la sécurisation et la résilience d’une infrastructure complète.

---

## 🧩 Objectifs et contexte

Le projet consiste à concevoir une **infrastructure informatique performante, évolutive et hautement sécurisée**, répondant aux exigences opérationnelles de deux équipes de développeurs. Les priorités fixées étaient :

- Sécurité des données sensibles
- Haute disponibilité des services
- Résilience face aux menaces internes et externes
- Respect des bonnes pratiques de cybersécurité (CIS, EBIOS, OWASP…)

---

## 🧱 Architecture mise en place

- Hyperviseurs Hyper-V de type 1 pour l’isolation et la scalabilité
- Infrastructure virtualisée (70+ VMs), répartie sur 5 serveurs physiques Dell R750
- Réseau redondé avec segmentation stricte (VLAN, HSRP, LACP)
- Services critiques séparés sur des sous-forêts AD (IGDLA)
- Infrastructure en haute disponibilité (switchs, firewalls, proxies…)

---

## 🔐 Composantes cybersécurité clés

### 🔹 Authentification & contrôle d’accès
- Active Directory (modèle IGDLA)
- SSO avec Keycloak, lié à l’AD
- Gestion centralisée des habilitations applicatives
- Accès restreint par rôles et auditables

### 🔹 Sécurisation applicative & réseau
- Proxy filtrant (Squid), Reverse Proxy (HAProxy)
- Firewall Fortinet (FortiGate + VPN IPSec)
- Répartition de charge, anonymisation, cache, whitelisting
- Séparation des flux DEV/PROD/RECETTE

### 🔹 Chiffrement & cryptographie
- Bitlocker sur postes Windows
- LUKS + Hashicorp Vault sur serveurs Linux
- OpenSSL (PKI interne), certificats TLS pour tous les services
- Interdiction des clés codées en dur, isolation des clés secondaires

### 🔹 Hardening systèmes & supervision
- CIS Benchmark, Tripwire, désactivation services inutiles
- Wazuh (EDR + antivirus), Graylog (SIEM), OpenVAS (scans vulnérabilités)
- Supervision complète via Zabbix + alertes automatisées
- Audit régulier (pingcastle, analyse logs, CVSS, Metasploit)

---

## 🔄 Résilience et sauvegarde

- Stratégie **3-2-1** : sauvegardes locales + NAS distant
- Acronis CyberProtect (On-prem + Cloud, snapshot + forensic)
- PRA/PCA documentés et testés
- Virtualisation + duplication des services critiques

---

## 🧪 DevSecOps & CI/CD

- **GitLab** pour gestion du code source
- **Jenkins** pour pipelines CI
- **Ansible** pour déploiement sécurisé (CD)
- **SonarQube + SonarLint** pour inspection continue du code

---

## 🧬 Stack technique

| Élément         | Technologies principales                                               |
|----------------|------------------------------------------------------------------------|
| Hyperviseur     | Hyper-V                                                               |
| Authentification | AD + Keycloak                                                        |
| Systèmes        | Windows Server, Debian                                                |
| Supervision     | Zabbix, Wazuh, Graylog                                                |
| Audit           | OpenVAS, Pingcastle, Tripwire                                         |
| CI/CD           | GitLab, Jenkins, Ansible                                              |
| Inventaire      | GLPI                                                                  |
| Partage fichier | FreeNAS                                                               |
| Reverse proxy   | HAProxy                                                               |
| Proxy filtrant  | Squid                                                                 |
| EDR/AV          | Wazuh                                                                 |
| Chiffrement     | Bitlocker, LUKS, Hashicorp Vault, OpenSSL                             |

---

## 🧑‍💻 Équipe projet – 2PLTS

- **Kilian** – Expert Cyber & Hardening
- **Corentin** – Expert virtualisation & infrastructure système  
- **Étienne** – Expert sécurité réseau & architecture  
- **Gaëtan** – Analyste sécurité réseau & firewall  
- **Safa** – DevOps & automatisation de déploiement  

---
<!-- Hashtags pour référencement -->
#Cybersecurity #InfrastructureSecurity #ActiveDirectory #Vault #Hardening #SIEM #Wazuh #Zabbix #Resilience #PRA #CI_CD #Firewall #ThreatDetection
