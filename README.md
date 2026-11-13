# TP-Gestion_de_vol
# Gestion de Réservation de Billets d'Avion (Application Console C++)

## 📝 Présentation du Projet
Ce projet consiste en une application de gestion de vols et de réservations de billets d'avion pour une agence de voyage. Développée en **C++** en respectant les principes de la **Programmation Orientée Objet (POO)**, cette application en mode console permet de gérer l'intégralité du flux de réservation, depuis l'enregistrement des passagers jusqu'au traitement des paiements et des annulations.

## 🚀 Fonctionnalités Principales
L'application s'articule autour d'un menu principal interactif proposant les 10 options attendues :

1. **Enregistrer un passager** : Ajout d'un nouveau client avec ses coordonnées (Nom, Prénom, Téléphone, Numéro de pièce d'identité).
2. **Ajouter un vol** : Création d'un vol avec une capacité maximale et un tarif défini.
3. **Afficher les vols disponibles** : Liste de tous les vols ayant encore des places libres.
4. **Rechercher les vols disponibles** : Recherche ciblée de vols selon des critères précis.
5. **Effectuer une réservation** : Association d'un passager enregistré à un vol disponible (gère l'unicité de la réservation).
6. **Enregistrer un paiement** : Règlement d'une réservation active (par Espèces, Carte ou Mobile Money).
7. **Annuler une réservation** : Libération de la place occupée sur le vol et calcul automatique du remboursement si la réservation était payée.
8. **Consulter une réservation** : Recherche et affichage d'un dossier de réservation à l'aide de son identifiant.
9. **Afficher les informations d'une réservation** : Vue d'ensemble détaillée incluant le passager, le vol concerné et le statut du paiement.
10. **Quitter** : Fermeture sécurisée de l'application console.

## ⚙️ Principes Métiers Implémentés
* **Enregistrement obligatoire** : Un passager doit obligatoirement être créé dans le système avant de pouvoir réserver un billet.
* **Contrôle des capacités** : Un vol ne peut accepter plus de réservations que sa capacité maximale définie.
* **Unicité des trajets** : Un passager ne peut pas réserver deux fois le même vol (si la première réservation est toujours active).
* **Règles d'annulation** : Une réservation annulée ne peut plus être utilisée pour un paiement. Les places sur le vol ne sont définitivement confirmées qu'après validation.

## 🛠️ Concepts POO Utilisés
* **Encapsulation** : Utilisation stricte des attributs privés (`private`) accessibles uniquement via des getters/setters et des méthodes publiques.
* **Constructeurs** : Initialisation propre et sécurisée de tous les objets (`Passager`, `Vol`, `Reservation`, `Paiement`).
* **Collections dynamiques** : Utilisation de `std::vector` pour le stockage et la gestion dynamique des données au sein de la classe principale `Agence`.
* **Gestion des erreurs** : Contrôle des saisies utilisateurs et des exceptions logiques du système (par exemple : tenter de payer une réservation déjà annulée).

## 💻 Instructions de Compilation et d'Exécution

### Prérequis
Assurez-vous de disposer d'un compilateur prenant en charge au moins la norme **C++11** (comme `g++` ou `clang`).

### 1. Compilation via le Terminal
Ouvrez votre terminal dans le dossier contenant les fichiers sources (`.cpp` et `.h`) et exécutez la commande suivante :

```bash
g++ -std=c++11 main.cpp Agence.cpp Passager.cpp Vol.cpp Reservation.cpp Paiement.cpp -o ApplicationAgence
```

*(Note : Ajustez la liste des fichiers `.cpp` selon l'organisation exacte de votre code source).*

### 2. Exécution du Programme
Une fois la compilation réussie, lancez l'application à l'aide de la commande suivante :

* **Sur Linux / macOS :**
  ```bash
  ./ApplicationAgence
  ```
* **Sur Windows :**
  ```cmd
  ApplicationAgence.exe
  ```

## 📁 Architecture des Fichiers du Projet
* `main.cpp` : Point d'entrée de l'application (gestion de la boucle du menu console).
* `Agence.h` / `Agence.cpp` : Classe maîtresse centralisant les vecteurs de données et la logique métier.
* `Passager.h` / `Passager.cpp` : Modèle de données pour les clients.
* `Vol.h` / `Vol.cpp` : Gestion des vols et des places disponibles.
* `Reservation.h` / `Reservation.cpp` : Logique de liaison entre un passager et un vol.
* `Paiement.h` / `Paiement.cpp` : Entité comptable gérant les transactions et les statuts de remboursement.
* `diagramme_classe.puml` : Fichier PlantUML décrivant la modélisation des classes.
* `README.md` : Guide d'utilisation et de présentation du projet.
* 
