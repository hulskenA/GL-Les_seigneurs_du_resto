```puml
@startuml
hide footbox
title __Scénario 1__: Prise de commande et notifications

actor ":Client" as Client order 10
actor ":Serveur" as Serveur order 20
actor ":Préparateur" as Préparateur order 40

box #Lightblue
  participant ":Application" as app order 30
endbox

Client -> Serveur : Demande une table
Client <-- Serveur : L'installe
Client <- Serveur : Prend la commande
Client --> Serveur : Donne sa commande

Serveur ->> app : Communique\nla commande
activate app
app -> app : Enregistre la commande
app ->> Préparateur : Envoi une alerte aux\npréparateurs concernés
deactivate app

@enduml
```puml
