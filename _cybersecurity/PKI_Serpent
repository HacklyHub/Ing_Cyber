---
Title : Ingénieur Cybersécurité PKI - Developpeur
Date : 2026 - 02 -15
Duration : 2 months
---



# 🛡️ Mini-PKI & Messagerie Sécurisée E2EE (From Scratch)

Ce projet est une implémentation complète d'une **Infrastructure à Clés Publiques (PKI)** et d'un système de **messagerie client-serveur chiffré de bout en bout**, réalisé intégralement de zéro (**sans aucune librairie cryptographique externe**). 

Il a été développé pour comprendre en profondeur les mathématiques et la logique bas niveau des algorithmes de chiffrement.


### **Objectif** 
1. **Comprendre les entrailles de la cryptographie :** Ne pas utiliser de "boîtes noires" (API externes) mais coder les mathématiques sous-jacentes.
2. **Implémenter des algorithmes standards :** Développer RSA (Asymétrique) et SERPENT (Symétrique) en Python natif.
3. **Mettre en place une architecture de confiance :** Créer une Autorité de Certification (CA) capable de signer numériquement des certificats utilisateurs.
4. **Sécuriser des communications en temps réel :** Développer un chat Client-Serveur multi-threadé avec un chiffrement hybride (Génération de clés de session éphémères).

---

## Réalisations & Architecture

Le projet est divisé en deux composants principaux qui communiquent via des Sockets TCP/IP :

### 1. Le Serveur (L'Autorité & Le Routeur)
* **Autorité de Certification (CA) :** Possède sa propre paire de clés RSA. Signe les clés publiques des nouveaux utilisateurs avec sa clé privée pour créer des Certificats authentifiés.
* **Annuaire (Séquestre) :** Stocke les certificats valides des utilisateurs connectés.
* **Routage Aveugle :** Transfère les paquets chiffrés entre les clients sans jamais pouvoir en lire le contenu (Zero-Knowledge du contenu).

### 2. Le Client (L'Utilisateur)
* Génération locale de clés RSA (1024 bits).
* Demande d'authentification auprès du Serveur.
* Interface de chat asynchrone (Multi-threading).
* Chiffrement/Déchiffrement hybride transparent à la volée.

---

## Tâches Réalisées (Exhaustif)

### Cryptographie Asymétrique (RSA)
- [x] Implémentation du test de primalité probabiliste de Miller-Rabin.
- [x] Générateur de très grands nombres premiers (>= 512 bits).
- [x] Algorithme d'Euclide étendu et calcul de l'inverse modulaire.
- [x] Fonctions de chiffrement, déchiffrement, signature et vérification.

### Cryptographie Symétrique (SERPENT)
- [x] Implémentation de l'algorithme par blocs SERPENT (128 bits).
- [x] Génération des sous-clés (Key Schedule) avec le nombre d'Or.
- [x] Substitutions (S-Boxes) et permutations (Linear Transforms).
- [x] **Défi technique résolu :** Gestion du débordement d'entiers en Python (précision infinie) via un bitmasking strict (`& 0xFFFFFFFF`) pour simuler des registres 32 bits lors des décalages bit à bit.
- [x] Ajout d'un padding personnalisé pour gérer les messages de tailles variables.

### Infrastructure (PKI)
- [x] Création de la structure objet `Certificate` (Identité + Clé Publique + Signature du CA).
- [x] Sérialisation des objets via `pickle` pour le transit réseau.
- [x] Mécanisme de demande et de vérification d'authenticité des certificats par les pairs.

### Réseau & Application
- [x] Mise en place de Sockets TCP (Client/Serveur).
- [x] Gestion du multi-threading côté Client (écoute non bloquante `receive_loop`).
- [x] Gestion du multi-threading côté Serveur (gestion de N clients simultanés).

---

## 📈 Résultats et Compétences Acquises

* **Résultat technique :** Le système permet à deux terminaux distincts d'échanger des messages instantanés avec la certitude mathématique que le serveur relais ne peut pas les déchiffrer.
* **Maîtrise de Python :** Forte compréhension de la gestion de la mémoire, des types natifs, des opérations *bitwise* (`^`, `<<`, `>>`, `&`) et de l'asynchronisme basique (`threading`).
* **Cybersécurité :** Visualisation concrète des vulnérabilités liées au padding et de l'importance cruciale de la vérification des signatures (lutte contre les attaques *Man-in-the-Middle*).

---

## 🚀 Guide d'Installation et d'Utilisation

### Prérequis
Le projet n'utilise volontairement **aucune librairie cryptographique**. Seuls des modules d'aide à la structure de données sont requis.
