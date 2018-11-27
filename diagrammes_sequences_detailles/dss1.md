```puml
@startuml
hide footbox
title __Scénario 1__: Prise de commande et notifications

actor ":Client" as Client order 10
actor ":Serveur" as Serveur order 20
actor ":Préparateur" as Préparateur order 30

box "Application" #Lightblue
  participant ":VueTabletteServeur" as VueServeur order 40
  participant ":VuePréparateur" as VuePréparateur order 50
  participant ":Controller" as Controller order 60
  participant ":CommandeDAO" as CommandeDAO order 70
endbox

box "Base de données" #Lightblue
  participant ":Commande" as Commande order 80
endbox

activate VuePréparateur

Client -> Serveur : Demande une table
Client <-- Serveur : L'installe à une table
Client <- Serveur : Prend la commande
Client --> Serveur

Serveur -> VueServeur : Saisit la commande\net la valide
activate VueServeur
VueServeur -> Controller : nouvelleCommande\n(listeConsommations)
activate Controller
Controller -> CommandeDAO : creerUneCommande\n(listeConsommations,table)

activate CommandeDAO
  create Commande
  CommandeDAO -> Commande : creerUneCommande\n(listesConsommations,table)
  CommandeDAO <-- Commande : commande
  CommandeDAO <- CommandeDAO : insereCommande\n(commande)
  CommandeDAO --> Controller : Confirme la création
deactivate CommandeDAO

Controller --> VueServeur : Confirme la création
VueServeur --> Serveur : Confirme la création
deactivate VueServeur

Controller ->> VuePréparateur : informeNouvelleCommande\n(commande)
deactivate Controller
VuePréparateur ->> Préparateur : Alerte sonore\nou visuelle

@enduml
```
