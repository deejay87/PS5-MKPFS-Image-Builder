# 🎮 PS5 MKPFS Image Builder (mkpfs 0.0.8)

![Windows](https://img.shields.io/badge/platform-Windows-blue?style=for-the-badge)
![PS5](https://img.shields.io/badge/platform-PS5-1F6FEB?style=for-the-badge)

Une interface graphique pour packager et compresser des dossiers de jeux, fichiers `.ffpkg` ou `.exfat` au format PFS (`.ffpfs` / `.ffpfsc`) pour la PS5.

Cette application regroupe toutes les fonctionnalités du cœur de l'outil [mkpfs](https://github.com/PSBrew/MkPFS) dans un exécutable portable et autonome.

---

## 📥 Téléchargement

1. Rendez-vous dans la section **[Releases](https://github.com/deejay87/PS5-MKPFS-Image-Builder/releases)** à droite de cette page.
2. Téléchargez la dernière version du fichier `PS5_MKPFS_IMAGE_BUILDER.exe`.
3. Lancez-le directement (aucune installation requise).

---

## 🚀 Fonctionnalités

- **Glisser-Déposer (Drag & Drop) :** Glissez simplement votre dossier de jeu, votre fichier `.ffpkg` ou `.exfat` directement sur la fenêtre, ou cliquez dessus pour charger vos fichiers manuellement.
- **Options de compression :**
  - Compresser les données (`--compress`)
  - Vérifier l'intégrité de l'image créée (`--verify`)
  - Ignorer la compression des exécutables pour accélérer le processus.
- **Dossier temporaire personnalisable :** Idéal si vous stockez vos jeux sur un NAS (réseau) ou si votre disque principal `C:` n'a pas assez d'espace libre pour les fichiers de travail.

---

## 📋 Mode d'emploi

1. Lancez l'exécutable.
2. Glissez votre dossier de jeu ou votre fichier .ffpkg ou .exfat source dans la zone grise (ou cliquez dessus pour parcourir vos fichiers).
3. *(Optionnel)* Cochez vos options et choisissez un dossier temporaire rapide si vous travaillez depuis un disque réseau ou lent.
4. Cliquez sur **⚡ GÉNÉRER L'IMAGE FFPFS**.
5. L'image finale sera créée automatiquement au même endroit que votre dossier source.

---

## 💡 Guide simple des options

### 1. La case "Compresser"

- **Option DÉCOCHÉE (Recommandé) :** Le jeu se crée en 2 secondes. Il fait la même taille que l'original, et les temps de chargement sur la PS5 seront ultra-rapides. (Extension `.ffpfs`).
- **Option COCHÉE :** Le jeu sera plus léger sur votre disque dur, mais la création va prendre beaucoup plus de temps. (Extension `.ffpfsc`).

---

### 2. La case "Ignorer exécutables"

- **🛡️ Laissez cette case cochée.** Elle empêche la compression des fichiers système du jeu. Si vous la décochez, votre jeu risque de faire un écran noir ou de planter au lancement sur la PS5.

---

### 3. Le "Dossier temporaire"

Le programme utilise un **dossier temporaire de travail** pour traiter les fichiers en toute sécurité.

- Par défaut : dossier temporaire Windows (`%TEMP%`)
- Optionnel : vous pouvez choisir un dossier sur un SSD rapide (ex: `D:\Temp`)

👉 Ce dossier sert à :

- copier les fichiers nécessaires au traitement
- accélérer les opérations de lecture/écriture
- éviter les lenteurs des disques réseau ou externes

✔️ Une fois le traitement terminé, les fichiers temporaires sont automatiquement supprimés.

---

## 📦 Option "Copier la source dans le dossier temporaire"

Cette option contrôle le comportement du traitement des fichiers :

#### ✔️ Case cochée (recommandé pour NAS / réseau)

- La source est entièrement copiée dans le dossier temporaire
- Le traitement se fait uniquement en local
- Plus stable et plus sécurisé

#### ❌ Case décochée (mode direct)

- Le programme lit directement depuis la source
- Plus rapide sur SSD local
- Utilise moins d’espace disque

---

### 4. Le "Dossier de sortie"

- Choisir l'emplacement ou le fichier `.ffpfsc` ou `.ffpfs` sera enregistré.

---

### 5. Choix de l'interface

- L’application est **multilingue**
- Les langues sont accessibles directement depuis l’interface

---

### Remarque sur la vitesse de conversion

L'analyse de votre antivirus peut réduire la vitesse de conversion, en particulier durant la phase d'écriture ou lors du traitement de nombreux fichiers individuels.

Vous pouvez désactiver temporairement la protection en temps réel de votre antivirus pour accélérer le processus. Si vous n'êtes pas sûr, laissez l'antivirus activé et attendez-vous à des conversions plus lentes.

### ⚡ Slider de puissance CPU (Performance)

Le logiciel inclut un **slider de gestion de la puissance CPU** permettant d’ajuster la priorité des ressources utilisées pendant le traitement.

---

### 📜 Fichier de log automatique

L’application génère automatiquement un **fichier de log** pendant chaque conversion.

---

## 📸 Screenshot
<img src="screenshots/PS5-MKPFS-Image-Builder.jpg" alt="Aperçu de l'application" width="600"/>

---

## ⚠️ Notes sur la Stabilité & Bonnes Pratiques

> [!IMPORTANT]
> **Le flux de travail `exfat ➜ ffpfsc` est la solution fortement recommandée et la plus stable à l'heure actuelle.**

Bien que la conversion directe à partir d'un **dossier de jeu brut (Raw folder)** soit entièrement supportée, elle est encore considérée comme expérimentale et peut rencontrer des limites ou des plantages lors de la gestion de :

- Backups de jeux de très grande taille.
- Dossiers contenant une quantité excessive de fichiers de petite taille (ce qui peut saturer les accès disque temporaires).

### 💡 Méthode Recommandée

Si vous rencontrez une erreur ou un plantage, veuillez d'abord monter ou encapsuler votre dossier de jeu dans une **image exFAT (`.exfat` ou `.img`)**, puis glissez-déposez ce fichier image dans l'application.

---

## 🛡️ Note importante concernant l'Antivirus (Faux Positifs)

Étant donné que cet exécutable est autonome (portable), **Windows Defender ou votre antivirus peut parfois le détecter comme une menace (faux positif).**

- Cliquez sur **"Informations complémentaires"**
- Puis **"Exécuter quand même"**
- Ou ajoutez le fichier en exclusion antivirus

---

## ⚖️ Crédits

- **Github source de MkPFS :** [MkPFS par l'équipe PSBrewnet](https://github.com/PSBrew/MkPFS)