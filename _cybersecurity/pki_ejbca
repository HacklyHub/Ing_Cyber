---
Title : Ingénieur PKI
Date : 2025 - 03 -02
Duration : 5 months
---
# Projet : Architecture et Déploiement d'une PKI "Two-Tier" d'Entreprise

### **Objectif** 
- *Simuler un environnement de confiance d'entreprise (Enterprise Trust)*
  - *en déployant une Infrastructure à Clés Publiques (PKI) complète à deux niveaux*
  - *en respectant les standards de sécurité de l'industrie (séparation Root/Issuing, publication CRL/OCSP) avec des solutions exclusivement open source.*


**Type :** Laboratoire d'Architecture Sécurité (Homelab)  
**Statut :** Achevé  


## Tâches et Implémentation
* **Design de l'Architecture (Two-Tier Hierarchy) :**
  * **Tier 1 (Root CA) :** Déploiement d'une Autorité Racine basée sur `OpenSSL` fonctionnant sur une machine virtuelle Linux isolée du réseau (Air-gapped / Offline).
  * **Tier 2 (Issuing CA) :** Déploiement de **EJBCA Community Edition** (Standard industriel) sur un conteneur Docker/VM en ligne pour l'émission quotidienne des certificats.
* **Cérémonie des Clés (Simulée) :**
  * Rédaction d'un script de cérémonie (Checklist) pour la création de la paire de clés Racine et la signature de la requête (CSR) de l'Issuing CA, suivie de la mise hors tension de la Root CA.
* **Gouvernance et Procédures (CP/CPS) :**
  * Rédaction d'une mini Déclaration des Pratiques de Certification (DPC / CPS) en format Markdown expliquant les règles d'émission, de renouvellement et de révocation dans ce laboratoire.
* **Haute Disponibilité des Informations (CDP/AIA) :**
  * Configuration d'un serveur web Apache léger dédié à la publication de la Liste de Révocation des Certificats (CRL).
  * Activation et test du répondeur **OCSP** intégré à EJBCA pour la validation des certificats en temps réel.
* **Cas d'usage (Tests clients) :**
  * Génération de certificats clients (Client Authentication) pour simuler la connexion sécurisée d'un utilisateur à un service interne (VPN OpenVPN ou mTLS sur un serveur web).

## Réalisations Techniques
* Intégration réussie entre une Racine construite manuellement (OpenSSL) et une autorité émettrice industrielle (EJBCA).
* Démonstration d'une révocation réussie : révocation d'un certificat client depuis l'interface EJBCA, mise à jour de la CRL, et vérification du rejet de la connexion par le serveur web cible.
* Documentation complète de l'architecture "As Code" et des procédures de recouvrement.

## 📈 Résultats et Impact
* Assimilation profonde des concepts de chaîne de confiance (Chain of Trust) et de l'importance de la protection physique des clés racines.
* Démontre la capacité à lire des RFC et à concevoir une architecture PKI complexe sans dépendre d'assistants graphiques (GUI).

## Environnement Technique (100% Open Source)
* **PKI Software :** EJBCA Community Edition, OpenSSL CA.
* **Serveurs & Déploiement :** Docker, Linux Alpine / Ubuntu, Apache Web Server (pour la CRL).
* **Protocoles :** X.509, OCSP, LDAP/HTTP (pour CDP).
