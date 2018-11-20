```puml
@startuml
hide footbox
title __Scénario 9__


actor ":Client" as Client order 10
actor ":Préparateur" as Préparateur order 20

box "Application" #Lightblue
    participant ":VueTabletteClient" as VueTabletteClient order 30
    participant ":VuePréparateur" as VuePréparateur order 40
    participant ":Controller" as Controller order 50
    participant ":CommandeDAO" as CommandeDAO order 60
endbox

box "Base de données" #Lightblue
  participant ":Commande" as Commande order 70
endbox

Client ->> VueTabletteClient : Saisie une entrée
Client ->> VueTabletteClient : Saisie un plat
Client -> VueTabletteClient : Valide sonchoix

VueTabletteClient -> Controller : Envoi les détails\nde la commande

Controller -> CommandeDAO : Demande l'enregistrement\nen base

create Commande
CommandeDAO -> Commande
CommandeDAO <-- Commande
CommandeDAO -> CommandeDAO : Insert en base
CommandeDAO --> Controller : Confirme la\ncréation

Controller ->> VuePréparateur : Notifie de la création
Controller --> VueTabletteClient : Confirmation de\nla création

VuePréparateur ->> Préparateur : Notification sonore\nou visuelle

VueTabletteClient --> Client : Confirme au client\nque la commande\nest prise en compte

@enduml
```
