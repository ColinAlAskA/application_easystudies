# EasyStudies

Application mobile de suivi scolaire développée avec Flutter pour l'association
EasyStudies.

Projet réalisé dans le cadre du stage de première année à l'ENSIIE par :

- **Colin Coërchon**
- **Adam Ouzegdouh**

Maître de stage : **Atchuthan Mahendravasa**.

## Présentation

EasyStudies permet aux élèves et aux professeurs de consulter et de gérer les
informations liées au suivi scolaire : devoirs, notes, bilans, commentaires,
présences, paiements et cours.

L'application comprend également une authentification, un thème sombre, un
accueil avec des vidéos YouTube et un Easter egg.

<table>
    <tr>
        <td><img src="https://github.com/user-attachments/assets/210f6ef3-9166-4f58-8907-0b116a94b628" alt="Page d'accueil" width="320"></td>
        <td><img src="https://github.com/user-attachments/assets/cd378637-087d-482c-bf82-fffe8ef08d2f" alt="Détails d'un élève" width="320"></td>
    </tr>
    <tr>
        <td align="center">Page d'accueil</td>
        <td align="center">Détails d'un élève</td>
    </tr>
</table>

## Fonctionnalités

- **Élève** : consultation des devoirs, notes, bilans, commentaires, présences,
  paiements et profil ; affichage d'un QR code personnel.
- **Professeur** : gestion des élèves, devoirs, notes, bilans, commentaires,
  cours et présences ; scan des QR codes élèves.
- **Application** : authentification persistante, thème clair ou sombre,
  vidéos YouTube et Easter egg.

## Architecture du projet

Le point d'entrée est `lib/main.dart`. L'application utilise `Provider` pour
gérer l'authentification (`AuthState`) et le thème (`ThemeProvider`).

```text
lib/
├── main.dart                         # Initialisation, thèmes et routes
├── utils.dart                         # Modèles métier et appels API
├── logs/
│   └── auth_stat.dart                 # Authentification et session
├── utilities/
│   ├── constantes.dart                # Constantes communes
│   ├── facebook_news.dart             # Service Facebook
│   ├── theme_provider.dart            # Gestion du thème
│   └── video_youtube.dart              # Service YouTube
└── screens/
    ├── splash_screen.dart             # Écran de démarrage
    ├── login_screen.dart              # Connexion
    ├── app_bar.dart                   # Barre supérieure
    ├── body.dart                      # Accueil
    ├── eleve_screen.dart              # Espace élève
    ├── prof_screen.dart               # Espace professeur
    ├── super_user_screen.dart         # Espace super utilisateur
    ├── action_buttons_eleve/          # Fonctionnalités élève
    ├── action_buttons_prof/           # Fonctionnalités professeur
    └── boutons_app_bar/               # Profil et historiques
```

### Arborescence de `lib`

<img width="320" alt="Arborescence du dossier lib" src="https://github.com/user-attachments/assets/c766b22c-91b7-4f26-845b-e39485abd6c4" />

### Diagramme de classes

Le diagramme de classes complet de l'application part de la classe principale
`Eleve` et présente les classes utilisées pour les devoirs, notes, bilans,
présences, paiements et cours.

<img width="800" alt="Diagramme de classes de l'application" src="https://github.com/user-attachments/assets/3f913bde-793c-497a-81ee-3459f7d87c32" />

## Données et API

Les modèles et les appels HTTP sont regroupés dans `lib/utils.dart`. Les
principaux modèles sont `Eleve`, `Devoir`, `Commentaire`, `Note`, `Bilan`,
`Course`, `Presence` et `Paiement`.

L'application utilise l'API EasyStudies : `https://app.easystudies.fr/api/`. Ces API ont été développées par notre maître de stage **Atchuthan
Mahendravasa**.

## Installation et lancement

### Prérequis

- Flutter installé ;
- Android Studio et un émulateur ou un appareil Android ;
- Dart SDK `>= 3.0.3 < 4.0.0`.

Depuis le dossier du projet :

```bash
flutter pub get
flutter run
```

## Génération de l'application Android

Pour générer un APK :

```bash
flutter build apk
```

Pour générer un App Bundle destiné au Google Play Store :

```bash
flutter build appbundle
```
