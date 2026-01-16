# Cas de Test - Login GitHub

## CT-GH-001 : Connexion avec identifiants valides

### Fonction de Test (g)
Vérifier que l'utilisateur peut se connecter avec succès à GitHub en utilisant des identifiants valides.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Username/Email | `moncompte` ou `utilisateur@example.com` |
| Mot de passe | `MotDePasseSecurise456!` |

### Résultats Attendus (RA)
1. L'utilisateur est redirigé vers son tableau de bord GitHub
2. L'avatar et le nom d'utilisateur apparaissent en haut à droite
3. Le lien vers les repositories personnels est accessible
4. Aucun message d'erreur n'est affiché

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir le navigateur et accéder à `https://github.com/login` | La page de connexion GitHub s'affiche |
| 2 | Localiser le champ "Username or email address" | Le champ est visible et accessible |
| 3 | Saisir le nom d'utilisateur ou email valide | Les données sont affichées dans le champ |
| 4 | Localiser le champ "Password" | Le champ est visible et accessible |
| 5 | Saisir le mot de passe valide | Les caractères sont masqués |
| 6 | Cliquer sur le bouton "Sign in" | Chargement en cours |
| 7 | Attendre la redirection | Page tableau de bord affichée |

### Préconditions
- Compte GitHub existant et actif
- Connexion internet stable
- Authentification à deux facteurs désactivée (ou token disponible)

### Postconditions
- Utilisateur authentifié sur GitHub
- Session active avec cookies de session

---

## CT-GH-002 : Connexion avec mot de passe incorrect

### Fonction de Test (g)
Vérifier que le système refuse la connexion avec un mot de passe incorrect.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Username/Email | `moncompte` |
| Mot de passe | `MauvaisMotDePasse` |

### Résultats Attendus (RA)
1. L'utilisateur reste sur la page de connexion
2. Message d'erreur : "Incorrect username or password."
3. Le champ mot de passe est vidé

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://github.com/login` | Page de connexion affichée |
| 2 | Saisir le username valide | Username affiché |
| 3 | Saisir un mot de passe incorrect | Caractères masqués |
| 4 | Cliquer sur "Sign in" | Erreur affichée |
| 5 | Vérifier le message | "Incorrect username or password." |

---

## CT-GH-003 : Connexion avec username inexistant

### Fonction de Test (g)
Vérifier que le système refuse la connexion avec un compte non enregistré.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Username/Email | `utilisateurinexistant999xyz` |
| Mot de passe | `UnMotDePasse123` |

### Résultats Attendus (RA)
1. L'utilisateur reste sur la page de connexion
2. Message d'erreur générique (sécurité : ne pas révéler l'existence du compte)
3. Pas de création de session

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://github.com/login` | Page de connexion affichée |
| 2 | Saisir un username inexistant | Username affiché |
| 3 | Saisir un mot de passe quelconque | Caractères masqués |
| 4 | Cliquer sur "Sign in" | Message d'erreur affiché |

---

## CT-GH-004 : Connexion avec champs vides

### Fonction de Test (g)
Vérifier le comportement du système lorsque les champs sont laissés vides.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Username/Email | *(vide)* |
| Mot de passe | *(vide)* |

### Résultats Attendus (RA)
1. Le bouton "Sign in" déclenche une validation
2. Messages d'erreur pour les champs requis

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://github.com/login` | Page de connexion affichée |
| 2 | Laisser les champs vides | Champs vides |
| 3 | Cliquer sur "Sign in" | Validation des champs obligatoires |

---

## CT-GH-005 : Vérification du lien "Forgot password"

### Fonction de Test (g)
Vérifier que le lien de récupération de mot de passe fonctionne.

### Données d'Entrée (DE)
*(Aucune saisie requise)*

### Résultats Attendus (RA)
1. Le lien "Forgot password?" est cliquable
2. Redirection vers la page de récupération de mot de passe

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://github.com/login` | Page de connexion affichée |
| 2 | Localiser "Forgot password?" | Lien visible |
| 3 | Cliquer sur le lien | Redirection vers `/password_reset` |

---

## Matrice de Traçabilité

| ID Test | Exigence | Priorité | Statut |
|---------|----------|----------|--------|
| CT-GH-001 | Authentification réussie | Haute | À exécuter |
| CT-GH-002 | Gestion erreur mot de passe | Haute | À exécuter |
| CT-GH-003 | Gestion username inconnu | Moyenne | À exécuter |
| CT-GH-004 | Validation champs obligatoires | Haute | À exécuter |
| CT-GH-005 | Récupération mot de passe | Moyenne | À exécuter |

---

## Environnement de Test

| Élément | Spécification |
|---------|---------------|
| Navigateurs | Chrome 120+, Firefox 121+, Edge 120+ |
| Système d'exploitation | Windows 10/11, macOS, Linux |
| Résolution écran | 1920x1080 (minimum 1366x768) |
| Connexion | Internet haut débit |
