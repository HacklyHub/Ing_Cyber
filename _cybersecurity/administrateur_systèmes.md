


---
Title : Administrateur systèmes - Ingénieur Réseaux - Consultant Cybersécurité - DevOps
Date : 2021 - 03 -15 à nos jours
Duration : à nos jours
---
# Projet Déploiement d’une Infrastructure Réseau Sécurisée Multi-services
## ENSA - Ecole nationale des Sciences Appliquées 
### **Objectif** 
- *Mettre en place une infrastructure réseau sécurisée et fonctionnelle.*
- *sécurité des communications*
- *la gestion centralisée des utilisateurs et la résilience des services*



###  **Réalisations**
1. Installation et configuration du DHCP.
     - attribuer une adresse IP au serveur
     - Mettre son adresse IP dans le nom de domaine server avec le nom de domaine etc..
     - Donner une plage d'adresses disponibles, default lease-time, max lease time, etc..
     - Configure les machines clientes 

2. Configuration d'un serveur DNS
     - crée une zone directe qui est de type master puis on crée la zone inverse qui commence par l’adresse inverse de l’adresse réseau
     - créeet configure des fichiers .rev et .zone
     - Configur les 10 types d’enregistrements DNS, comme A, AAAA, etc.,
3. Configuration des serveurs Microsoft IIS, Tomcat, Nginx, Apache, etc..
4. Configuration du serveur FTPS, SFTP et gestion des utilisateurs



###  **Résultats**
1. Clients reçoivent automatiquement une IP dans une plage définie.
2. Résolution DNS dynamique via mise à jour automatique.
3. DNSSEC pour signer les zones et éviter le spoofing, éviter les attaques de spoofing DHCP.
4. Résolution directe et inverse fonctionnelle dans tout le LAN.
5. Base DNS prête à intégrer d'autres services (IIS, Apache, messagerie, etc.).
6. Accès HTTPS aux serveurs web internes.
7. Services segmentés selon leur usage (public, admin, etc.).
8. Transferts chiffrés, utilisateurs cloisonnés, accès traçable.
9. Services accessibles de manière sécurisée via TLS/SSH.
