#outil-du-dev
# Lien :

[Metz Numeric School GitBook](https://metz-numeric-school.gitbook.io/cours-dev/git)

> Inventé par Linux / Torvald

---

## Outils de versionning (Gestion de version des fichiers)

- **Historisation des modifications** d'un répertoire
- Rendre les projets **dépendants**
- Écoute des changements (création, modification, suppression) dans un dossier
- Ne traite que les fichiers **"suivis"** (à choisir donc)

---

## PHASE 1 : Initialisation

### Choisir le répertoire cible

- Fonctionne sur invite de commande

#### Étapes :

1. **Ouvrir un terminal** (CMD, Terminal, PowerShell, GitBash)
2. **Pointer le terminal dans le répertoire cible** (en bash) :
    - Commande : `cd chemin_du_dossier` (cd = change directory, parcours de l'arborescence de l'OS)

#### Raccourcis :

1. Ouvrir le dossier dans l'**Explorateur Windows**
2. Faire un **clic droit** (RMB)
3. Sélectionner **"Open GitBash Here"**

Sous Windows 11 → **"Afficher d'autres options"**

---

### Exemple de chemin :

`C:/repositories` (pour Git-er les dossiers de projet, nom de dépôt git)

---

## Commande pour ouvrir un projet dans **VSCode** (ne jamais ouvrir d'autres projets en même temps) :

css

Copier le code

`code . nom_du_dossier`

---

### Commandes de base

- **`ls`** : Voir les fichiers dans la position actuelle dans l'arborescence
- **`cd C:/`** : Se mettre dans la racine
- **`cd _arborescence`** : Parcourir les sous-dossiers
- **`mkdir repositories`** : Créer un répertoire "repositories" dans la position actuelle
- **`cd..`** : Revenir en arrière

---

### Initialisation du projet Git

1. **`git init`** : Initialiser un projet Git
2. **`git status`** : Voir l'état actuel de la branche

---

### Créer un fichier `README.md`

shell

Copier le code

`$ echo "# Mon projet " >> README.md`

### Ajouter les fichiers au suivi de version :

csharp

Copier le code

`git add .`

### Premier commit :

sql

Copier le code

`git commit -a -m "First commit"`

---

### Lier le dépôt local au dépôt distant (GitHub)

csharp

Copier le code

`git remote add origin https://github.com/votre-nom-utilisateur/mon-projet.git git push -u origin master`

---

## Branches

- La branche **main** est la branche stable.
    
- Créer une branche **dev** avec la commande :
    
    Copier le code
    
    `git branch dev`
    
- Basculer sur la nouvelle branche :
    
    Copier le code
    
    `git checkout dev`
    
    Ou créer et basculer en une seule commande :
    
    css
    
    Copier le code
    
    `git checkout -b dev`
    
- **Fusionner deux branches** (en étant sur la branche réceptrice) :
    
    sql
    
    Copier le code
    
    `git merge dev`
    

> **`dev`** = branche tampon de **main**. Vous pouvez créer d'autres branches si nécessaire pour séparer les différentes étapes du projet.

---

### Synchronisation avec le dépôt distant

- Avant de **pusher** vos changements, vous devez d'abord faire un **pull** pour synchroniser avec le dépôt distant :
    
    Copier le code
    
    `git pull`
    

---

### Ajouter des collaborateurs

1. Aller dans les **paramètres du projet**.
2. Accédez à **Settings > Collaborators** pour ajouter des collaborateurs.

---

### Cloner un projet

- Pour cloner un projet depuis GitHub :
    
    bash
    
    Copier le code
    
    `git clone <lien_du_projet>`
    

---

### Renommer un répertoire déjà existant

bash

Copier le code

`mv anciennom nouveaunom`

##  Phase 2: Bonnes pratiques 

- **Utiliser des commits atomiques** : Commiter aussi souvent que possible avec le moins de changements possibles, sauf si on n'a pas le choix.
    
    - Les commits doivent être réalisés par fonctionnalité ou objectif.
    - Exemples :
        - Ajouter les mentions légales
        - Créer le formulaire de contact
        - Corriger la version responsive de la homepage
- **Si on est contraint de changer d'objectif ou de tâche** avant d'avoir terminé, il est conseillé de créer ou de changer de branche pour éviter un commit global mal organisé.
    
    - Exemple de nomenclature pour les branches :
        - `feature/form-contact` (ajout d'une fonctionnalité)
        - `fix/home-responsive` (correction de bug)
        - `refactor/form-contact` (amélioration du code)
- **Mises à jour régulières des branches**  
    ![[Pasted image 20241220091159.png]]
    
- **Utiliser le fichier `.gitignore`** : Permet d'ignorer certains fichiers ou répertoires (comme `cache/`, `node_modules/`, `.env`, `.vscode`).
    
    - Il faut configurer `.gitignore` avant de committer les fichiers pour éviter les complications liées à un fichier déjà commité.
- **Faire des pull requests** : Lorsque les fonctionnalités ou corrections sont terminées, il est important de soumettre des pull requests pour révision.
    
- **Faire des tags** : Si un ensemble de modifications est fonctionnel, vous pouvez étiqueter la version relative.
    
    - Exemple de commande pour créer un tag :
        
        Copier le code
        
        `git tag v1.3.0`
        
    - Pour cibler une version taguée :
        
        Copier le code
        
        `git checkout v1.3.0`
        
    - Pour pousser les tags :
        
        perl
        
        Copier le code
        
        `git push origin v1.3.0`
        
- **Incrémentation des versions** :
    
    - Format : `Majeure.Mineure.Patch`
        - **Majeure** : Changement significatif, grosse refonte.
        - **Mineure** : Petits ajouts de fonctionnalité.
        - **Patch** : Petits correctifs.
- **Conventions de commits**  
    ![[Pasted image 20241220104803.png]]
    
- **Utilisation de `git cliff` pour générer un changelog** :
    
    - Commandes :
        
        css
        
        Copier le code
        
        `git cliff -o ./CHANGELOG.md git cliff --bump -o ./CHANGELOG.md`
        
    - Ajouter les tags après avoir généré le changelog.







