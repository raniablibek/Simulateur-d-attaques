# 🔐 Cyber Attack Simulator

Une suite interactive et pédagogique de simulateurs pour explorer les attaques cyber courantes : **DoS**, **DDoS** et **Phishing**.

> **⚠️ Important :** Tous les simulations sont locales et éducatives. Aucun trafic réseau réel n'est généré.

## 📋 Table des matières

- [Vue d'ensemble](#vue-densemble)
- [Simulateurs](#simulateurs)
  - [DoS](#dos--denial-of-service)
  - [DDoS](#ddos--distributed-denial-of-service)
  - [Phishing](#phishing)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [À propos](#à-propos)

## 🎯 Vue d'ensemble

Ce projet offre une plateforme interactive pour comprendre les mécanismes des cyberattaques courantes. Chaque simulateur permet d'ajuster des paramètres en temps réel et d'observer les effets sur le système cible.

### Caractéristiques principales

- 🎨 **Interface interactive** avec visualisations en temps réel
- 📊 **Graphiques dynamiques** montrant l'évolution des attaques
- 🎮 **Paramètres ajustables** pour explorer différents scénarios
- 🔴 **Alertes en direct** pour observer les seuils critiques
- 📱 **Responsive** - fonctionne sur desktop et mobile

## 🛡️ Simulateurs

### DoS → Denial of Service

Un **DoS (Denial of Service)** désigne une attaque lancée par une seule source qui vise à surcharger un serveur avec des requêtes massives.

#### Paramètres contrôlables

| Paramètre | Description |
|-----------|-------------|
| **Intensity** | Nombre de requêtes par seconde envoyées par l'attaquant |
| **Capacity** | Capacité maximale du serveur à traiter les requêtes |
| **Defense** | Pourcentage de requêtes bloquées par les systèmes de sécurité |

#### Métriques affichées

- 📨 **Requêtes totales** : Nombre cumulé de requêtes reçues
- 🚫 **Bloquées** : Nombre de requêtes filtrées
- 🟢 **Statut** : État du serveur (UP/RISK/DOWN)

#### Seuils d'alerte

- 🟡 **70% de charge** : Avertissement - le serveur devient instable
- 🔴 **90% de charge** : Danger critique - risque d'indisponibilité imminente

---

### DDoS → Distributed Denial of Service

Un **DDoS (Distributed Denial of Service)** utilise un réseau de machines compromises (botnet) pour lancer une attaque distribuée multiples sources.

#### Paramètres contrôlables

| Paramètre | Description |
|-----------|-------------|
| **Bots** | Nombre de machines compromises dans le botnet |
| **Per bot** | Requêtes par seconde envoyées par chaque bot |
| **Capacity** | Capacité maximale du serveur |
| **Defense** | Pourcentage du trafic malveillant bloqué |

#### Métriques affichées

- 🌐 **Trafic** : Requêtes valides par seconde
- 🤖 **Bots** : Nombre total de bots actifs
- 🗺️ **Sources** : Nombre de sources géographiques distinctes

#### Visualisation

- 🎯 Carte animée montrant la distribution des attaques par région
- 📈 Graphique en temps réel du trafic réseau
- 💀 Animation montrant les paquets du botnet vers le serveur

---

### Phishing

La simulation **Phishing** reproduit une attaque d'ingénierie sociale par email pour sensibiliser aux menaces.

#### Métriques

- 📧 **Emails reçus** : Nombre d'emails phishing simulés
- 🖱️ **Clics** : Nombre d'utilisateurs ayant cliqué sur les liens
- 🚨 **Alertes** : Détections de sécurité déclenchées

#### Scénarios simulés

- Emails de faux domaines bancaires et de services populaires
- Variété de sujets d'urgence pour augmenter les taux de clics
- Simulation de soumissions de credentials
- Détection automatique par règles de sécurité (SPF, signatures phishing)

#### Types d'événements

| Type | Description |
|------|-------------|
| **Email reçu** | Email phishing simulé reçu |
| **Clic utilisateur** | Utilisateur a cliqué sur le lien malveillant |
| **Submission credentials** | Identifiants ont été saisis (simulé) |
| **Alerte détection** | Système de sécurité a bloqué/alerté |

---

## 💻 Installation

### Prérequis

- Un navigateur web moderne (Chrome, Firefox, Safari, Edge)
- Aucune installation serveur requise

### Démarrage rapide

1. **Cloner ou télécharger le projet**
   \`\`\`bash
   git clone <repository-url>
   cd cyber-attack-simulator
   \`\`\`

2. **Servir les fichiers localement** (optionnel mais recommandé)
   \`\`\`bash
   # Avec Python 3
   python -m http.server 8000
   
   # Ou avec Node.js/http-server
   npx http-server
   \`\`\`

3. **Accéder à l'application**
   - Ouvrir `index.html` directement dans le navigateur, ou
   - Visiter `http://localhost:8000` si serveur local

## 🎮 Utilisation

### Navigation

1. **Page d'accueil** - Choisir un simulateur via les gros boutons
2. **Sélecteur latéral** - Basculer entre DoS, DDoS et Phishing
3. **Guide d'utilisation** - Accessible via le bouton "📖 Guide"

### Workflow typique

1. **Sélectionner un simulateur**
2. **Ajuster les paramètres** avec les sliders
3. **Lancer la simulation** (activée par défaut)
4. **Observer les métriques et graphiques** en temps réel
5. **Modifier les paramètres** pour tester différents scénarios
6. **Réinitialiser** pour recommencer

### Exemple : Tester la défense DoS

\`\`\`
1. Réduire "Intensity" à 50
2. Augmenter "Defense" à 80%
3. Observer : Le serveur reste stable malgré l'attaque
4. Augmenter progressivement "Intensity" à 200
5. Observer : Les défenses sont submergées
\`\`\`

## 📁 Structure du projet

\`\`\`
cyber-attack-simulator/
├── index.html              # Page HTML principale
├── style.css               # Styles globaux
├── portal-main.js          # Logique de navigation
├── sim-dos.js              # Simulateur DoS
├── sim-ddos.js             # Simulateur DDoS
├── sim_phishing.js         # Simulateur Phishing
└── images/                 # Images et assets
    ├── phishing-optimized.jpg
    ├── ddos2.webp
    ├── arriereplan.jpg
    └── ...
\`\`\`

### Détails des fichiers

| Fichier | Rôle |
|---------|------|
| `index.html` | Structure HTML avec sections DoS, DDoS, Phishing |
| `style.css` | Thème sombre cybersécurité, animations, responsive |
| `portal-main.js` | Gestion de la navigation et des modales |
| `sim-dos.js` | Animation et simulation du DoS |
| `sim-ddos.js` | Animation et simulation du DDoS |
| `sim_phishing.js` | Web Component Phishing avec logique d'événements |

## 🔧 Technologies utilisées

- **HTML5** - Structure sémantique
- **CSS3** - Design moderne avec gradients et animations
- **JavaScript (Vanilla)** - Logique de simulation et animations Canvas
- **Web Components** - Isolation du simulateur Phishing (Shadow DOM)
- **Canvas API** - Visualisations graphiques temps réel

## 📊 Algorithmes clés

### DoS Simulation
- Calcul dynamique du taux de blocage basé sur la défense
- Graphique glissant 60-points de la charge serveur
- Warbugs d'alerte aux seuils 70% et 90%

### DDoS Simulation
- Distribution de sources géographiques simulées (5 régions)
- Variation aléatoire du trafic par bot
- Visualisation par carte avec cercles radiatifs

### Phishing Simulation
- Génération aléatoire d'emails avec domaines/sujets réalistes
- Taux de clics et submission credentials configurable
- Détection multi-règles (SPF, signatures phishing)

## 🎓 À propos

### Équipe

Projet développé par les étudiants du **Master Cybersécurité** de l'**Université Paris Cité** :

- 👤 **Rania Blibek**
- 👤 **Lounas Ben Medjeber**
- 👤 **Yanis Merabet**
- 👤 **Zahem Yasmine**
- 👤 **Silakhel Imane**

### Objectifs pédagogiques

- ✅ Comprendre les mécanismes des attaques DoS/DDoS
- ✅ Sensibiliser aux menaces de phishing
- ✅ Étudier l'impact des paramètres sur les attaques
- ✅ Visualiser les défenses en action
- ✅ Contextualiser les concepts de cybersécurité

### Avertissements

- 🔒 **Légal** : Ce projet est purement éducatif
- ⚠️ **Sécurité** : Ne générez JAMAIS de vrai trafic
- 📚 **Responsabilité** : À utiliser uniquement à fins pédagogiques

## 📜 Licence

Ce projet est fourni à titre éducatif pour l'Université Paris Cité.

## 🤝 Contribution

Les améliorations sont bienvenues ! Pour proposer des changements :

1. Fork le projet
2. Créer une branche (`git checkout -b feature/amelioration`)
3. Commit les modifications (`git commit -m 'Ajouter une amélioration'`)
4. Push vers la branche (`git push origin feature/amelioration`)
5. Ouvrir une Pull Request

## ❓ FAQ

**Q: Peut-on lancer de vraies attaques avec ça ?**  
R: Non, ce sont des simulations visuelles 100% locales. Aucun trafic réseau n'est généré.

**Q: Fonctionne-t-il sur mobile ?**  
R: Oui, l'interface est responsive et accessible sur smartphone/tablette.

**Q: Comment ajouter de nouveaux types d'attaques ?**  
R: Créer un fichier `sim-<new-attack>.js` et l'intégrer dans `index.html` et `portal-main.js`.

**Q: Les données sont-elles collectées ?**  
R: Non, tout se passe en local dans votre navigateur.

---

**Dernière mise à jour :** novembre 2025  
**Version :** 1.0.0
