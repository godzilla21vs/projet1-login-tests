# Cas de Test - Login Facebook

## CT-FB-001 : Connexion avec identifiants valides

### Fonction de Test (g)
Vérifier que l'utilisateur peut se connecter avec succès à Facebook en utilisant des identifiants valides.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Email/Téléphone | `utilisateur@example.com` |
| Mot de passe | `MotDePasseValide123!` |

### Résultats Attendus (RA)
1. L'utilisateur est redirigé vers sa page d'accueil (fil d'actualité)
2. Le nom de l'utilisateur apparaît dans la barre de navigation
3. Aucun message d'erreur n'est affiché
4. La session est créée (cookie de session actif)

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir le navigateur et accéder à `https://www.facebook.com` | La page de connexion Facebook s'affiche |
| 2 | Localiser le champ "Adresse e-mail ou numéro de mobile" | Le champ est visible et accessible |
| 3 | Saisir l'email valide dans le champ | L'email est affiché dans le champ |
| 4 | Localiser le champ "Mot de passe" | Le champ est visible et accessible |
| 5 | Saisir le mot de passe valide | Les caractères sont masqués (●●●●) |
| 6 | Cliquer sur le bouton "Se connecter" | Chargement de la page |
| 7 | Attendre la redirection | Page d'accueil affichée avec fil d'actualité |

### Préconditions
- Compte Facebook existant et actif
- Connexion internet stable
- Navigateur compatible (Chrome, Firefox, Edge)

### Postconditions
- Utilisateur authentifié
- Session active

---

## CT-FB-002 : Connexion avec mot de passe incorrect

### Fonction de Test (g)
Vérifier que le système refuse la connexion avec un mot de passe incorrect.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Email/Téléphone | `utilisateur@example.com` |
| Mot de passe | `MotDePasseIncorrect` |

### Résultats Attendus (RA)
1. L'utilisateur reste sur la page de connexion
2. Un message d'erreur s'affiche indiquant que le mot de passe est incorrect
3. Aucune session n'est créée

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://www.facebook.com` | Page de connexion affichée |
| 2 | Saisir l'email valide | Email affiché |
| 3 | Saisir un mot de passe incorrect | Caractères masqués |
| 4 | Cliquer sur "Se connecter" | La page affiche une erreur |
| 5 | Vérifier le message d'erreur | "Mot de passe incorrect" ou similaire |

---

## CT-FB-003 : Connexion avec email inexistant

### Fonction de Test (g)
Vérifier que le système refuse la connexion avec un email non enregistré.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Email/Téléphone | `emailinexistant12345@test.com` |
| Mot de passe | `UnMotDePasse123` |

### Résultats Attendus (RA)
1. L'utilisateur reste sur la page de connexion
2. Un message d'erreur indique que l'email n'est pas reconnu
3. Suggestion de créer un compte

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://www.facebook.com` | Page de connexion affichée |
| 2 | Saisir un email inexistant | Email affiché |
| 3 | Saisir un mot de passe quelconque | Caractères masqués |
| 4 | Cliquer sur "Se connecter" | Message d'erreur affiché |

---

## CT-FB-004 : Connexion avec champs vides

### Fonction de Test (g)
Vérifier le comportement du système lorsque les champs sont vides.

### Données d'Entrée (DE)
| Paramètre | Valeur |
|-----------|--------|
| Email/Téléphone | *(vide)* |
| Mot de passe | *(vide)* |

### Résultats Attendus (RA)
1. Le formulaire ne se soumet pas
2. Un message d'erreur ou validation HTML5 indique les champs requis

### Étapes de Test
| # | Action | Résultat Attendu |
|---|--------|------------------|
| 1 | Ouvrir `https://www.facebook.com` | Page de connexion affichée |
| 2 | Laisser les champs vides | Champs vides |
| 3 | Cliquer sur "Se connecter" | Validation : champs obligatoires |

---

## Matrice de Traçabilité

| ID Test | Exigence | Priorité | Statut |
|---------|----------|----------|--------|
| CT-FB-001 | Authentification réussie | Haute | À exécuter |
| CT-FB-002 | Gestion erreur mot de passe | Haute | À exécuter |
| CT-FB-003 | Gestion email inconnu | Moyenne | À exécuter |
| CT-FB-004 | Validation champs obligatoires | Haute | À exécuter |
