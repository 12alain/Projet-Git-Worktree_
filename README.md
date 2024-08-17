# Projet Git Worktree: Développement de Fonctionnalités Simultanées

Les git worktrees permettent de créer plusieurs répertoires de travail à partir d'un seul dépôt Git. Cela vous permet de travailler sur plusieurs branches en même temps, chacun dans son propre répertoire, sans avoir à changer de branche dans le dépôt principal. En résumé, c'est une manière pratique de gérer plusieurs tâches ou fonctionnalités simultanément.
Étapes pour Créer et Utiliser des Git Worktrees
# 1. Création du Dépôt Git Principal
Créez un répertoire pour le dépôt principal :

```javascript
mkdir projet-git-worktree
cd projet-git-worktree

```
2.Initialisez le dépôt Git :


```javascript

git init

```
3.Créez un fichier README et effectuez un commit initial 

```
git add README.md
git commit -m "Initial commit avec README.md"

```
4-Créez une branche principale et effectuez un commit :


```
git checkout -b main
echo "Contenu de la branche principale" > main.txt
git add main.txt
git commit -m "Ajouter main.txt dans la branche principale"


```
# 2. Création des Branches pour les Fonctionnalités

1-Créez les branches pour les fonctionnalités :
```
git checkout -b feature-login
git checkout -b feature-dashboard

```
#3. Ajouter des Worktrees
1-Ajoutez les worktrees pour chaque fonctionnalité :
```
git worktree add ../feature-login feature-login
git worktree add ../feature-dashboard feature-dashboard

```
# 4. Développer les Fonctionnalités:
1-Naviguez vers le répertoire de la fonctionnalité de connexion et développez :
```
cd ../feature-login
```
Ajoutez des fichiers ou apportez des modifications spécifiques à la fonctionnalité de connexion. Par exemple :
```
echo "Fonctionnalité de connexion" > login.txt
git add login.txt
git commit -m "Ajouter la fonctionnalité de connexion"
```
2-Naviguez vers le répertoire de la fonctionnalité du tableau de bord et développez :

```
cd ../feature-dashboard

```
Ajoutez des fichiers ou apportez des modifications spécifiques au tableau de bord. Par exemple :
```
echo "Fonctionnalité du tableau de bord" > dashboard.txt
git add dashboard.txt
git commit -m "Ajouter la fonctionnalité du tableau de bord"
```
# 5. Fusionner les Changements:
Revenez au dépôt principal et fusionnez les branches :
```
cd ../projet-git-worktree
git checkout main
git merge feature-login
git merge feature-dashboard
```

# 6. Nettoyage:
1-Supprimez les worktrees une fois que vous avez terminé:
```
git worktree remove ../feature-login
git worktree remove ../feature-dashboard
```
2-Supprimez les branches locales si nécessaire :
```
git branch -d feature-login
git branch -d feature-dashboard

```
Pour expliquer l'utilisation des `git worktrees` à l'aide d'un dépôt, voici un guide pour créer un dépôt, ajouter des `worktrees`, et illustrer le développement de fonctionnalités simultanées.

### Étapes pour Créer et Utiliser des Git Worktrees

#### 1. Création du Dépôt Git Principal

1. **Créez un répertoire pour le dépôt principal :**

    ```sh
    mkdir projet-git-worktree
    cd projet-git-worktree
    ```

2. **Initialisez le dépôt Git :**

    ```sh
    git init
    ```

3. **Créez un fichier README et effectuez un commit initial :**

    ```sh
    echo "# Projet Git Worktree" > README.md
    git add README.md
    git commit -m "Initial commit avec README.md"
    ```

4. **Créez une branche principale et effectuez un commit :**

    ```sh
    git checkout -b main
    echo "Contenu de la branche principale" > main.txt
    git add main.txt
    git commit -m "Ajouter main.txt dans la branche principale"
    ```

#### 2. Création des Branches pour les Fonctionnalités

1. **Créez les branches pour les fonctionnalités :**

    ```sh
    git checkout -b feature-login
    git checkout main
    git checkout -b feature-dashboard
    ```

2. **Retournez à la branche principale :**

    ```sh
    git checkout main
    ```

#### 3. Ajouter des Worktrees

1. **Ajoutez les worktrees pour chaque fonctionnalité :**

    ```sh
    git worktree add ../feature-login feature-login
    git worktree add ../feature-dashboard feature-dashboard
    ```

    Cette commande crée deux nouveaux répertoires (`../feature-login` et `../feature-dashboard`), chacun lié à la branche correspondante.

#### 4. Développer les Fonctionnalités

1. **Naviguez vers le répertoire de la fonctionnalité de connexion et développez :**

    ```sh
    cd ../feature-login
    ```

    Ajoutez des fichiers ou apportez des modifications spécifiques à la fonctionnalité de connexion. Par exemple :

    ```sh
    echo "Fonctionnalité de connexion" > login.txt
    git add login.txt
    git commit -m "Ajouter la fonctionnalité de connexion"
    ```

2. **Naviguez vers le répertoire de la fonctionnalité du tableau de bord et développez :**

    ```sh
    cd ../feature-dashboard
    ```

    Ajoutez des fichiers ou apportez des modifications spécifiques au tableau de bord. Par exemple :

    ```sh
    echo "Fonctionnalité du tableau de bord" > dashboard.txt
    git add dashboard.txt
    git commit -m "Ajouter la fonctionnalité du tableau de bord"
    ```

#### 5. Fusionner les Changements

1. **Revenez au dépôt principal et fusionnez les branches :**

    ```sh
    cd ../projet-git-worktree
    git checkout main
    git merge feature-login
    git merge feature-dashboard
    ```

#### 6. Nettoyage

1. **Supprimez les worktrees une fois que vous avez terminé :**

    ```sh
    git worktree remove ../feature-login
    git worktree remove ../feature-dashboard
    ```

2. **Supprimez les branches locales si nécessaire :**

    ```sh
    git branch -d feature-login
    git branch -d feature-dashboard
    ```

En suivant ces étapes, vous pouvez facilement illustrer comment les `git worktrees` permettent de travailler sur plusieurs branches simultanément sans avoir à changer de branche dans le dépôt principal.












