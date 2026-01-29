# ☢️ NUKE WINTER

<div align="center">

![Nuke Winter Banner](Nuke-Winter-Front/public/assets/images-scene/banner.jpg)

![Angular](https://img.shields.io/badge/Angular-21-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-4.0.1-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![Java](https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![H2](https://img.shields.io/badge/H2-Database-0000BB?style=for-the-badge)

**Un escape game narratif en ligne dans un univers post-apocalyptique pixel art**

*Survivrez-vous à l'hiver nucléaire ?*

---

[Installation](#-installation) • [Comment Jouer](#-comment-jouer) • [Fonctionnalités](#-fonctionnalités) • [Technologies](#-technologies) • [API](#-api-endpoints)

</div>

---

## 📖 À Propos

**Nuke Winter** est un escape game narratif en ligne plongeant les joueurs dans un univers d'hiver nucléaire sombre et oppressant. Avec son esthétique **pixel art 16-bit** inspirée des classiques du genre, le jeu propose une expérience immersive où chaque choix compte.

Incarnez un survivant dans un monde dévasté, résolvez des énigmes, faites des choix difficiles et tentez de survivre face aux dangers qui vous guettent. Mais attention : **chaque mauvaise décision vous rapproche de la fin**.

### 🎮 Scénarios Disponibles

- **"Ne te retourne pas"** - Fuyez une créature mystérieuse dans les ruines d'une ville abandonnée
- **"Sur sa trace"** - Retrouvez un être cher disparu dans le chaos de l'apocalypse

---

## ✨ Fonctionnalités

### 🎯 Gameplay

| Fonctionnalité | Description |
|----------------|-------------|
| **Système de Santé** | Barre de vie dynamique - chaque mauvais choix inflige des dégâts |
| **Choix Multiples** | Prenez des décisions qui façonnent votre histoire |
| **Énigmes Variées** | QCM, codes à 4 chiffres, mots à deviner |
| **Fins Multiples** | Victoire héroïque, survie amère, ou mort tragique |
| **Sauvegarde Auto** | Reprenez votre partie où vous l'avez laissée |

### 🎨 Expérience

- **Pixel Art 16-bit** - Esthétique rétro soignée
- **Effets Parallax** - Arrière-plans à plusieurs couches
- **Effet Neige** - Particules animées pour l'ambiance
- **Effet Machine à Écrire** - Textes narratifs immersifs
- **Bande Son Atmosphérique** - Musique d'ambiance et effets sonores

### 👤 Personnalisation

- **5 Avatars Jouables** - Kurt, Sarah, Pedro, Michel, Crackhead
- **Import de Scénarios** - Créez et importez vos propres histoires au format JSON
- **Paramètres Audio** - Contrôle du volume musique et effets

---

## 🛠 Technologies

### Frontend - Angular 21

```
Nuke-Winter-Front/
├── src/app/
│   ├── pages/           # 8 pages (Start, Login, Menu, Game, etc.)
│   ├── components/      # 10 composants UI réutilisables
│   ├── core/
│   │   ├── services/    # Game, Audio, Account, Scenario...
│   │   └── models/      # Interfaces TypeScript
│   └── shared/          # Directives (parallax)
└── public/assets/       # Fonts, images, musiques, sons
```

**Stack :** Angular 21 • TypeScript 5.9 • RxJS 7.8 • SCSS • Vitest

### Backend - Spring Boot 4

```
Nuke-Winter-Back/
├── src/main/java/groupe1/nukewinter/
│   ├── controller/      # REST endpoints
│   ├── service/         # Logique métier
│   ├── domain/          # Entités JPA
│   ├── repository/      # Accès données
│   ├── DTO/             # Objets de transfert
│   └── adapter/         # Conversion JSON → Entités
└── uploads/             # Stockage images & audio
```

**Stack :** Spring Boot 4.0.1 • Java 21 • H2 Database • JPA/Hibernate • Maven

---

## 🚀 Installation

### Prérequis

- **Node.js** (npm 10.9+)
- **Java 21** ou supérieur
- **Maven 3.6+**

### 1. Cloner le projet

```bash
git clone https://github.com/votre-repo/nuke-winter.git
cd nuke-winter
```

### 2. Lancer le Backend

```bash
cd Nuke-Winter-Back

# Avec Maven Wrapper
./mvnw spring-boot:run

# Ou avec Maven installé
mvn spring-boot:run
```

Le serveur démarre sur `http://localhost:8080`

> 💡 Console H2 disponible : `http://localhost:8080/h2-console`

### 3. Lancer le Frontend

```bash
cd Nuke-Winter-Front

# Installer les dépendances
npm install

# Lancer le serveur de développement
npm start
```

L'application est accessible sur `http://localhost:4200`

### 4. Build Production

```bash
# Frontend
cd Nuke-Winter-Front
npm run build

# Backend
cd Nuke-Winter-Back
./mvnw clean package
java -jar target/nukewinter-0.0.1-SNAPSHOT.jar
```

---

## 🎮 Comment Jouer

1. **Créer un compte** - Entrez votre pseudo pour commencer
2. **Choisir un avatar** - Sélectionnez votre personnage
3. **Sélectionner un scénario** - Choisissez votre aventure
4. **Survivre** - Lisez attentivement, faites vos choix, résolvez les énigmes
5. **Gérer votre santé** - Évitez les mauvaises décisions qui drainent votre vie

### Types d'Énigmes

| Type | Description |
|------|-------------|
| `MULTICHOICE` | Choisissez parmi plusieurs réponses |
| `MATCH` | Devinez le mot exact |
| `CODE` | Entrez un code à 4 chiffres |

### Fin de Partie

- **SUCCEED** ✅ - Vous avez survécu et atteint la fin du scénario
- **FAILED** ❌ - Votre santé est tombée à zéro

---

## 📡 API Endpoints

### Authentification

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| `POST` | `/account/login` | Connexion par pseudo |
| `POST` | `/account/register` | Créer un compte |
| `GET` | `/account/me` | Récupérer le compte connecté |

### Jeu

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| `POST` | `/game/read-or-save` | Créer ou récupérer une partie |
| `POST` | `/game/calcul-response` | Soumettre une réponse |
| `POST` | `/game/{id}/give-up` | Abandonner la partie |
| `GET` | `/game/all` | Lister toutes les parties |

### Contenu

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| `GET` | `/scenario/all` | Lister les scénarios |
| `POST` | `/scenario/import` | Importer un scénario JSON |
| `GET` | `/avatar/all` | Lister les avatars |

### Médias

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| `POST` | `/api/images/upload` | Upload une image |
| `GET` | `/api/images/{filename}` | Télécharger une image |
| `POST` | `/api/audios/upload` | Upload un fichier audio |
| `GET` | `/api/audios/{filename}` | Télécharger un audio |

---

## 📁 Structure des Scénarios

Les scénarios sont définis en JSON et peuvent être importés dans le jeu :

```json
{
  "name": "Mon Scénario",
  "description": "Une aventure terrifiante...",
  "author": "VotreNom",
  "version": "1.0",
  "background": "scenario-bg.png",
  "firstScene": "scene1",
  "scenes": [
    {
      "idScene": "scene1",
      "description": "Vous vous réveillez dans une pièce sombre...",
      "question": "Que faites-vous ?",
      "typeScene": "MULTICHOICE",
      "background": "dark-room.png",
      "audio": "ambiance.mp3",
      "responses": [
        {
          "idResponse": "r1",
          "name": "Explorer la pièce",
          "nextScene": "scene2",
          "damage": 0
        },
        {
          "idResponse": "r2",
          "name": "Crier à l'aide",
          "nextScene": "scene3",
          "damage": 20
        }
      ]
    }
  ]
}
```

---

## 🎨 Assets

### Polices
- **Pixellari** - Police pixel rétro pour l'UI
- **Demon-Flowing** - Police décorative pour les titres

### Sons
- `main-ambiance.mp3` - Musique de fond atmosphérique
- `beep.mp3` - Son du clavier numérique
- `click.mp3` - Clic sur les boutons
- `error.mp3` - Mauvaise réponse
- `open.mp3` - Bonne réponse / porte ouverte

---

## 🧪 Tests

```bash
# Tests Frontend (Vitest)
cd Nuke-Winter-Front
npm test

# Tests Backend (JUnit)
cd Nuke-Winter-Back
./mvnw test
```

---

## 📝 Configuration

### Variables d'Environnement Frontend

Fichier : `src/environments/environment.ts`

```typescript
export const environment = {
  apiUrl: 'http://localhost:8080',
  imageApiUrl: 'http://localhost:8080/api/images/',
  audioApiUrl: 'http://localhost:8080/api/audios/'
};
```

### Configuration Backend

Fichier : `src/main/resources/application.properties`

```properties
spring.application.name=nukewinter
spring.h2.console.enabled=true
spring.datasource.url=jdbc:h2:mem:testdb
spring.servlet.multipart.max-file-size=50MB
```
---

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

---

<div align="center">

**☢️ Survivrez-vous à l'hiver nucléaire ? ☢️**

*Made with 💚 and fear*

</div>
