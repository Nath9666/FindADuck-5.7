# 🦆 FindADuck - Chasse aux Canards en VR

## 📖 Description

**FindADuck** est un jeu de réalité virtuelle développé sur Unreal Engine 5.7 qui vous met au défi de trouver et capturer des canards en plastique cachés dans un environnement virtuel immersif. Armé de votre contrôleur VR et d'un système de lancer de rayons (raycast), vous devrez localiser tous les canards avant la fin du chronomètre !

### 🎮 Concept du Jeu

Plongez dans une salle de classe de chimie virtuelle où des canards en plastique sont disséminés. Utilisez vos contrôleurs VR pour pointer et interagir avec les canards grâce au système de raycast. Le temps est compté - trouvez tous les canards avant la fin du chronomètre pour remporter la victoire !

## ✨ Fonctionnalités Principales

- **🥽 Expérience VR Immersive** : Support complet OpenXR pour une compatibilité maximale avec les casques VR
- **🎯 Système de Raycast** : Pointez et cliquez sur les canards avec vos contrôleurs VR
- **⏱️ Chronomètre** : Course contre la montre pour trouver tous les canards
- **🏆 Écrans de Fin** : Écrans de victoire ou de défaite selon votre performance
- **🎨 Environnement Détaillé** : Explorez une salle de classe de chimie réaliste
- **👐 Hand Tracking** : Support du suivi des mains pour une immersion accrue

## 🛠️ Technologies Utilisées

- **Moteur** : Unreal Engine 5.7
- **Plateforme** : Réalité Virtuelle (VR)
- **Framework VR** : OpenXR
- **Langages** : Blueprints Visual Scripting

### Plugins Activés

- OpenXR
- OpenXR Eye Tracker
- OpenXR Hand Tracking
- OpenXR Vive Tracker
- OpenXR Microsoft Hand Interaction

## 🎯 Plateformes Supportées

- Windows
- Linux
- Android
- Mac
- iOS (Vision Pro)
- Consoles (PS4, PS5, Xbox One, Xbox Series X/S, Nintendo Switch)

## 📋 Prérequis

- **Unreal Engine 5.7** installé
- **Casque VR** compatible OpenXR (Meta Quest, HTC Vive, Valve Index, etc.)
- **Configuration minimale** :
  - Processeur : Intel Core i5-4590 / AMD Ryzen 5 1500X ou supérieur
  - Mémoire : 8 GB RAM minimum, 16 GB recommandés
  - Carte graphique : NVIDIA GTX 1060 / AMD Radeon RX 480 ou supérieur
  - Espace disque : 5 GB d'espace libre

## 🚀 Installation

### Cloner le Projet

```bash
git clone https://github.com/Nath9666/FindADuck-5.7.git
cd FindADuck-5.7
```

### Ouvrir dans Unreal Engine

1. Ouvrez l'**Epic Games Launcher**
2. Lancez **Unreal Engine 5.7**
3. Cliquez sur **"Browse"** et sélectionnez le fichier `FindADuck.uproject`
4. Le projet s'ouvrira automatiquement

### Configuration VR

Le projet est préconfiguré pour démarrer en VR (`bStartInVR=True`). Assurez-vous que :
- Votre casque VR est connecté et reconnu par votre système
- Les pilotes OpenXR sont installés
- Le runtime VR (SteamVR, Oculus, etc.) est en cours d'exécution

## 🎮 Comment Jouer

### Démarrage du Jeu

1. Dans l'éditeur Unreal, ouvrez la carte principale : `Content/VRTemplate/Maps/ChimistryClass.umap`
2. Cliquez sur **"VR Preview"** ou appuyez sur **Alt+P** pour lancer le jeu en mode VR
3. Mettez votre casque VR

### Commandes

- **Gâchette du contrôleur** : Tirer un rayon pour capturer un canard
- **Joystick/Trackpad** : Se déplacer dans l'environnement (si la téléportation est activée)
- **Bouton Grip** : Saisir des objets

### Objectif

- 🦆 **Trouvez tous les canards** en plastique cachés dans la salle de classe
- ⏱️ **Battez le chronomètre** avant la fin du temps imparti
- 🎯 **Utilisez le raycast** pour pointer et capturer les canards

### Fin de Partie

- **Victoire** : Si vous trouvez tous les canards avant la fin du temps, vous serez redirigé vers l'écran de victoire (`Finish.umap`)
- **Défaite** : Si le temps se termine avant que vous ayez trouvé tous les canards, vous verrez l'écran d'échec (`FinishFail.umap`)

## 📁 Structure du Projet

```
FindADuck-5.7/
├── Config/                      # Fichiers de configuration du projet
│   ├── DefaultEngine.ini
│   ├── DefaultGame.ini
│   └── DefaultInput.ini
├── Content/                     # Contenu du jeu
│   ├── Duck/                    # Assets des canards
│   │   ├── BP_PawnDuck.uasset  # Blueprint du canard
│   │   └── ricaS.uasset        # Modèle 3D du canard
│   ├── VRTemplate/             # Template VR principal
│   │   ├── Blueprints/         # Logique du jeu
│   │   │   ├── VRPawn.uasset   # Personnage VR du joueur
│   │   │   ├── VRGameMode.uasset
│   │   │   ├── Pistol.uasset   # Système de tir
│   │   │   └── Menu.uasset     # Interface menu
│   │   └── Maps/               # Niveaux du jeu
│   │       ├── ChimistryClass.umap  # Niveau principal
│   │       ├── Finish.umap          # Écran de victoire
│   │       └── FinishFail.umap      # Écran d'échec
│   ├── XRFramework/            # Framework XR
│   │   └── Blueprints/
│   │       └── Timer.uasset    # Système de chronomètre
│   ├── Characters/             # Personnages et animations
│   ├── Weapons/                # Système d'armes
│   └── StarterContent/         # Contenu de base Unreal
└── FindADuck.uproject          # Fichier projet principal
```

## 🔧 Développement

### Modifier le Temps de Jeu

1. Ouvrez `Content/XRFramework/Blueprints/Timer.uasset`
2. Modifiez la variable du temps limite
3. Sauvegardez et testez

### Ajouter des Canards

1. Ouvrez le niveau `ChimistryClass.umap`
2. Glissez-déposez `BP_PawnDuck` depuis le dossier `Content/Duck/`
3. Positionnez le canard dans l'environnement
4. Ajustez la rotation et l'échelle si nécessaire

### Personnaliser les Écrans de Fin

- Victoire : Éditez `Content/VRTemplate/Maps/Finish.umap`
- Défaite : Éditez `Content/VRTemplate/Maps/FinishFail.umap`

## 🤝 Contribution

Les contributions sont les bienvenues ! Si vous souhaitez améliorer le projet :

1. Forkez le projet
2. Créez une branche pour votre fonctionnalité (`git checkout -b feature/AmazingFeature`)
3. Committez vos changements (`git commit -m 'Add some AmazingFeature'`)
4. Poussez vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrez une Pull Request

## 🐛 Problèmes Connus

- Le projet nécessite Unreal Engine 5.7 exactement
- Certains casques VR peuvent nécessiter des ajustements spécifiques du runtime OpenXR

## 📝 Licence

Ce projet est un projet éducatif. Veuillez respecter les licences des assets utilisés.

## 👤 Auteur

**Nath9666**

- GitHub : [@Nath9666](https://github.com/Nath9666)

## 🙏 Remerciements

- Merci à Epic Games pour Unreal Engine
- Merci à la communauté OpenXR pour le support VR
- Assets StarterContent fournis par Epic Games

---

**Amusez-vous bien à chasser les canards ! 🦆🎮**
