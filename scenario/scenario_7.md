### <u>Scénario 7 :</u> Gestion de la disponibilité des tables

> *Le but de ce scénario est de mettre en évidence le fait que notre application gère la disponibilité des tables. Cette fonctionalité peut-être utile si le restaurant possède plusieurs étages par exemple. Ce cas n'est pas dans le cahier des charges fourni.*

---

#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

#### Acteurs principaux : Deux groupes de clients et un serveur.

#### Pré-conditions : Des clients sont sur le départ et un groupe de client arrive.

#### Déclenchement : Des clients viennent de finir leur repas.

#### Scénario nominal :

1. Timoléon, client du restaurant, demande l'addition à son serveur.

1. Lorsqu'il paye, la libération de la table est prise en compte par l'application.

1. Dès lors, un jeune couple entre dans le restaurant.

1. Le serveur consulte les tables disponibles sur l'application.

1. Le serveur installe les clients.

1. La table n'est désormais plus disponible sur l'application.

#### Post-conditions : Le groupe de client venant d'arriver est installé.
---

[:leftwards_arrow_with_hook: Retour à la page d'accueil](../README.md)
