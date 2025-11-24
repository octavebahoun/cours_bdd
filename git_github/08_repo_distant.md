# Travailler avec des dépôts distants
Jusqu’ici, nous avons utilisé Git en local. Mais en pratique, les projets sont souvent collaboratifs : plusieurs personnes travaillent ensemble sur le même code. Pour cela, on utilise des dépôts distants, hébergés sur des serveurs accessibles via Internet ou un réseau d’entreprise.

La gestion des dépôts distants est plus complexe que celle des dépôts locaux, car il faut :

 - gérer les droits d’accès des utilisateurs,
 - décider quelles modifications doivent être intégrées,
 - coordonner les contributions.

Principe : on clone le dépôt distant en local, on fait ses modifications, puis on les pousse vers le serveur. Les changements peuvent ensuite être acceptés ou rejetés.

## Cloner, afficher et renommer un dépôt distant
Cloner un dépôt :

```bash
git clone url-du-depot
```

Lister les dépôts distants associés :

```bash
git remote
git remote -v   # affiche les URLs
```
Par défaut, le dépôt cloné est nommé origin.


## Récupérer des données depuis un dépôt distant
Récupérer les nouvelles données sans les fusionner :

```bash
git fetch
```
→ Les données sont téléchargées mais restent séparées.

Récupérer et fusionner directement :

```bash
git pull
```
→ Les modifications de la branche distante sont intégrées dans la branche locale.

## Pousser des modifications vers un dépôt distant
Commande :

```bash
git push nom-distant nom-de-branche
```
Exemple :

```bash
git push origin master
```
Conditions :
 - avoir les droits d’écriture sur le serveur,
 - éviter les conflits si quelqu’un d’autre a poussé des modifications entre-temps.

## Obtenir des informations sur un dépôt distant
Commande :

```bash
git remote show nom-distant
```
Donne :

 - les URLs du dépôt,
 - les branches suivies,
 - celles fusionnées automatiquement avec git pull,
 - celles poussées avec git push.


# En résumé :

 - `git clone` → copier un dépôt distant.
 - `git fetch` → récupérer sans fusionner.
 - `git pull` → récupérer et fusionner.
 - `git push` → envoyer ses modifications.
 - `git remote` → gérer les dépôts distants (ajout, renommage, suppression).
