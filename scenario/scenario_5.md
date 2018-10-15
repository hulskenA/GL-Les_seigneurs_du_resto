### <u>Scénario 5 :</u> Déroulement des commandes de plusieurs clients distincts

> *Ce scénario décrit le déroulement des commandes et du service en fonction de l’ordre d’arrivée des différents clients. Le but est de montrer que le logiciel traite les commandes de manière séquentielle.*

---

#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

#### Acteurs principaux : Bob, Timoléon et un serveur.

#### Pré-conditions : Timoléon a réalisé une commande.

#### Déclenchement : Bob prend une commande.

#### Scénario nominal :

1. Bob arrive au restaurant, le serveur prend sa commande : entrée, plat, dessert.

1. La commande est envoyée à la cuisine (resp. bar, resp. glacier). La commande de Bob apparaît après celle de Timoléon dans la file des plats (resp. boisson, resp. glaces) à préparer.

1. Bob est servi après Timoléon.

#### Post-conditions : Les préparateurs voient les commandes par ordre d'arrivée
---

[:leftwards_arrow_with_hook: Retour à la page d'accueil](../README.md)
