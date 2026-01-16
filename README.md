# Projet 1 - Cas de Test Login (Facebook & GitHub)

## 📋 Description

Ce projet contient les **cas de test manuels détaillés** pour valider l'authentification utilisateur sur les plateformes Facebook et GitHub. Chaque cas de test est documenté selon une méthodologie rigoureuse, conforme aux standards de test logiciel.

Ce projet fait partie du cours **INF563 - Test Logiciel**.

## 🎯 Objectifs Pédagogiques

- Conception de cas de test structurés
- Identification des scénarios positifs et négatifs
- Documentation professionnelle des tests
- Analyse des données d'entrée et résultats attendus
- Création de matrices de traçabilité

## 📁 Structure du Projet

```
projet1-login-tests/
├── README.md               # Documentation principale
├── cas_test_facebook.md    # Cas de test pour Facebook Login (4 scénarios)
└── cas_test_github.md      # Cas de test pour GitHub Login (5 scénarios)
```

## 🔬 Méthodologie de Test

Chaque cas de test est défini selon le format standardisé :

| Élément | Description |
|---------|-------------|
| **ID du Test** | Identifiant unique (CT-FB-XXX, CT-GH-XXX) |
| **Fonction de Test (g)** | Objectif spécifique du test |
| **Données d'Entrée (DE)** | Données nécessaires à l'exécution |
| **Résultats Attendus (RA)** | Comportement attendu du système |
| **Étapes de Test** | Procédure détaillée pas à pas |
| **Préconditions/Postconditions** | État avant et après le test |

## 📝 Scénarios de Test

### Facebook Login (cas_test_facebook.md)

| ID | Scénario | Priorité | Type |
|----|----------|----------|------|
| CT-FB-001 | Connexion avec identifiants valides | Haute | Positif |
| CT-FB-002 | Connexion avec mot de passe incorrect | Haute | Négatif |
| CT-FB-003 | Connexion avec email inexistant | Moyenne | Négatif |
| CT-FB-004 | Connexion avec champs vides | Haute | Négatif |

### GitHub Login (cas_test_github.md)

| ID | Scénario | Priorité | Type |
|----|----------|----------|------|
| CT-GH-001 | Connexion avec identifiants valides | Haute | Positif |
| CT-GH-002 | Connexion avec mot de passe incorrect | Haute | Négatif |
| CT-GH-003 | Connexion avec username inexistant | Moyenne | Négatif |
| CT-GH-004 | Connexion avec champs vides | Haute | Négatif |
| CT-GH-005 | Vérification du lien "Forgot password" | Moyenne | Fonctionnel |

## 🖥️ Environnement de Test

| Élément | Spécification |
|---------|---------------|
| **Navigateurs** | Chrome 120+, Firefox 121+, Edge 120+ |
| **Système d'exploitation** | Windows 10/11, macOS, Linux |
| **Résolution écran** | 1920x1080 (minimum 1366x768) |
| **Connexion** | Internet haut débit stable |

## 📊 Couverture des Tests

```
Total des cas de test : 9
├── Tests Positifs : 2 (22%)
├── Tests Négatifs : 6 (67%)
└── Tests Fonctionnels : 1 (11%)

Priorité :
├── Haute : 6 tests (67%)
└── Moyenne : 3 tests (33%)
```

## 🚀 Comment Utiliser

1. **Lire** les cas de test dans les fichiers `.md`
2. **Préparer** l'environnement selon les préconditions
3. **Exécuter** chaque étape de test manuellement
4. **Comparer** les résultats obtenus aux résultats attendus
5. **Documenter** le statut (Passé/Échoué) et les observations

## 📈 Matrice de Traçabilité

La matrice de traçabilité complète se trouve à la fin de chaque fichier de cas de test, permettant de :
- Suivre la couverture des exigences
- Identifier les priorités de test
- Gérer le statut d'exécution

## 🔗 Références

- [Facebook Login](https://www.facebook.com)
- [GitHub Login](https://github.com/login)

## 👤 Auteur

**Cours INF563 - Test Logiciel**

---

*Ce projet est à but éducatif et démontre les bonnes pratiques en conception de cas de test.*
