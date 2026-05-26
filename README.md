# 📱 LAB 10 – Guide d'installation de Frida

> **Auteur :** Mourad EL OUATIK  
> **Encadrant :** Dr. Mohamed LACHGAR  
> **Établissement :** ENSA Marrakech – Génie Cyber Défense et Systèmes de Télécommunications Embarquées  
> **Année :** 2025/2026

---

## Environnement

| Paramètre | Valeur |
|-----------|--------|
| **Système hôte** | Windows 11 Pro |
| **Android Studio** | Hedgehog 2023.1.1+ |
| **AVD utilisé** | Pixel XL – API 29 (Android 13) x86_64 |
| **Version Android** | 13.0 (API Level 29) |
| **Application de test** | DIVA Android (Damn Insecure Vulnerable App) |
| **Frida version** | 16.x |
| **frida-tools** | 12.x |
| **ADB version** | 1.0.41 |
| **Mode SELinux** | Permissive (durant les tests) |
| **Comptes personnels** | ✅ Aucun compte personnel utilisé |

---

## Étape 1 — Installation de Frida sur le poste de travail

<img width="949" height="290" alt="image" src="https://github.com/user-attachments/assets/7c0528cf-7297-4173-8258-9f99a49628e9" />

Vérification de l'installation :

<img width="934" height="179" alt="image" src="https://github.com/user-attachments/assets/f082ad85-08fb-4702-b2ad-feee1251471d" />

---

## Étape 2 — Téléchargement et déploiement du serveur Frida sur l'AVD

Identifier l'architecture de l'émulateur :

<img width="896" height="87" alt="image" src="https://github.com/user-attachments/assets/635b4105-3e73-441b-9b86-2080e4ac96a5" />

Télécharger le bon binaire `frida-server` depuis :  
`https://github.com/frida/frida/releases`  
→ choisir `frida-server-16.x.x-android-x86_64.xz`

Décompresser et pousser sur l'AVD :

<img width="528" height="90" alt="image" src="https://github.com/user-attachments/assets/a22e6980-73cf-4c4e-8ccc-91b5f07d68ad" />

---

## Étape 3 — Démarrage du serveur Frida sur l'AVD

Changement des droits d'accès :

<img width="945" height="44" alt="image" src="https://github.com/user-attachments/assets/f856c182-99af-471b-b44c-88978833078a" />

---

## Étape 4 — Test de connexion depuis le PC

Lister les processus visibles par Frida depuis le PC hôte :

<img width="945" height="250" alt="image" src="https://github.com/user-attachments/assets/42216ac7-4f0f-4b1f-aed0-e3e716a70f03" />

---

## Étape 5 — Injection minimale pour valider

### Test simple avec l'API Java

Créer le script `hello.js` :

<img width="945" height="61" alt="image" src="https://github.com/user-attachments/assets/35c75b97-8fe1-46a7-bade-360b2aabcc08" />

<img width="766" height="195" alt="image" src="https://github.com/user-attachments/assets/0962f87e-188c-42fa-be04-5f20244145d0" />

Exécution :

<img width="945" height="269" alt="image" src="https://github.com/user-attachments/assets/f64509a9-01ae-4f30-9a36-636bd7fc3296" />

### Test simple avec un hook natif

<img width="713" height="202" alt="image" src="https://github.com/user-attachments/assets/b395e370-7098-42c8-a902-f4a6af2083f6" />


Exécution :

<img width="945" height="368" alt="image" src="https://github.com/user-attachments/assets/fb5ce902-b7ed-40e5-ba8e-a790d7be2412" />


---

## Étape 6 — Explorer la console interactive Frida dans un contexte de sécurité

### Vérifier l'architecture du processus

<img width="845" height="144" alt="image" src="https://github.com/user-attachments/assets/d1141b2f-d54f-4fd6-8bf4-956059f89179" />


### Identifier le module principal de l'application

<img width="841" height="286" alt="image" src="https://github.com/user-attachments/assets/f5a891df-22d9-40dc-a749-5e6bdd9188a5" />

### Inspecter une bibliothèque système critique

<img width="839" height="220" alt="image" src="https://github.com/user-attachments/assets/fb90ae6f-d50b-4054-b831-c9e034fb06da" />

### Vérifier la présence d'une fonction sensible

<img width="839" height="85" alt="image" src="https://github.com/user-attachments/assets/c0df2bb5-bbfd-4ada-aa8b-7148b41f00e2" />

### Lister les bibliothèques chargées

<img width="733" height="597" alt="image" src="https://github.com/user-attachments/assets/b7349c22-5781-4e77-b1b9-3d11fd1daf11" />

### Lister les threads actifs

<img width="721" height="513" alt="image" src="https://github.com/user-attachments/assets/c93e7896-4ce2-44d5-b10b-43ae5e401fd0" />

### Examiner les plages mémoire du processus

<img width="654" height="473" alt="image" src="https://github.com/user-attachments/assets/d0d28ac6-1853-41a8-ae32-ec681433060f" />

### Vérifier si l'environnement Java est disponible

<img width="656" height="113" alt="image" src="https://github.com/user-attachments/assets/8a058324-894a-4d71-b36b-b217e7f7feaf" />

### Énumérer quelques classes Java chargées

<img width="684" height="292" alt="image" src="https://github.com/user-attachments/assets/47f50cb4-5268-4035-863f-b24144f8cc4f" />

### Vérifier la présence de bibliothèques liées au chiffrement ou au TLS

<img width="927" height="226" alt="image" src="https://github.com/user-attachments/assets/d8696725-6668-42f5-afe5-750fc47e1029" />

### Observer les accès réseau de manière pédagogique

<img width="945" height="347" alt="image" src="https://github.com/user-attachments/assets/eca29993-b2f9-4c81-acf3-dd8196e6de4f" />

### Vérifier les informations de base sur le processus

<img width="945" height="157" alt="image" src="https://github.com/user-attachments/assets/a180c91b-ed75-4e66-a931-9909daaf80d0" />

---

## Étape 7 — Observer les bibliothèques de chiffrement, le stockage local et les appels réseau sensibles

### Repérer les bibliothèques liées au chiffrement

<img width="733" height="656" alt="image" src="https://github.com/user-attachments/assets/36d33084-6156-48e8-9ae1-a07157d432c6" />

### Vérifier la présence d'une fonction réseau sensible

<img width="945" height="78" alt="image" src="https://github.com/user-attachments/assets/7fe9d9ad-9c3b-42c4-9dc0-cc11d82db046" />

### Installer un hook sur `connect`

<img width="945" height="374" alt="image" src="https://github.com/user-attachments/assets/8e35a17c-e319-4fe0-8289-47de4aa84308" />

### Installer un hook sur `send` et `recv`

<img width="720" height="330" alt="image" src="https://github.com/user-attachments/assets/4c570295-7e10-401f-bc65-15c0ca87268d" />

### Observer les accès au système de fichiers

<img width="727" height="350" alt="image" src="https://github.com/user-attachments/assets/a93ba9c9-bece-4207-ad2e-dd08652c6826" />

### Rechercher des classes Java liées au stockage ou à la sécurité

<img width="945" height="565" alt="image" src="https://github.com/user-attachments/assets/8dc2b317-4f11-4c1a-bb09-78a0896fc898" />

---

## Étape 8 — Hooker des méthodes Java liées à SharedPreferences, SQLite et aux vérifications de sécurité

### Observer l'utilisation de SharedPreferences

<img width="945" height="290" alt="image" src="https://github.com/user-attachments/assets/7a9a2e77-1a21-4ccb-b60e-a15271e927db" />

### Observer les requêtes SQLite

<img width="945" height="296" alt="image" src="https://github.com/user-attachments/assets/f50e3292-0b89-4b66-8745-ef48b7a3e308" />

### Observer certaines vérifications de débogage

<img width="945" height="265" alt="image" src="https://github.com/user-attachments/assets/f67d601f-b284-40e2-a81e-430b74750a44" />

---

## Checklist Finale

### ✅ Début de session

| Élément | Statut | Détail |
|---------|--------|--------|
| Périmètre écrit | ✅ | Analyse dynamique via Frida – hooking Java et natif |
| AVD neuf | ✅ | Pixel 6 API 33, créé pour ce lab |
| App test installée | ✅ | `adb install DIVA-Android.apk` |
| 3 scénarios notés | ✅ | Injection Frida / hooks réseau / hooks stockage |
| Versions notées | ✅ | Android 13 / Frida 16.x / DIVA v1.0 |

### ✅ Fin de session

| Élément | Statut | Preuve |
|---------|--------|--------|
| Données de test supprimées | ✅ | `adb shell pm clear com.target.app` → Success |
| Reset AVD (wipe) | ✅ | `emulator -wipe-data` → Successfully wiped |
| Preuve du reset | ✅ | Captures ci-dessous |
| Rapport + traçabilité | ✅ | Ce document archivé |
| Aucun compte personnel | ✅ | Confirmé |


*© Mourad EL OUATIK – ENSA Marrakech 2025/2026*
