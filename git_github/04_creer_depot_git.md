# Les deux façons de créer un dépôt Git
Il existe deux méthodes principales pour démarrer un dépôt Git :

 - Initialiser un dépôt à partir d’un répertoire existant.
 - Cloner un dépôt déjà existant.

# Créer un dépôt Git à partir d’un répertoire existant
Souvent, on dispose déjà d’un projet sur son ordinateur ou sur un serveur et l’on souhaite mettre en place un système de gestion de versions.

Étapes pratiques :
Préparer le répertoire

Exemple : créer un dossier projet-git contenant deux fichiers vides : fichier1.txt et README.txt.

Commandes utiles :

```bash
cd ..        # se placer sur le bureau
mkdir projet-git  # créer le répertoire
cd projet-git     # entrer dans le répertoire
touch fichier1.txt README.txt  # créer les fichiers
ls                # vérifier le contenu
```

Initialiser le dépôt

Commande :

```bash
git init
```
Cela crée un sous-répertoire .git contenant les fichiers nécessaires au fonctionnement du dépôt.

Git confirme l’initialisation et précise que le dépôt est vide (aucun fichier encore versionné).

Vérifier l’état des fichiers

Commande :

```bash
git status
```
Résultat : les fichiers apparaissent comme non suivis (untracked).

Git indique également la branche active (par défaut master).

Indexer les fichiers

Commande :

```bash
git add fichier1.txt README.txt
```
On peut aussi utiliser des motifs (fileglobs) comme :

```bash
git add *.txt
```
Les fichiers passent alors à l’état indexés (staged).

Valider les fichiers

Commande :

```bash
git commit -m "Version initiale du projet"
```
Exemple de message : "Version initiale du projet".

Une fois validé, Git enregistre les fichiers dans la base locale et affiche les informations du commit (branche, identifiant unique, nombre de fichiers modifiés).

Vérification finale

Commande :

```bash
git status
```
Résultat : aucun fichier en attente, tous sont désormais suivis et enregistrés.

# Cloner un dépôt Git existant
La seconde méthode consiste à cloner un dépôt déjà créé.

Étapes pratiques :
Se placer dans le répertoire parent

```bash
cd ..
```

## Cloner le projet

Commande :

```bash
git clone <url du projet git à copier>
```
Ici, on copie le dépôt du projet git à copier dans le dossier courant.

## Vérifier l’état du clone

Commande :
```bash
cd <nom du projet git>
git status
```
Résultat : tous les fichiers sont déjà suivis et enregistrés en base, car l’historique complet du projet a été copié.

# En résumé :

 - `git init` sert à transformer un répertoire existant en dépôt Git.
 - `git clone` permet de copier un dépôt déjà existant, avec tout son historique.
