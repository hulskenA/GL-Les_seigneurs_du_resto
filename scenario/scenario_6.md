### <u>Scénario 6 :</u> Le plat commandé n’est plus disponible

> *Ce scénario intervient apres que le client ait fait son choix de plat, dans le cas où la commande est déja envoyée et les préparateurs ne sont plus en mesure de réaliser le plat. Ce scénario n'est pas explicité dans le cahier des charges fourni, mais est indispensable au bon fonctionnement du restaurant.*

---
#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

#### Acteurs principaux : Préparateurs et le serveur.

#### Pré-conditions : Une commande est reçue par les préparateurs.

#### Déclenchement : Les préparateurs n'ont plus les ingrédients pour confectionner le plat souhaité.

#### Scénario nominal :

1. Les cuisiniers recoivent la commande du client. Il s'apercoivent que le plat n'est plus disponible, ils envoient une notification pour cet évenement.

2. Le plat est retiré de la carte par le préparateur pour le reste du service.

1. Le serveur est notifié de la situation, il informe le client de l'indisponibilié de son plat et lui propose de modifier son choix

1. Le serveur modifie la commande et le cuisinier est notifié à nouveau.  

#### Post-conditions : Le préparateurs visualisent le nouveau choix.
---

[:leftwards_arrow_with_hook: Retour à la page d'accueil](../README.md)
