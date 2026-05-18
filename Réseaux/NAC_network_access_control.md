---
Title : Ingénieur NAC
Date : 2025 - 07 -01
Duration : 5 months
---
# Open-Source NAC Lab : PacketFence & Samba4 AD

### **Objectif** 
- *La mise en place d'un **Contrôle d'Accès Réseau (NAC)** complet en environnement local*
  - *transformer un réseau domestique ou de laboratoire en un environnement **Zero Trust** : aucun appareil n'accède au réseau sans être authentifié et vérifié.*

###  **Réalisations**
L'implémentation de ce NAC repose sur une intégration verticale de trois couches technologiques majeures :

1. Architecture Identity-Aware (Samba4 AD)
  - Contrôleur de Domaine Open Source : Déploiement de Samba4 en mode AD DS pour gérer les identités (utilisateurs et ordinateurs) sans licence propriétaire.
  - Structuration de l'Annuaire : Mise en place d'Unités d'Organisation (OU) spécifiques pour permettre un mapping précis entre les groupes de sécurité et les rôles NAC (ex: GG_Finance -> VLAN_Compta).
  - Authentification Centralisée : Configuration du protocole LDAP pour permettre à PacketFence d'interroger la base d'utilisateurs en temps réel.

2. Orchestration & Contrôle (PacketFence)
  - Moteur RADIUS : Configuration de FreeRADIUS pour traiter les requêtes 802.1X (WPA2-Enterprise / Filaire).
  - Gestion des Profils (MAB) : Mise en œuvre du MAC Authentication Bypass pour les équipements ne supportant pas le 802.1X (imprimantes, caméras IP, terminaux IoT).
  - Portail Captif Dynamique : Création d'un workflow d'auto-enregistrement pour les invités avec isolation temporaire en VLAN de transition.

3. Segmentation & Enforcement (Switching)
  - VLAN Dynamiques : Configuration des switchs pour l'attribution de VLAN par assignation RADIUS (VLAN ID transmis dynamiquement après authentification).
  - SNMP & RADIUS CoA : Utilisation du Change of Authorization pour déconnecter ou changer le VLAN d'un utilisateur à la volée (ex: bascule immédiate en quarantaine après un scan négatif).
  - Sécurisation des Ports : Limitation du nombre d'adresses MAC par port et filtrage des trames pour prévenir les attaques de type "MAC Flooding".
    1. Mise en place d’une politique de sécurité pour le développement des sites web de don de sang (ISO 27001 & ISO 27002)
    2. Rédaction et implémentation d’une politique de sécurité conforme aux normes ISO.

###  **Résultats**
1. Visibilité et Contrôle Total
    -Inventaire en Temps Réel : Visibilité complète sur 100% des terminaux connectés (OS, Type de device, Utilisateur associé).
    -Zéro Accès Anonyme : Aucun équipement ne peut obtenir d'adresse IP fonctionnelle sans avoir franchi une étape d'authentification ou d'enregistrement préalable.
2. Sécurité et Conformité (Posturing)
  - Isolation Automatique : Réduction drastique du temps de réaction face à un terminal non conforme (antivirus désactivé) : passage en VLAN Quarantaine en moins de 2 secondes.
  - Segmentation Étanche : Isolation hermétique entre les flux "Invités" (Internet uniquement) et les flux "Production" (Accès aux ressources critiques).
3. Efficacité Opérationnelle
  - Self-Service Invité : Automatisation de l'accueil des visiteurs via le portail captif, supprimant la gestion manuelle des accès Wi-Fi temporaires.
  -Administration Agnostique : Gestion de la politique de sécurité depuis une interface unique, indépendamment de la marque ou du modèle du switch utilisé dans le parc  .
