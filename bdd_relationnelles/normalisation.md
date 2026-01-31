# Normalisation et Formes Normales

> 📍 **Où on est** : Bases de Données Relationnelles → Normalisation

## 🎯 Objectifs
- Comprendre pourquoi "nettoyer" sa base de données est vital.
- Savoir appliquer les règles **1NF**, **2NF** et **3NF**.
- Éviter les doublons et les erreurs de mise à jour.

## 📘 Notions clés
- **Normalisation** : Processus pour organiser les données sans redondance.
- **Formes Normales (FN)** : Niveaux de "propreté" (1NF, 2NF, 3NF...).
- **Clé Primaire** : Identifiant unique d'une ligne.
- **Dépendance Fonctionnelle** : Quand une info dépend d'une autre (ex: le prix dépend du produit).

---

## 1. Pourquoi normaliser ?

C'est comme ranger sa chambre : on veut éviter le désordre.

> ℹ️ **Info**
> Le but est de réduire la **redondance** (doublons) et d'éviter les **anomalies** lors de l'ajout, la modification ou la suppression de données.

En pratique, on vise la **3NF** (Troisième Forme Normale). C'est le bon compromis entre structure propre et performance.

---

## 2. Première Forme Normale (1NF) : Atomicité

Pour être en 1NF, une table doit respecter deux règles simples :

1. Une **clé primaire** unique (ex: ID).
2. Des valeurs **atomiques** (une seule info par case, pas de liste).

### 🧪 Exemple 1NF

🔴 **Problème** (Non normalisé) :
```Code
Client(id, nom, commandes)
1 | Alice | iPod, iPad
```
Ici, la colonne `commandes` contient une liste "iPod, iPad". C'est interdit.

🟢 **Solution** (1NF) :
On sépare les commandes.
```Code
Client(id, nom)
Commande(id_commande, id_client, produit)
```
Chaque commande a sa propre ligne.

> ✅ **Astuce**
> Si tu utilises des virgules dans une case Excel, tu n'es probablement pas en 1NF !

---

## 3. Deuxième Forme Normale (2NF) : Dépendance Totale

Pour être en 2NF, il faut :
*   Être déjà en **1NF**.
*   Si la clé primaire est composée de plusieurs colonnes (clé composite), chaque attribut doit dépendre de **toute** la clé, pas juste d'un morceau.

### 🧪 Exemple 2NF

Imagine une table de commandes : `Commande(id_commande, id_client, produit, nom_client)`.

🔴 **Problème** :
`nom_client` dépend seulement de `id_client`, pas de `id_commande`. Si on change le nom du client, il faut le faire partout !

🟢 **Solution** (2NF) :
On sort les infos du client.
```Code
Client(id_client, nom_client)
Commande(id_commande, id_client, produit)
```
Maintenant, `nom_client` est stocké une seule fois.

> ⚠️ **Attention**
> Si ta table a une clé primaire simple (une seule colonne), elle est automatiquement en 2NF si elle est en 1NF.

---

## 4. Troisième Forme Normale (3NF) : Pas de dépendance transitive

Pour être en 3NF, il faut :
*   Être déjà en **2NF**.
*   Les colonnes ne doivent pas dépendre les unes des autres (sauf de la clé primaire).

### 🧪 Exemple 3NF

`Employe(id, nom, id_departement, nom_departement, chef_departement)`

🔴 **Problème** :
`nom_departement` dépend de `id_departement`. Si `id_departement` change, le nom doit changer. Mais `id_departement` n'est pas la clé primaire de la table Employé ! C'est une dépendance transitive :
`Employé -> id_departement -> nom_departement`.

🟢 **Solution** (3NF) :
On sépare les départements.
```Code
Employe(id, nom, id_departement)
Departement(id_dept, nom_dept, chef_dept)
```

---

## 📝 À retenir

| Forme Normale | Règle Clé | Résumé |
| :--- | :--- | :--- |
| **1NF** |  **Atomicité** | 1 case = 1 valeur. Pas de listes. |
| **2NF** | **Toute la clé** | Les infos dépendent de TOUTE la clé primaire composite. |
| **3NF** | **Rien que la clé** | Les colonnes ne dépendent pas d'autres colonnes non-clés. |

> "La clé, toute la clé, rien que la clé." (Bill Kent)

---

## ❓ Exercices

Modélise les données suivantes pour qu'elles soient en **3NF**.

**Données brutes :**
Une facture contient : `NumFacture`, `Date`, `NomClient`, `VilleClient`, `Produit`, `PrixUnitaire`, `Quantité`.

<details>
<summary>👀 Voir la solution</summary>

1. **Client**(`id_client`, nom, ville)  *(Ville dépend du client)*
2. **Produit**(`id_produit`, nom, prix_unitaire) *(Prix dépend du produit)*
3. **Facture**(`num_facture`, date, id_client)
4. **LigneFacture**(`num_facture`, `id_produit`, quantite) *(Quantité dépend de la combinaison facture+produit)*

</details>
