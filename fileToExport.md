---
phantomjs:
    header:
        height: "9mm"
        contents: "<div style='text-align: right;'>GL - Les Seigneurs du resto</div>"
    footer:
        height: "9mm"
        contents:
            default: '<span style="color: #444;"><u>Page :</u> {{page}}</span>/<span>{{pages}}</span>'
---

<h1 style="text-align:center">Génie Logiciel
<br/>
Sujet 1 - Prise de commande dans un restaurant
</h1>

![Rendu: 2](https://img.shields.io/badge/Rendu-2-green.svg?longCache=true&style=for-the-badge)  ![PDF: V3.1](https://img.shields.io/badge/PDF-V3.1-blue.svg?longCache=true&style=for-the-badge)

<table>
<tbody>
<tr><td style="border:none" rowspan="2"><img src="http://www.fil.univ-lille1.fr/portail/img/logo-FIL-transparent-site.png" width="300"/></td><th style="border:none">Enseignant responsable du module:<br/> Cedric Dumoulin </th></tr>
<tr><th style="border:none">Enseignant de travaux dirigés:<br/> Michaël Launay </th></tr>
<tbody>
</table>

## Auteurs: Les  seigneurs du resto

>>>
+ Louisa Fodil
+ Valentine Lejeune
+ Alexandre Hulsken
+ Martin Vasilev
+ Rémi Delavalle
>>>

#### M1S1 - Gr.1

---

> Ce projet porte sur l'analyse et la conception d'une application de commande pour un restaurateur.

> L’objectif de l’application est de faciliter la communication entre les différents membres de l’équipe restauratrice et ainsi d’améliorer leur coordination. La réactivité de l’équipe sera améliorée.

---

<div style="page-break-before: always;"> </div>

## Table des matières

1. [Bilans de séance](#Bilan1)
    1. [Bilan 11/09/2018](#Bilan1)
    2. [Bilan 25/09/2018](Bilan2)
    2. [Bilan 02/10/2018](Bilan3)
    2. [Bilan 09/10/2018](Bilan4)
    2. [Bilan 23/10/2018](Bilan5)
    2. [Bilan 06/11/2018](Bilan6)
3. [Scénarios possibles d'utilisation](#scenario1)
    1. [Prise de commande et notifications](#scenario1)
    2. [La commande se déroule comme prévu](#scenario2)
    3. [Le client ajoute un élément à sa commande](#scenario3)
    4. [La commande est modifiée](#scenario4)
    5. [Déroulement des commandes de plusieurs clients distincts](#scenario5)
    6. [Le plat commandé n’est plus disponible](#scenario6)
    7. [Ajout ou retrait des tables disponibles](#scenario7)
    8. [Attribution d’une table à un serveur](#scenario8)
    9. [Le client saisit lui même sa commande via une tablette](#scenario9)
    10. [Les responsables ajoutent/enlèvent des plats à la carte](#scenario10)
4. [Tableau Sujet / Concept / Type correspondant à nos scénarios](#tableau)
5. [Diagramme de Cas d'utilisations](#CU)
6. [Diagramme de Classes](#DC)
7. [Diagramme de Séquences](#DS)
    1. [Diagramme de Séquences Simples](#DSS)
    2. [Diagramme de Séquences Détaillés](#DSD)
8. [Maquettes de l'application](#maquette)
    1. [Maquettes de l'interface Gérant](#maquetteGerant)
    2. [Maquettes de l'interface Préparateur](#maquettePreparateur)
    3. [Maquettes de l'interface Serveur](#maquetteTabletteServeur)
    4. [Maquettes de l'interface Client](#maquetteTabletteClient)

+ [[Annexe] Glossaire métier](#glossaire_metier)
+ [[Annexe] Glossaire technique](#glossaire_technique)
+ [[Annexe] Glossaire ingenierie besoins](#glossaire_ingenierie_besoins)
+ [[Annexe] Récapitulation de commandes `GIT` usuelles](#recap_git)

<div style="page-break-before: always;"> </div>

### Bilan des tâches {#Bilan1}
##### *11/09/2018*

---

- ***Choix du sujet :*** prise des commandes d’un restaurant
- ***Brainstorming :*** idées des features à développer
- Conception et rédaction des différents scénarios
- Définition des scénarios à préparer pour la séance du 18 septembre.

<div style="page-break-before: always;"> </div>

### Bilan des tâches {#Bilan2}
##### *25 / 09 / 2018*

---

- ***Diagramme use case :*** Description des principales fonctionnalités de l'application sous forme de diagramme.
- ***Diagramme UML :*** Premier jet d'équipe sur le diagramme UML.
- ***Organisation :*** Répartition des tâches.

<div style="page-break-before: always;"> </div>

### Bilan des tâches {#Bilan3}
##### *02 / 10 / 2018*

---

- travail sur les diagrammes de Cas d'Utilisation
- travail d'équipe sur des choix de conception lors de diagramme UML
- veille technologique et recherche sur des solutions d'exports pdf

<div style="page-break-before: always;"> </div>

### Bilan des tâches {#Bilan4}
##### *09 / 10 / 2018*

---

+ Présentation de rendu n°1
+ Refonte des scénarios 1 à 8

<div style="page-break-before: always;"> </div>

### Bilan des tâches {#Bilan5}
##### *23 / 10 / 2018*

---

+ Préparation des diagrammes de séquences

<div style="page-break-before: always;"> </div>

### Bilan des tâches {#Bilan6}
##### *06 / 11 / 2018*

---

+ Travail de groupe sur les diagrammes de séquences
+ Reflexion sur l'architecture de l'application
+ Préparation des diagrammes de séquences détaillés
+ Préparation de différentes maquettes

<div style="page-break-before: always;"> </div>

## Scénarios possibles d'utilisation {#scenario1}

### <u>Scénario 1 :</u> Prise de commande et notifications

> *Ce scénario décrit le déroulement du début à la fin d’une commande et du repas d’un client.*

---

#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

#### Acteurs principaux : Les clients et le serveur

#### Pré-conditions : Le serveur dispose d'une tablette avec accès à l'application.

#### Déclenchement : Les clients souhaitent prendre une commande.

#### Scénario nominal :

1. Timoléon se rend au restaurant. Un serveur installe Timoléon à une table et prend sa commande.

1. Timoléon souhaite une entrée, un plat, une glace ainsi qu’une boisson.
Le serveur saisit la commande sur sa tablette.

1. Le serveur valide la commande.

1. Les cuisiniers reçoivent la commande de l’entrée et le plat et commencent leurs préparations.
Le barman est notifié de la commande de boisson.
Le glacier reçoit la commande de la glace dans la file d’attente.


#### Post-conditions : Les préparateurs visualisent la commande.

<div style="page-break-before: always;"> </div>

### <u>Scénario 2 :</u> La commande se déroule comme prévu {#scenario2}

> *Déroulement normal d'un service*

---

#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

#### Acteurs principaux : Les clients et le serveur

#### Pré-conditions : Le serveur dispose d'une tablette avec accès à l'application.

#### Déclenchement : Le serveur reçoit une notification de fin de préparation.

#### Scénario nominal :

1. Le serveur est notifié lorsque la boisson est prête.
Le serveur amène la boisson à Timoléon.

1. Le serveur est notifié lorsque l’entrée est prête. Il la sert à Timoléon.

1. Lorsque Timoléon a fini son entrée, le serveur débarrasse la table. Il sert le plat.

1. Le serveur débarrasse le plat et apporte le dessert.

1. Timoléon finit son dessert, il est débarrassé.

1. Le serveur clôture la commande qui disparaît de l’application et peut générer l’addition.

#### Pré-conditions : Le client peut payer l'addition.

<div style="page-break-before: always;"> </div>

### <u>Scénario 3 :</u> Le client ajoute un élément à sa commande {#scenario3}

> *Il nous semble nécessaire qu'un client puisse ajouter un élément à sa commande.  Ce scénario n'est pas dans le cahier des charges, il est cependant indispensable à la satisfaction des clients.*

---

#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

#### Acteurs principaux : Les clients et le serveur

#### Pré-conditions : Le serveur dispose d'une tablette avec accès à l'application.

#### Déclenchement : Le client désire autre chose.

#### Scénario nominal :

1. Timoléon vient de terminer son repas. Il est débarrassé par le serveur.

1. Le serveur demande si Timoléon désire autre chose.

1. Timoléon répond qu’il désire une autre glace ainsi qu’un café.

1. Le serveur notifie le barman et le glacier qui prépare la glace sans attendre.
Le serveur amène la glace et le café à Timoléon.

#### Post-conditions : les préparateurs voient la suite de la commande.

<div style="page-break-before: always;"> </div>

### <u>Scénario 4 :</u> La commande est modifiée {#scenario4}

> *Ce scénario peut intervenir à tout moment. Il nous semble important que le client puisse modifier sa commande.  Ce scénario n'est pas dans le cahier des charges fourni.*

---
#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

:warning:<span style="background-color: #ff6d6d; align-item: middle">Ce scénario sera explicité dans une version ultérieure de notre logiciel. </span>

<div style="page-break-before: always;"> </div>

### <u>Scénario 5 :</u> Déroulement des commandes de plusieurs clients distincts {#scenario5}

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

#### Post-conditions : Les préparateurs voient les commandes par ordre d'arrivée {#scenario6}

<div style="page-break-before: always;"> </div>

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

<div style="page-break-before: always;"> </div>

### <u>Scénario 7 :</u> Gestion de la disponibilité des tables {#scenario7}

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

<div style="page-break-before: always;"> </div>

### <u>Scénario 8 :</u> Attribution d’un groupe de table à un serveur {#scenario8}

> *Nous voulons inclure la possibilité de gérer la répartition des tables entre les serveurs. Ce scénario n'était pas présent dans le cahier des charges, cependant il est essentiel au bon fonctionnement du restaurant.*

---

#### Version : 2

#### Auteurs : Martin VASILEV, Valentine LEJEUNE, Alexandre HULSKEN, Louisa FODIL, Rémi DELAVALLE

:warning:<span style="background-color: #ff6d6d; align-item: middle">Ce scénario sera explicité dans une version ultérieure de notre logiciel. </span>

<div style="page-break-before: always;"> </div>

### <u>Scénario 9 :</u> Le client saisit lui même sa commande via une tablette {#scenario9}

> *Ce scénario décrit le déroulement d’une commande prise via une tablette via le client lui-même.*

---

#### Version : 2

#### Auteurs : Rémi DELAVALLE

#### Acteur principal : Bob

#### Pré-conditions : Une tablette avec accès à l'application ets disponible à la table de Bob.

#### Déclenchement : Bob choisit la saisie de commande sur la tablette.

#### Scénario nominal :

1. Bob arrive au restaurant et il s'installe à une table.

1. Il prend sa commande via une tablette.

1. Bob valide sa commande.


#### Post-conditions : Les préparateurs voient la commande de Bob

<div style="page-break-before: always;"> </div>

### <u>Scénario 10 :</u> Les responsables ajoutent/enlèvent des plats à la carte {#scenario10}

> *Ce scénario décrit la procédure d'ajout de boissons, repas ou glaces à la carte.*

---

#### Version : 2

#### Auteur : Rémi DELAVALLE

#### Acteurs principaux : Préparateurs et directeur

#### Pré-condition : Le cuisinier à le droit d'ajouter un plat.

#### Déclenchement : Un cuisinier veut ajouter le plat du jour à la carte.



#### Scenario nominal

1. Le cuisinier ajoute le repas du jour à la carte .

1. Il renseigne les ingrédients et quantités et un prix de vente.

1. Le directeur reçoit une notification concernant la demande d'ajout.

1. Le directeur valide l'ajout à la carte.

1. La carte des repas est mise à jour automatiquement.


#### Post-condition : Le plat est disponible sur la carte.

#### Scénarios alternatifs

4. *A.*
    1. Le directeur modifie le prix de vente.
    2. Retour à l'étape 5.

4. *B.*
    1. Le directeur refuse l'ajout du plat.
    2. La demande d'ajout est supprimée.

<div style="page-break-before: always;"> </div>

## Tableau Sujet / Type / Concept correspondant à nos scénarios {#tableau}

---

|           Sujet           | Type                       | Concept            |
|:-------------------------:|:-------------------------- |:------------------ |
|       **Timoléon**        | Utilisateur                | Client             |
|        **Serveur**        | Acteur                     | Préparateur        |
|        **Alerte**         | Objet                      | Alerte             |
|       **Commande**        | Action / Cas d'utilisation | Commander          |
|        **Entrée**         | Objet                      | Choix              |
|         **Plat**          | Objet                      | Choix              |
|         **Glace**         | Objet                      | Choix              |
|        **Boisson**        | Objet                      | Choix              |
|       **Cuisinier**       | Acteur                     | Préparateur        |
|        **Barman**         | Acteur                     | Préparateur        |
|     **Notification**      | Objet                      | Alerte             |
|        **Glacier**        | Acteur                     | Préparateur        |
|    **File d'attente**     | Objet                      | Ordonnancement     |
|   **Clôturer commande**   | Action / Cas d'utilisation | Clôture            |
|   **Générer addition**    | Action                     | Payer              |
|  **Disponibilité plat**   | Contrainte                 | Contrainte binaire |
| **Modification commande** | Action / Cas d'utilisation | Modifier           |
|  **Demande d'addition**   | Action / Cas d'utilisation | Payer              |
|   **Attribution table**   | Action                     | Attribuer          |
|  **Attribution serveur**  | Action                     | Attribuer          |
|    **Ajout d'un plat**    | Action / Cas d'utilisation | Ajouter            |
|      **Ingrédients**      | Donnée                     | Element du plat    |
|    **Demande d'ajout**    | Action                     | Ajouter            |
|         **Prix**          | Donnée / Contrainte        | Prix               |
|   **Mise à jour carte**   | Action                     | Actualisation      |
|     **Consommation**      | Donnée                     | Element du menu    |
|         **Carte**         | Objet                      | Liste de choix     |
|        **Profil**         | Objet                      | Profil             |

<div style="page-break-before: always;"> </div>

## Diagramme de Cas d'utilisations {#CU}

>>>
Vous pourrez retrouver l'ensemble des diagrammes de cas d'utilisation effectués sur la prise de commande sur notre git. vous pourrez retrouver l'adresse de celui-ci ci-dessous:
https://gitlab-etu.fil.univ-lille1.fr/hulsken/GL
>>>

## Diagramme de Classes {#DC}

---

@import "diagrammes/diagramme.md"

<!--
![](diagrammes/prise_de_commandes/class_diagram_v2.png)
-->

<div style="page-break-before: always;"> </div>

## Diagramme de Séquences {#DS}
### Diagramme de Séquences Simples {#DSS}

---

<!--
![Scénario 1](https://www.plantuml.com/plantuml/img/LPB1Ri8m38RlUGgB7NQg1DjErLI1s6uSaBWYLQ7rm59mCZT1l5AVeo-sjBGilLdnv___RMNTU2q-N8swK8tmOwq_sRlov0r2MHwghcKjP65Lbahfobk1HRurXEmNe1jub62bHe7LyeaSK6uOP636UeJU_g6zTAtJelr4fWyZ_h5KAaQ2bnsTB_va0Yg0o7YgoEbelSWtpXcgj2VBWufsRXn-Nohakjz8ZK6puXadXo-yQevh1qRm-cHmeZwpBC5shyJnJYRj9-szH0ym6Yfx7VIUNdCpoz6cIJ0rDREY64Bdi8szmFGRyCYfOhmOtU9PUaprQ3PDVBFWcHelE8lmO8hvHNlwPcdOLnkKNY_SZ-mIg8aQNA5mrpQgnfcnMiTDusVv0m00)
![Scénario 2](https://www.plantuml.com/plantuml/img/PPAnRi8m48PtFyM93an8b7RAWAZQfHAgAh5qG497V1HNZctC1RLlqpLzZRnOpoI1f1sGBlRt_-V_5uiZO-Ioi6flDC7EUzxwJyM6BS5ciyhhoc4q7cQRZLAOiuymoXwj8SSZm2Cq8_YeASBjz8AiA9weZ6UcdLjeTeLUOrq5ZCWTsJzeyVkfKl8ak5cQzprlRKaAG1WskGaegqVPGmZMvCZ6kxCBXj2AxwQAd4w9rC1wCf-VgGoUdJQ7ak1GZeq51APO65TNQwSfD1BniGYvBmgKGtYJ7aIQBBfW6RnuDZkJR6W8hnqT6SJfXqbr_51x4dvFCVr0MWyMUK2s5MSWENraka1Iepb9e9PGpiiSKqtT2S2I86_qWKe6_F2bH9GBJKUeArjNXLpA-0qvGU7JL-eCafbgLq_wptsY9feTezOcbQuq_NrABq1Rz7yPf2zSkrwp5nlHD2rVL_UtfElBXibyK80_IO-TPb00Vj4rcbh8A7_yNm00)
![Scénario 3](https://www.plantuml.com/plantuml/img/ZPAzRi8m4CTtFyM93an8j6m8LI3QhKCb697GuLoQgumTsHVKL-8vUB6UGmWWEZIJBV_-7pvddWIZD7jdAYu8oX1a5twCi3Y2xNPbJqUFaGDCjbjZq4g8C9Wk7PEN0M02souXn88YF8zxP4NnG4ricNHUTz3B5VgCfsED4UL2rf4k-uwUZ8qMWgSF_gfavneoe9z2mfPhrEZ1T57NZYqA1z-wO5rViyWN-KQcApfwxUjCOKrnpvuW1G-rGxb0iz4Dz4Pxz3gRD6G7nUcOEDB6OoEHm5OXqP_Mox0_onhr_t9eLKEYEx1Odex6N51LvRvJU2zO21o2xQGzCXkDClCeMNo79cleR0eQu73ZspXzBMLwT1rHxJVU3J6BzDG99ExQv9bs-EqJQ2b_24o03UmmQgls4fhdWt39PCWboZRdo7_OP90fFlZueYzyBrsK9TlgVZ1chdp-QNy1)
![Scénario 5](https://www.plantuml.com/plantuml/img/jP8zRiCm38LtdO98XqmfqfyiHX4apbeK1N80Gx6PXe0igH9jz4e-XozMAhNT15cwT2EbZq-Ff3QHTU2cDkf45SBHEJwuByN41g4ezcNVMHt8mQeebD8bkm2pRROpX9Pde2FyX5jmeS803yiHoc-XV80U9oZROsYn2MTeY0VewHTw3ttdTT0yafS70xvQAYNEuUwLFavyC0qg066OIlBQiiXilJTKQYPdPv1ajFT3zVDIeQrIvsfqiLXFhMNWWro3qL2wkjQsmWbxMIn6xh9sVHRF86gAXAaJQiLkEbNf9X5NNMJmvfYEmbPuHTyQolzeAFyVGzP9u5gPMie0TWYVpTnPa9SOQcGE26YXxrhvKhPCYy380Y4OZ9DZcNy8r8fHq4rQrkNhbROHp5os8s8f4S2WI1X0arIYaxg-uxwJGeeOxzC68PbJQYEX_Ebl)
![Scénario 6](https://www.plantuml.com/plantuml/img/RLB1JYCn3BtdAomuzB98NP0uL0ZH8n92ICiHgKeJ3_KgjOV46Utkrt3jTyoFhJCgq0AtnFQpttlsJL6VjMwJsr14w4HqBN-SaYQ4rUfN67ViCmbShbREzLPBWNhF2YUBHxzEg8edu0kyVK1on0m_vyu7bMnb3tdS6T0hrZoL7WRsvHTpvsmkdDxHyqRNgQ83E9wsxFj4mIi9JrqE_licvtE771jzTvWykpwUk81brr7O82GFGRPRpn4TYt5FsEa2xZx2W4KXZhlVuoiKJyK22iY3_1rtpXsr_JhcmLZwKl3V4ySPyRDb8o7h5zmXsmNSSgINQcGC4wdqmhIcH6tW9rd7ECsUz5lO-swkpZvXxaMf8_m1ouHP9tKH9-LFREuqoOGGPvM1fGxeAuIDa3ay-IM3sVxMtJPs6yWyX92QpCaxRnLAK4neyMsdMVgCeE_NKXkWO1xC2yiF4pBDaFVGR7RRMN9eZAqWLclMzv8RquyzLJMjnSJQ1K3ZvjoDFTjX_mS0)
![Scénario 7](https://www.plantuml.com/plantuml/img/VPDDJiCm48NtFiMeB5XLQWC8AKAeQK5ika1aMoboaYcrvDgHFK5m6vRq7BaOjlDJIWDPMPxllNaUEmjBt52zbsmdIeIjrfJhTqQ294AMfKLpKDm83RTPnXWlI1kO9F5A2bGq0MwXNIQWJOa6vhCUMfv3omwAPeDLEezJD6zOcy1rwta7NWrkQJJ6HHrtxGnTRBXOYzSTvR961kwhtD548Igk22PnKbLI59o4Li63LrKdlvanLAK_D-k3Jk-FMM9um3rNRZpoafUby0vig3hIEyNmv4RLV9bnwcxQKSbsAuhT2TJtTCpFdbgfKUmqsZF_m94mQv6tMJWGpoKolprKLr9JtLOBlGzdsoWaaBzLhB_TOzF8wHyLESe9ocumjOlQAWPgQ3OC3-r61SX2AMobbV3he-9yHjmbieIkJUjkJ-pxR4601VaMK8HDQ3x_pVI2rk_zCHuoN50eckRWmV1e65kuL-9_bMy0)
![Scénario 9]()
![Scénario 10](https://www.plantuml.com/plantuml/img/TPDDJiCm48NtFiMeB5XLAh2h46h5WWqWHAHkAzUP98DSst9iYUEmpJboCSPk6aW3MUJFtynxyvnisY1zY4Sj6YeHAcl3mNwAG44ZxFU5wZiZFLcuMUttGWYfWlMmMB_vldFIou3HBq2syFi5M5-Yvv8HV-exBqt8v70_G7Sh8LWHhfwfRi91HnJ01xSAfCWbSB7UEgT9oK3Mv1RIkQ7yTYNGbCcoc3XOFcHe3O-DfPO2j98l7g81fsMOmlVB0TvM5Qa6GKisK2Dm8eh1B9mUvgMZJY6pZCOMoDICb8Ji7TChS9xOO097ViSfK4LPAtj3SMagk_f7RYTrsYyzU9hstdxO6A2Cmzevy77CLnkoT7bIZtMDRHfn97-cwZkDAgsPp9fSUTg9UTynlj6L3b3GEG5W5Gv7MU-v9s_pJEx5bgTCXiZIbp23BaPFp7pwSHtwhsHSyVU4atxdV56tc4nwh2BVwMkPwlzoztv9J6IBwDZpyRUncPGfXTZmcV-tRm00)
-->

@import "diagrammes_sequences/ds1.md"
@import "diagrammes_sequences/ds2.md"
@import "diagrammes_sequences/ds3.md"
@import "diagrammes_sequences/ds5.md"
@import "diagrammes_sequences/ds6.md"
@import "diagrammes_sequences/ds7.md"
@import "diagrammes_sequences/ds10.md"


<div style="page-break-before: always;"> </div>

### Diagramme de Séquences Détaillés {#DSD}

---

<!--
![Scénario 1](https://www.plantuml.com/plantuml/img/TLHDQyCm3BthLuZii5EX-nvXZ9NkEDYWi5EWkB6w6Loxs4xPVb9_H__OvDPDdBIxMVPxJzAJaXSVX0lDIiEtaeHBQyF2_a1GGHFEvxDwjpN2AOjNypc0g8DrM9HJhSY40eN7mn6ja-JmQjn2PkGsrBWz9fqJwBe3VRZTTYsS24TaVf7WZsC0BWcBoNgjLIs2igR0YpVrzHqMkY50P4PGjLeBBgGeFnlAatTX4hmPdr2crWHdjQO3fGiJvVOSPRKIHjBhv3rnsZYHxludzHW9VdyAvz9F71hS9VB36CZ8E3b80nazjxQN-4g7J8qX36AXwOXw6eqosDkbChmFEd_FdZySvq0ji4wLjxcwP017FDzbrfSu4yehokcLeH3ZZT2yUv2XcPlDeCJWXF5BSWmdZtAt3K9fNyMMUkLqdBr2Dv5CeZAvHbn5jM4hSpX0xIY_WrmhasRTAGzZj-KoAbEVGqU7pyeyZGOLilUnGpALMGW_oDbp12HvFlvsmfBEzv4xCXm8losLMnqiv2xsNrPl2lbOUzu-dwnXB7zfevhi2wAyZ5lNUZCaHh61qeIJS2FU6kjuIMo36-KRYci9Bxo2_BVw0m00)
![Scénario 2]()
![Scénario 3](https://www.plantuml.com/plantuml/img/bPJBRjim44Nt_8g1kkZAWDlq1I4k8jXU5AZZmdci2XWqDR9OqAHAKK5_oT_X7-j8ecHASO9MApxkkHpU8NHJEcvTTL0ibob2PepRcJ_CIQSGjjixSJfgRgM1g-sMCSQ5CnQYUAuaQXS1Bq4qGp0sHGllfhta3kqJLhRHbEtOYzwVHJ_iwLXmorsdB2nsSw_-CcLK4KH9KIWfk9D6H_3ckzpdRgSgP40V8KuAMN0g98eVAmmFFq-zuzNq0ZGtsbcZ5BRGUUgX3vUXmu7h51V9sbFzt6CVNyC6Z0S-NGBe2i-I6grv_FEKeKxh5ZBVcCdNFluOxj4Uf4OeZOP2STU9hYU1Q85jGULRgI0z7KjfyQVcbRC88ZSbNhJkxr6H_rvnGGmwce7WsUd8M2SbAcX93CjKEWJ5GNW75coJE6W5dP9pkwTHA0y4ZVpSWnWs-Bl2aRsmI97rGXOIWG4RR5nF9Y7HdnYkaowilTtgbFtzAUl1_PCiao8VblXYMCalKzNNmJPLe8I9Q-9-BRQLIMKcyPzZUoXIFagDSUMWbBwRzHiT6epV8pLMFnawarUmuvPCclT0bMlZwc8OgX9hnxRw_tEi6OdscQLE6HjpP1N-Lbv8V3Q3pV9-_R21vUtZ-XlCrwjLShjOmcp6s0qPqq_oBm00)
![Scénario 5]()
![Scénario 6](https://www.plantuml.com/plantuml/img/XLJBZjim3BphAuZqa4i3fAyz68jYW_QomA9Te8_J0e4YCHiMYkHAbD7sQthDT_Z7IZbEx3o0ta9wXXoHmzmbrf7prgaDMOHr2BmAlnGJEuJbyejfTrv72d2pN2fL2vOCrTepJAglUkMG6IUW4nm22D5YX5TpfGs7AB37sEw4g1bpxA3ZH0-_cIibVM6og6j7HZC5Fu4N3_IyuPNBg01EUt_FUD9-5FSbNyylI1-2vnYSmxsE8UmfRwvG9CAFYyzxGX_qyBUNS95nyTopN4z-DrVeRPcryg68RYGvA9BA3nfCs6wrbxrWOh3jxaVx5vAc90a6z4tutUvA6IWbb3hlD7j_EkiAFWMcDNLqlLwJsI2ueOtw3_jHNgDJmZzFtax9FyjNI-ZvWdSkf89xR-bdbcx2ivJgu6b5ZaJ-DTMZpLJ0KHDVPOvWXNJOJWNVQgjv_xII70DlPxCZyhp2s4J3hEpLtaVWxUmwxoKif2ntixROpVV9YwAolr9rchsiBJUeCvXDe8CHOl7yyPp41_U6G8xHk3BgpWbQlC84IOQLTF5W37L4uEC1v49861kPftnlEgQRek-fKSmZj-vDkJC1s2p5wZh48dLmNMPvR3gns9tyb7-BVm00)
![Scénario 7](https://www.plantuml.com/plantuml/img/ZPLBRjim48RtFCN0NNHbmtOVQOMuYEmKHO40BUosgm06BOrZ0ZJ9KcJGtgRB9DVGnKf9b4IviXgj-FZ-8UUVaNIL6QgDFN9oO2d2Nagpax-8OOOZRBUR97yKL3C95zij8JGnKiCeZbQSeJ0Ze1bKmnYaJb73R5f3ot-XfOVcqoRKPXPjKD-ZrINdnpCFlcgYRUPztDnphrr0TsrtCwKuIwXXKepWnGsxEvWTjqZ0FSeboXAcg30mYdvO30EsKn_opRH7j9B2QCavLg9swaLl-qJVw8xZTVobbDGJBxZeF-Luf29jDC7SozuDoJeQBtW_9IZIehAaBiNuG-js1DTOuVmbJLDM-4UQNKS6zaJmoVL4_g0xS00uF30cWjM1whiE76oNS9jU16lyQVCdSyAtH20eOakH6MsP0KuXyUiT_d8yRWJXmU6wuy84ggsQR7su77TzYFTxbXowD_NcEZGqLmhHYtLhy9N-nlEkhxWqjZ0zI7J8zHvyoFUDLKgpurd1gL_TM4rRHt33TbLpK335wccG6YLaCfcGnG9YfVE73Anm4fKXkC8QFAeC5eiI8VKNfdLhxixvwA8Ye75yrGtMULoTs52d7gxHrKkNDSFiLfHq1YdBb1Ii63-ZZqjHe3dlHD7AQ8OL7KSwFTWzV8tYNhAUM4skfztvVqMHeBUsR6PCYjSE8IaN8VyJM3haQLQCsteFMBZaqbdIsnfTwxwhb9fdz92GvPNtnca-9wmHG6hhD9QtGg5rwJmL_KBBDFD7Dsg8c90hztLqFy6_)
![Scénario 9](https://www.plantuml.com/plantuml/img/ZPJFYjim4CRlUeh1FVGKIFzJKy8kkpqKIblOiYT3KEJ9Pa2MN6cyj8-KvyYBTMIhYUDus_fa3VERR-ORsLUHTU2kiMf7DSBMUzxudug9BS9wVMSEUwS3UNY_NYkbj64Ve2XlBA7Z0dI4uHLyg370Y-KnvLiux5iTD6CN-iHn8AU_MoebSb1SjwqbevcyA-3PPthOySPsg40UOPWCjLfKYlA-m-zwOv4PHqrSHBF0o-LCYHllE7XhSUZhTCpGgtceQRIhyVRwQwQEvuoz_XjsncJWpHmWarmuDubb_ErIeQlJjbIUUR5QpJXHmfscI0YTGv20LCB_9g2rca_PiydtsgQx4xqpEq_IpcMIa2ERI_Ze7Zs1nGZrOS-QRAoIBrQ3oHx9K2UWnqz-bt2BWv7sERg03nGvO2D2bKC76nq5Dm75hIEdnWL6zSxY7nQBVm930vzSnC3mHwr6wS3_UWAUJY-7BOKcpLiv8_leB_vaujN5saluufcsifTirP4SWqyiAMls-S9Nxgo0cceb_LdnuIDDo_P1glWE7YbsADgpUq-ZJrf0q1sOFbYv7ztPrcL_aQ4D5DDLJU6MfV2LN7JvH_q6)
![Scénario 10](https://www.plantuml.com/plantuml/img/ZLNBgjim4DthAuPqqTM5bBvDAJUa3mejlTHmLuMWs9CR5KLoPRdS_ast_Wx_M4UoBR-Ka2o2vJddpCoPKN9RMcviTPBiA7A4WzPshn-P5LOYx7PfrjIA6w7XsNgtOupnp6e3g-JED7N13RTOcHNm4iOlG9iS3L42_7DJ6wwiHtRF0RHcZ5B2QbCKKcJS2grMyEIhU3ZQlQoG0Nr8sOfC58wtIkuhNEIVlUlKdwyZz4_Qd2h9XS6KYrBWdUHjPR509_GY9hJLoXej9ROb3CUEz396Sg8VDjzRqzhd3lxg73nWE-3hQ35qmbwuFtI4Dp42EJOUot3iI6_N35Nkje6nYRKtxnTk9x0zQhBCGkcSCr0fAAXWDWSID-Ro0lVkvYOEdA4YbMmE1v4T4QHRvrxXYWvy4akq4eHwe5WkaCn0zmeA8nuN6gE19t3FfRj1BTqbzfjSChOrI0m_FpPY4D-FbAmZsQRsMMOOvuBdHOXkkWbyKIKQstD_AbImvoMo74l2_rraxHM9FHSTBK027zKVBQYRfvoYL3rrbb6PlYSsGX9l80NdEIXjnQ6xpMCyJMp0fqqjCNCGjIJDiaoyJZ7mJCotYKK6VrTeCU1O7necu5eRAVM0OFyP0w_m3yCrkEnONnkN5bBHRnpG56cRCcqCzKjtU2GoIVTDv-GSXarrj_qSDYngcz91BrWzRGHEFb5JUzgq__2RGstzqjNWE3J_t7Gp5v_pd9qzSLwAZmNef2SN6f0CPOdEDeE7glHRwmguuDUFEV0g1xmyc_SzR5fQ5UJ-QUpjcSsPQaogO-UxL3bZj_HDVzV_0G00)
-->

@import "diagrammes_sequences_detailles/dss1.md"
@import "diagrammes_sequences_detailles/dss2.md"
@import "diagrammes_sequences_detailles/dss3.md"
@import "diagrammes_sequences_detailles/dss5.md"
@import "diagrammes_sequences_detailles/dss6.md"
@import "diagrammes_sequences_detailles/dss7.md"
@import "diagrammes_sequences_detailles/dss9.md"
@import "diagrammes_sequences_detailles/dss10.md"


<div style="page-break-before: always;"> </div>

## Maquettes {#maquette}

### Maquettes de l'interface Gérant {#maquetteGerant}

---

[:open_file_folder: open pdf file](./maquette/maquetteGerant.pdf)

<!--
![](./maquette/maquetteGerant/maquetteGerant-1.jpg)
![](./maquette/maquetteGerant/maquetteGerant-2.jpg)
![](./maquette/maquetteGerant/maquetteGerant-3.jpg)
![](./maquette/maquetteGerant/maquetteGerant-4.jpg)
![](./maquette/maquetteGerant/maquetteGerant-5.jpg)
![](./maquette/maquetteGerant/maquetteGerant-6.jpg)

<div style="page-break-before: always;"> </div>
-->

---

### Maquettes de l'interface Préparateur {#maquettePreparateur}

---

[:open_file_folder: open pdf file](./maquette/maquettePreparateur.pdf)

<!--
![](./maquette/maquettePreparateur/maquettePreparateur-1.jpg)
![](./maquette/maquettePreparateur/maquettePreparateur-2.jpg)
![](./maquette/maquettePreparateur/maquettePreparateur-3.jpg)

<div style="page-break-before: always;"> </div>
-->

---

### Maquettes de l'interface Serveur {#maquetteTabletteServeur}

---

[:open_file_folder: open pdf file](./maquette/maquetteTabletteServeur.pdf)

<!--
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-1.jpg)
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-2.jpg)
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-3.jpg)
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-4.jpg)
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-5.jpg)
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-6.jpg)
![](./maquette/maquetteTabletteServeur/maquetteTabletteServeur-7.jpg)

<div style="page-break-before: always;"> </div>
-->

---

### Maquettes de l'interface Client {#maquetteTabletteClient}

---

[:open_file_folder: open pdf file](./maquette/maquetteTabletteClient.pdf)

<!--
![](./maquette/maquetteTabletteClient/maquetteTabletteClient-1.jpg)
![](./maquette/maquetteTabletteClient/maquetteTabletteClient-2.jpg)
![](./maquette/maquetteTabletteClient/maquetteTabletteClient-3.jpg)
-->

<div style="page-break-before: always;"> </div>

## [Annexe] *Glossaire métier* {#glossaire_metier}

>> *Ce glossaire donne une définition à chaque terme métier utilisé dans la conception de l'application.*

---

#### Carte
Ensemble des consommations proposées aux clients.

#### Consommation
Ensemble des entrées, plats, desserts, boissons, disponible pour le restaurant.

#### Commande
Les consommations demandées par une table.

#### Client
Personne commandant des consommations dans le restaurant.

#### Générer l'addition
A partir des consommations d'une table ou d'un client, génère une liste de consommations, avec leur prix, et calcule le total.

#### Serveur
Personne s'occupant d'une ou plusieures tables.

#### Table
Composée de plusieurs clients.

#### Tablette
Outil éléctronique permettant d'accéder à l'application.

<div style="page-break-before: always;"> </div>

### [Annexe] *Glossaire technique* {#glossaire_technique}

>> *Ce glossaire donne une définition à chaque terme technique utilisé dans la conception de l'application.*

---

#### Alerte

Message textuel pouvant être reçu par l'ensemble des employés de l'entreprise.


#### Carte

Ensemble des différents menus proposés par le restaurant.


#### Clôturer une commande

Terminer de manière définitive une commande. La commande est détruite, plus aucune action la concernant n'est possible.


#### Commande

Un ensemble de consommables reservés par un client.


#### Menu

Liste des plats/boissons/desserts proposé par l'entreprise.


#### Notifier

Envoie d'une alerte pour avertir d'un évènement.


#### Poste

Lieu de travail d'un préparateur (cuisine/bar/"glace")


#### Préparateurs

Employé du restaurant s'occupant de la préparation et de l'envoi des commandes.


#### Profil

Profession d'un employé de l'entreprise. (Barman/cuisinier/glacier/serveur/directeur)


<div style="page-break-before: always;"> </div>

## [Annexe] *Glossaire de l'ingénierie des besoins* {#glossaire_ingenierie_besoins}

>> *Ce glossaire définit chaque terme technique utilisé dans les étapes de conception de l'application .*

---

#### Alerte

Message textuel pouvant être reçu par l'ensemble des employés de l'entreprise.

#### Notification

Alerte pour avertir d'un évènement.

#### Profil

Profession d'un employé de l'entreprise. (Barman/cuisinier/glacier/serveur/directeur)

#### Modèle

Partie de l'application contenant les données devant figurer dans l'interface graphique.

#### Vue

Partie frontale de l'application, aussi appelée interface graphique.

#### Contrôleur

Partie de l'application où sont codées les actions pouvant être effectuées par l'utilisateur

#### DAO : Data Access Object

Patron de conception permettant de regrouper les accès aux données dans une partie distincte de l'application.

#### Boundary

Interface permettant de faire le lien entre les différents acteurs au sein d'une application.

#### BLL : Business Logic Layer

Couche métier de l'application.

#### UI : User interface

Interface graphique de l'application

#### UX : User Experience (Expérience Utilisateur)

Expérience de l'utilisateur utilisant l'application. Celle-ci est prise en compte lors de la phase conception de l'interface graphique dans laquelle nous identifions les besoins des utilisateurs.

#### Paquetage

Diviser l'architecture applicative en paquetages permets de distinguer les différentes partie de notre application et de séparer les différentes fonctionnalités proposées.


<div style="page-break-before: always;"> </div>

### [Annexe] *Récapitulation de commandes `GIT` usuelles* {#recap_git}

---

+ `git status` => voir la liste des fichiers et commits différents entre le repo local et le repo distant
+ `git add <fileName>` => ajout/indexation du fichier `<fileName>`
+ `git commit -m "type(where): what"` => nomination du/des changement(s) ajoutés précédemments (example en Karma commit)
+ `git merge <branchName>` => fusionne la branche actuelle avec la branche `<branchName>`
+ `git push` => ajouts des différents commits sur le repo distant
+ `git pull <branchName>` => merge la branche git distante `<branchName>` avec la branche locale (Si ce paramètre n'est pas précisé cela se fera sur la branche actuelle)
+ `git fetch && git rebase` => applique les différents commits du repo distant sur le repo local
+ `git checkout <fileName>` => supprime les modifications non indexés de `<fileName>`
+ `git branch` => liste toutes les branches du repo locales
+ `git branch -d <branchName>` => supprime la branche `<branchName>`
+ `git checkout <branchName>` => se déplace sur la branche `<branchName>` locale
+ `git checkout -b <branchName>` => crée une nouvelle branch `<branchName>` et se déplace dessus
+ `git reset HEAD` => supprime les commits locaux
