<h1 style="text-align:center">Génie Logiciel
<br/>
Sujet 1 - Prise de commande dans un restaurant</h1>

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

> Ce projet porte sur l'analyse et la conception d'une application de commande pour un restaurateur.

> L’objectif de l’application est de faciliter la communication entre les différents membres de l’équipe restauratrice et ainsi d’améliorer leur coordination. La réactivité de l’équipe sera améliorée.

---

## Table des matières

1. [Tableau de suivi des tâches](Tableau_des_taches.ods)
2. [Bilans de séance](./README.md)
    1. [Bilan 11/09/2018](Bilan_de_seance/11_09_2018_bilan_seance_1.md)
    2. [Bilan 18/09/2018](Bilan_de_seance/18_09_2018_bilan_seance_2.md)
    2. [Bilan 25/09/2018](Bilan_de_seance/25_09_2018_bilan_seance_3.md)
3. [Scénarios possibles d'utilisation](scenario/schema_scenario.md)
    1. [Prise de commande et notifications `Cas nominal`](scenario/scenario_1.md)
    2. [La commande se déroule comme prévu `Cas nominal`](scenario/scenario_2.md)
    3. [Le client ajoute un élément à sa commande](scenario/scenario_3.md)
    4. [La commande est modifiée](scenario/scenario_4.md)
    5. [Déroulement des commandes de plusieurs clients distincts](scenario/scenario_5.md)
    6. [Le plat commandé n’est plus disponible](scenario/scenario_6.md)
    7. [Ajout ou retrait des tables disponibles](scenario/scenario_7.md)
    8. [Attribution d’une table à un serveur](scenario/scenario_8.md)
    9. [Le client saisit lui même sa commande via une tablette](scenario/scenario_9.md)
    10. [Les responsables ajoutent/enlèvent des plats à la carte](scenario/scenario_10.md)
4. [Tableau Sujet/Concept/Type](tableau_sujet_concept_type.md)
5. [Diagramme de Cas d'utilisations](./)
6. [Diagramme de Classes](./)

+ [Glossaire métier](glossaire/glossaire_metier.md)
+ [Glossaire technique](glossaire/glossaire_technique.md)
+ [Récapitulation de commandes `GIT` usuelles](outil/recap_git.md)

<div style="page-break-before: always;"> </div>

### Bilan des tâches effectuées lors de la scéance 1
##### *11/09/2018*

---

- ***Choix du sujet :*** prise des commandes d’un restaurant
- ***Brainstorming :*** idées des features à développer
- Conception et rédaction des différents scénarios
- Définition des scénarios à préparer pour la séance du 18 septembre.

<div style="page-break-before: always;"> </div>

### Bilan des tâches effectuées lors de la scéance 2
##### *11 / 09 / 2018*

---

#### Recherche CU, Classes et Acteurs

+ Analyse de scénarion **TinCar**

| SUJET | CONCEPT | TYPE |
| :------------- | :-------------: | :-------------: |
| Alice | Conducteur | Acteur |
| Aller | Trajet | Concept |
| Parents | Destination | Objet |
| Nb places | X | Donnée |
| TinCarXsite | Application | X |
| Frais & compagnie | Motivation | Objectif |
| Utilisateurs | Utilisateur | ConceptXObjet ? |
| Proposer un trajet | Action | ActionXObjectif |
| Chercher un trajet | Action | ActionXObjectif |
| Itinéraire | X | Donnée du trajet |
| Date | X | Donnée du trajet |
| Formulaire | Message | Objet de médiation |
| Point de départ | X | Donnée du trajet |
| Point d'arrivé | X | Donnée du trajet |
| "Continuer" | Validation | Action |
| Passager | Passager | Acteur |
| Passager | Passager | Acteur |

+ Diagramme de CU **TinCar**

![Diagramme de CU TinCar](http://www.plantuml.com/plantuml/png/PSuzZeD030NWtgTuvL9m0OeL4XT0shs0DJWmOPX17ayHHRbxG0cXI6SzV_vfix5QMG85kHWiGVqu6GQluiodI7dsSMNb1IkxcKVviriGx6sEOn2YfajnACwaQ4DDppblQYlfO_3lOyUAEm4_lQOrPL6K25E-YbNWVERLZhf9r4tVwCWhUX2TTr7NlpWMqFk5LtfCK2kRNi8J)

<div style="page-break-before: always;"> </div>
<div style="page-break-beore: always;"> </div>

### Bilan des tâches effectuées lors de la scéance 3
##### *25 / 09 / 2018*

---

#### Recherche CU, Classes et Acteurs

+ Analyse de scénarion **TinCar**

| SUJET | TYPE | CONCEPT |
| :---- | :--: | :-----: |
| Bob | Acteur | Passager |
| Mennecy | Objet | Destination / Objet de recherche |
| Budjet | Contrainte | Max |
| Page de recherche | Interface | Recherche de trajets |
| Lille | Objet | Départ / Objet de recherche |
| Résultats | Objet | Liste Résultats |
| Prix | Donnée / Float | Prix |
| Le trajet d'Alice | Objet | Choix |
| Trier | Acteur | Trier / Ordonner |
| Date | Donée / Contrainte | Critère |
| Profil d'Alice | Objet | Profil |
| Taille des bagages | Données / contrainte | Contrainte |
| Niveau d'experience | Donnée | Donnée du profil |
| Réserver | Action / Cas d'utilisation | Réserver |
| Payer | Action | Payer |
| Demande de réservation | Objet |  |
| Mail de récap | Objet mail |  |

<div style="page-break-before: always;"> </div>

+ Diagramme de CU **TinCar**

![Diagramme de CU TinCar](http://www.plantuml.com/plantuml/png/RP91Si8m34NtEeMMOG47OC7GikYgCmpb0Y8HmSLnKjdf34CvKC_HYzL4eJGcYqoi_zz4NtAMFf24jh9WUHymr2YcF0GiZ70UJEt07urhIAZ2Xl8ZbVmMJfRnQfChBGFCdwp9UOxaiJl1_BdUTMLynuBSHwks7W4w3AVJhmM-ShKJXaWEQe2_1hWrRaM2Pm34RCFvWIK-4oJ_lxoQB-olcR5WZutKUsEzOgKQwqwRG6Jldp_72Z5Rqub5QJsglFdvzYoVBDWw34Bl71GILdshMazprLZJiTg_PrNMzZswgfrlRU07EE-D8RuL4r7B7kKsiiwcpgt_pSE2axIzSOzxWGj0flkUnEKFbZdGq-qb0ivcYyVOurIoYNjBzTES8qG_BcJwCsb2lR5XwZ4jlRGbkwAjx2y0)

+ Diagramme de classes

![Diagramme de classes](http://www.plantuml.com/plantuml/png/bPBDJiCm48JlVeezygD8SEsX2C45YKf8HRrldL5hI9neRLVbfm-KvyYB4P6iafGJbyWxysKoTXpUdQzPk2HRS0ZtCOhRfeWdM_cr-mJTcDwX5SgjGATdXwJhb-x1EuZE6-oTBK1VXeWosbH5Ah7Yew6J8W-LpvEDIA9K3IbTc22lmc-8QkSSyOYQ9VRp7abcWY2ov4EMkECyoGUsqLL-hEnGmiSrvE3iKFMwapyWT75tIOlvMoTZZ3RAij_TTqZUDds1FmwBk4FROBIMkbfGsqIk4UZAcEb1P9cUNCTiUSSxX7DY3BabguOO_GLpf1x4OCnqDnqp2VsFfLyvQ_MzrCkXn4py0G00)

---

#### Bilan TP

- ***Diagramme use case :*** Description des principales fonctionnalités de l'application sous forme de diagramme.
- ***Diagramme UML :*** Premier jet d'équipe sur le diagramme UML.
- ***Organisation :*** Répartition des tâches.

<div style="page-break-before: always;"> </div>

### Bilan des tâches effectuées lors de la scéance 4
##### *02 / 10 / 2018*

---

#### *<u>Note de TD :</u>*

+ **L'hippodrome (CU)**

![L'hippodrome (CU)](http://www.plantuml.com/plantuml/png/NP11QiGm34NtEeMMyM8kuDN0K2ZTj30d48wQYd7i8Dk5Kdht4giD9hllzuI_hMkffBMj4IA_LwmPLPQFYhCeXoevGNb8saXfnOt2WnQ-rw_8k6jAIsG0Vul2gNgaWXR1l-JmOEt88lYdq5Iu8ulWNtMX98KgDviT0S3HWS-oRNdMl39-0o1EzoQVoZXpmP2R5YuEgVppMqTk7tmZ5LQJbZlU9rIC7uTT_Bs0zNpte1p03y1aVtLukPnxHtMqmcIRC7fqJhQC4uMXhPjnCmwkdEQsnby0)

+ **La hiérarchie des chevaux**

![La hiérarchie des chevaux](http://www.plantuml.com/plantuml/png/RKzBIWGn4Dtd54MMOa1TIYE8A2W8WbwWZ0KTpAT99xqOva1pZxdOTAShanwONUhbVTuR_uqVCA83RN4SdrEAvZSdUjV1VviTmPqe7_0JGnu8CvylFKre1L-VQ8cVhmbjy7nyXMpH-4fx8qVspFp8ZdpQC8tkIGXHaq3UImXAWNoulP6S28-WWqzcKGg6khrIQuKjm64LaxE5KeidLvoTXkCXNY5mivdW2a4itgifhsj0NSXf1MJz1ROTo1fGJwtA7qrb4qTtJT0-Jm00)

<div style="page-break-before: always;"> </div>

+ **Les produits pour chevaux**

![Les produits pour chevaux](http://www.plantuml.com/plantuml/png/NOzDIaD13CVtEKMObKeBxROxyGC44S4JnDSWeRvCpMIAA1wev-Z5dBvEi-ZgvIM__yT0sOXkoMZ4uPDAkNKtUQ_EJqFMD_bXN01C5torlAxY-0k8B-JLU8KFMaSsRflYUTZ0NsUVvKDv8hyggOiVzcrky65lkKrRa--0x_8uagwv_zxpJahux8oaP0KunwVb36yIpZEczZbhSOMji0khG-pIueGUsMNgnbVTQ1RQwqQS6aFaHSnyaaR5HngEBxyuX-mV)

---

#### *<u>Note de TP :</u>*

- travail sur les diagrammes de Cas d'Utilisation
- travail d'équipe sur des choix de conception lors de diagramme UML
- veille technologique et recherche sur des solutions d'exports pdf

<div style="page-break-before: always;"> </div>

## Schéma de l'avancement des différents scénarios d'utilisation de l'application

:warning:<span style="background-color: #ff6d6d; align-item: middle">Ce schéma n'ayant pas été terminé, nous avons fait le choix de le sortir de ce premier rendu.</span>


<div style="page-break-before: always;"> </div>

### <u>Scénario 1 :</u> Prise de commande et notifications `Cas nominal`

> *Ce scénario décrit le déroulement du début à la fin d’une commande et du repas d’un client.*

---
1. Timoléon se rend au restaurant. Le serveur reçoit une alerte sur sa tablette et va prendre la commande de Timoléon.

2. Timoléon souhaite une entrée, un plat, une glace ainsi qu’une boisson.
Le serveur saisit la commande sur sa tablette.

3. Les cuisiniers reçoivent la commande de l’entrée et le plat et commencent leurs préparations.
Le barman est notifié de la commande de boisson.
Le glacier reçoit la commande de la glace dans la file d’attente.

<div style="page-break-before: always;"> </div>

### <u>Scénario 2 :</u> La commande se déroule comme prévu `Cas nominal`

> *Suite du scénario 1 après l’étape 3 lorsque le client ne change pas d’avis et que le serveur ne se trompe pas dans la saisie.*

---

***[Scénario 4 optionnel]***

4. Le serveur est notifié lorsque la boisson est prête.
Le serveur amène la boisson à Timoléon.

5. Le serveur est notifié lorsque l’entrée est prête. Il la sert à Timoléon.
Lorsque Timoléon a fini son entrée, le serveur débarrasse la table. Il sert le plat.

6. Lorsque le serveur débarrasse le plat, il notifie le glacier qu’il doit préparer la glace.
Le serveur apporte le dessert.
Timoléon finit son dessert, il est débarrassé.

***[Scénario 3 optionnel]***

7. Le serveur clôture la commande qui disparaît de l’application et peut générer l’addition.

<div style="page-break-before: always;"> </div>

### <u>Scénario 3 :</u> Le client ajoute un élément à sa commande

> *On reprend à l’étape 6 du scénario 1. Le client demande un dessert supplémentaire.*

---

7. Le serveur demande si Timoléon désire autre chose.

8. Timoléon répond qu’il désire une autre glace ainsi qu’un café.

9. Le serveur notifie le barman et le glacier qui prépare la glace sans attendre.
Le serveur amène la glace et le café à Timoléon.

<div style="page-break-before: always;"> </div>

### <u>Scénario 4 :</u> La commande est modifiée

> *Ce scénario peut intervenir à tout moment. Ici on le fera intervenir à la suite de l’étape 3 du scénario 1, avant le service.*

---

:warning:<span style="background-color: #ff6d6d; align-item: middle">Ce scénario sera explicité dans une version ultérieure de notre logiciel. </span>

<div style="page-break-before: always;"> </div>

### <u>Scénario 5 :</u> Déroulement des commandes de plusieurs clients distincts

> *Ce scénario décrit le déroulement des commandes et du service en fonction de l’ordre d’arrivée des différents clients. On reprend après l’étape 3 du scénario 1. Le but est de montrer que le logiciel traite les commandes de manière séquentielle.***

---

4. Bob arrive au restaurant, le serveur prend sa commande : entrée, plat, dessert.

5. La commande est envoyée à la cuisine (resp. bar, resp. glacier). La commande de Bob apparaît après celle de Timoléon dans la file des plats (resp. boisson, resp. glaces) à préparer.

6. Bob est servi après Timoléon.

<div style="page-break-before: always;"> </div>

### <u>Scénario 6 :</u> Le plat commandé n’est plus disponible

> *Ce scénario intervient apres que le client ait fait son choix de plat, a la place de l'étape 3 dans le scénario 1*

---

1. Les cuisiniers recoivent la commande du client. Il s'appercoivent que le plat n'est plus disponible, ils envoient une notifications pour cet évenement.

2. Le serveur est notifié de la situation, il informe le client de l'indisponibilié de son plat et lui propose de modifier son choix

3. Le serveur modifie la commande et le cuisinier est notifié à nouveau.  

<div style="page-break-before: always;"> </div>

### <u>Scénario 7 :</u> Ajout ou retrait des tables disponibles

> *Ce scénario peut se dérouler à tout moment du service.*

---

1. Timoléon, client du restaurant, demande l'addition à son serveur.

2. Lorsqu'il paye, la libération de la table est prise en compte par l'application.

3. Dès lors, un jeune couple entre dans le restaurant et demande une table.

4. Le serveur fait donc une demande à l'application pour une table pour 2.

5. Celle-ci lui répond qu'une table a été libérée il y a peu, et le serveur peut donc la réattribuer au jeune couple.

6. Une fois installés à leur table, notre serveur peut prendre en compte dans l'application que la table n'est plus libre.

<div style="page-break-before: always;"> </div>

### <u>Scénario 8 :</u> Attribution d’une table à un serveur

> *Ce scénario décrit l'attribution d'un nouveau client à un serveur*

---

1. Sam rentre dans le restaurant. Un serveur est notifié de son
arrivée et va l'accueillir.

2. Le serveur place Sam à une table. Il rentre sur sa tablette le
numéro de la table.

3. La table est automatiquement attribuée au serveur assigné à cette
table et le serveur en est notifié.

<div style="page-break-before: always;"> </div>

### <u>Scénario 9 :</u> Le client saisit lui même sa commande via une tablette

> *Ce scénario décrit le déroulement d’une commande prise via une tablette via le client lui-même.*

---

1. Bob arrive au restaurant. Il s’installe à une table. Il prend sa commande via une tablette correspondant à sa table.

2. Lorsque Bob valide sa commande, les plats, boissons et desserts sont transmis à leurs postes respectifs (cuisine, bar, glacier).

3. Reprise au point 3 du scénario 1 et 2 (cas nominaux)

<div style="page-break-before: always;"> </div>

### <u>Scénario 10 :</u> Les responsables ajoutent/enlèvent des plats à la carte

> *Ce scénario décrit la procédure d'ajout de boissons, repas ou glaces à la carte.*

---
1. Par souci de temps, le directeur autorise ses cuisiniers à ajouter des repas à la carte.

2. Les cuisiniers ajoutent à la carte le repas du jour.

3. Ils renseignent les ingrédients et quantités et un prix de vente.

4. Le directeur reçoit une notification concernant la demande d'ajout.

5. Le directeur modifie le prix de vente et valide l'ajout à la carte.

6. La carte des repas est mise à jour automatiquement.

<div style="page-break-before: always;"> </div>

## Tableau Sujet / Type / Concept correspondant à nos scénarios

---

| Sujet                     | Type                       | Concept            |
| :-----------------------: | :------------------------: | :----------------: |
| **Timoléon**              | Utilisateur                | Client             |
| **Serveur**               | Acteur                     | Préparateur        |
| **Alerte**                | Objet                      | Alerte             |
| **Commande**              | Action / Cas d'utilisation | Commander          |
| **Entrée**                | Objet                      | Choix              |
| **Plat**                  | Objet                      | Choix              |
| **Glace**                 | Objet                      | Choix              |
| **Boisson**               | Objet                      | Choix              |
| **Cuisinier**             | Acteur                     | Préparateur        |
| **Barman**                | Acteur                     | Préparateur        |
| **Notification**          | Objet                      | Alerte             |
| **Glacier**               | Acteur                     | Préparateur        |
| **File d'attente**        | Objet                      | Ordonnancement     |
| **Clôturer commande**     | Action / Cas d'utilisation | Clôture            |
| **Générer addition**      | Action                     | Payer              |
| **Disponibilité plat**    | Contrainte                 | Contrainte binaire |
| **Modification commande** | Action / Cas d'utilisation | Modifier           |
| **Demande d'addition**    | Action / Cas d'utilisation | Payer              |
| **Attribution table**     | Action                     | Attribuer          |
| **Attribution serveur**   | Action                     | Attribuer          |
| **Ajout d'un plat**       | Action / Cas d'utilisation | Ajouter            |
| **Ingrédients**           | Donnée                     | Element du plat    |
| **Demande d'ajout**       | Action                     | Ajouter            |
| **Prix**                  | Donnée / Contrainte        | Prix               |
| **Mise à jour carte**     | Action                     | Actualisation      |
| **Consommation**          | Donnée                     | Element du menu    |
| **Carte**                 | Objet                      | Liste de choix     |
| **Profil**                | Objet                      | Profil             |

<div style="page-break-before: always;"> </div>

## Diagramme de Cas d'utilisations
## Diagramme de Classes

>>>
Vous pourrez retrouver l'ensemble des diagrammes effectués sur la prise de commande sur notre git. vous pourrez retrouver l'adresse de celui-ci ci-dessous:
https://gitlab-etu.fil.univ-lille1.fr/hulsken/GL
>>>

<div style="page-break-before: always;"> </div>

## Glossaire technique

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

### Glossaire technique

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

### Récapitulation de commandes `GIT` usuelles

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
