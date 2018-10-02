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

+ Diagramme de CU **TinCar**


```mermaid
graph LR

classDef p fill:#fff, stroke-width: 0;

p1(Alice fa:fa-user)
class p1 p
p2(Bob fa:fa-user)
class p2 p
p3(Banque fa:fa-user)
class p3 p
p4(Membre fa:fa-user)
class p4 p

subgraph TinCar
t1(fa:fa-search Recherche de trajet)
t2(fa:fa-sort Trier les recherche)
t3(fa:fa-eye Consulter un profil)
t4(fa:fa-address-book Remplir un profil)
t5(fa:fa-map-signs Réserver un trajet)
t6(fa:fa-credit-card Payer)
end

a1(fa:fa-search Recherche)
a2(fa:fa-address-book Gestion des profils)

p1 --> p4
p2 --> p4

p4 --- a1
a1 -.-> t1
a1 -.-> t2

p4 --- a2
a2 -.-> t3
a2 -.-> t4

p4 --- t5
p4 --- t6
p3 --- t6
```

![http://www.plantuml.com/plantuml/png/RP91Si8m34NtEeMMOG47OC7GikYgCmpb0Y8HmSLnKjdf34CvKC_HYzL4eJGcYqoi_zz4NtAMFf24jh9WUHymr2YcF0GiZ70UJEt07urhIAZ2Xl8ZbVmMJfRnQfChBGFCdwp9UOxaiJl1_BdUTMLynuBSHwks7W4w3AVJhmM-ShKJXaWEQe2_1hWrRaM2Pm34RCFvWIK-4oJ_lxoQB-olcR5WZutKUsEzOgKQwqwRG6Jldp_72Z5Rqub5QJsglFdvzYoVBDWw34Bl71GILdshMazprLZJiTg_PrNMzZswgfrlRU07EE-D8RuL4r7B7kKsiiwcpgt_pSE2axIzSOzxWGj0flkUnEKFbZdGq-qb0ivcYyVOurIoYNjBzTES8qG_BcJwCsb2lR5XwZ4jlRGbkwAjx2y0](http://www.plantuml.com/plantuml/png/RP91Si8m34NtEeMMOG47OC7GikYgCmpb0Y8HmSLnKjdf34CvKC_HYzL4eJGcYqoi_zz4NtAMFf24jh9WUHymr2YcF0GiZ70UJEt07urhIAZ2Xl8ZbVmMJfRnQfChBGFCdwp9UOxaiJl1_BdUTMLynuBSHwks7W4w3AVJhmM-ShKJXaWEQe2_1hWrRaM2Pm34RCFvWIK-4oJ_lxoQB-olcR5WZutKUsEzOgKQwqwRG6Jldp_72Z5Rqub5QJsglFdvzYoVBDWw34Bl71GILdshMazprLZJiTg_PrNMzZswgfrlRU07EE-D8RuL4r7B7kKsiiwcpgt_pSE2axIzSOzxWGj0flkUnEKFbZdGq-qb0ivcYyVOurIoYNjBzTES8qG_BcJwCsb2lR5XwZ4jlRGbkwAjx2y0)

***<u>Code PlantUML associé :</u>***
>>>
  ```puml
  @startuml
  left to right direction
  skinparam packageStyle rectangle

  :Alice: as Alice
  :Bob: as Bob
  :Banque: as Banque

  Alice --|> Membre
  Bob --|> Membre


  rectangle TinCar {

    (Recherche) as (Recherche)
    (Gestion des profils) as (gestionProfil)

    rectangle {
      (Payer) as (Payer)
      (Réserver un trajet) as (reserverTrajet)
      (Remplir un profil) as (remplirProfil)
      (Consulter un profil) as (consulterProfil)
      (Trier les recherches) as (Trier)
      (Recherche de trajet) as (rechercheTrajet)
    }
  }

  (Membre) -- (Recherche)
  (Membre) -- (gestionProfil)

  (gestionProfil) ..> (consulterProfil)
  (gestionProfil) ..> (remplirProfil)
  (Recherche) ..> (rechercheTrajet)
  (Recherche) ..> (Trier)

  (Banque) -- (Payer)
  (Membre) -- (Payer)
  (Membre) -- (reserverTrajet)
  @enduml
  ```
>>>

+ Diagramme de classes

![http://www.plantuml.com/plantuml/png/bPBDJiCm48JlVeezygD8SEsX2C45YKf8HRrldL5hI9neRLVbfm-KvyYB4P6iafGJbyWxysKoTXpUdQzPk2HRS0ZtCOhRfeWdM_cr-mJTcDwX5SgjGATdXwJhb-x1EuZE6-oTBK1VXeWosbH5Ah7Yew6J8W-LpvEDIA9K3IbTc22lmc-8QkSSyOYQ9VRp7abcWY2ov4EMkECyoGUsqLL-hEnGmiSrvE3iKFMwapyWT75tIOlvMoTZZ3RAij_TTqZUDds1FmwBk4FROBIMkbfGsqIk4UZAcEb1P9cUNCTiUSSxX7DY3BabguOO_GLpf1x4OCnqDnqp2VsFfLyvQ_MzrCkXn4py0G00](http://www.plantuml.com/plantuml/png/bPBDJiCm48JlVeezygD8SEsX2C45YKf8HRrldL5hI9neRLVbfm-KvyYB4P6iafGJbyWxysKoTXpUdQzPk2HRS0ZtCOhRfeWdM_cr-mJTcDwX5SgjGATdXwJhb-x1EuZE6-oTBK1VXeWosbH5Ah7Yew6J8W-LpvEDIA9K3IbTc22lmc-8QkSSyOYQ9VRp7abcWY2ov4EMkECyoGUsqLL-hEnGmiSrvE3iKFMwapyWT75tIOlvMoTZZ3RAij_TTqZUDds1FmwBk4FROBIMkbfGsqIk4UZAcEb1P9cUNCTiUSSxX7DY3BabguOO_GLpf1x4OCnqDnqp2VsFfLyvQ_MzrCkXn4py0G00)

<!--
```puml
skinparam classAttributeIconSize 0
 class Membre
 class Lieu
 class Passager
 class Vehicle {
   - VolumeMax
 }
 class Conducteur {
   - permis
 }
 class Trajet {
   - dateDepart
   - heureDepart
   - retard
   - prix
 }
 class Transaction
 class PaiementService {
   + Payer (?) : Transaction
 }


 Trajet -- Lieu : départ
 Trajet -- Lieu : arrivée
 Trajet -> Trajet : étapes *

 Conducteur -- Vehicle : bagages

 Conducteur -- Trajet : 1 conducteur
 Passager -- Trajet : passagers

 Transaction -- Conducteur
 Transaction -- Conducteur
 Transaction -- Passager

 Conducteur -|> Membre
 Passager -|> Membre
```
-->

---
#### Bilan TP

- ***Diagramme use case :*** Description des principales fonctionnalités de l'application sous forme de diagramme.
- ***Diagramme UML :*** Premier jet d'équipe sur le diagramme UML.
- ***Organisation :*** Répartition des tâches.

---

[:leftwards_arrow_with_hook: Retour à la page d'accueil](../README.md)
