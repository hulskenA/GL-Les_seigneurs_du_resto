```puml
@startuml
hide footbox
title __Scénario 10__


actor ":Préparateur" as Préparateur order 10
actor ":Gérant" as Gérant order 20

box "Application" #Lightblue
    participant ":VuePréparateur" as VuePréparateur order 30
    participant ":VueGérant" as VueGérant order 40
    participant ":FormulaireSaisiePlat" as FormulaireSaisiePlat order 50
    participant ":Controller" as Controller order 60
    participant ":PlatDAO" as PlatDAO order 70
    participant ":CarteDAO" as CarteDAO order 80
endbox

box "Base de données" #Lightblue
  participant ":Plat" as Plat order 90
  participant ":Carte" as Carte order 100
endbox

Préparateur -> VuePréparateur : Choisit saisir un plat
VuePréparateur -> FormulaireSaisiePlat
VuePréparateur <-- FormulaireSaisiePlat
Préparateur <- VuePréparateur : Affiche le formulaire
Préparateur -> VuePréparateur : Saisit les ingrédient et le prix
Préparateur -> Controller : Valide les informations

Controller -> PlatDAO : Insert le plat\nen base
Create Plat
PlatDAO -> Plat
PlatDAO <-- Plat
Controller <-- PlatDAO

Controller -> VueGérant : Envoie l'alerte de création
VueGérant -> Gérant : Affiche la notification
VueGérant <- Gérant : Sélectionne la notification

VueGérant -> Controller : Selectionner le plat
Controller -> PlatDAO : requete le plat

PlatDAO -> Plat : créer le plat
PlatDAO <-- Plat
Controller <-- PlatDAO
Controller -> VueGérant : Envoie le plat
VueGérant -> Gérant : Affiche le plat

alt Si le prix est incorrect
  Gérant -> VueGérant : Modifie le prix
    Gérant -> VueGérant : Valide le plat
    VueGérant -> Controller : Envoie le plat modifié
    Controller -> CarteDAO : Ajoute le plat à la carte
    CarteDAO -> Carte
    CarteDAO <-- Carte
    Controller <-- CarteDAO
    VueGérant <-- Controller
    Gérant <-- VueGérant
else Si refuse l'ajout
  Gérant -> VueGérant : Refuse l'ajout
  VueGérant -> Controller : Envoie le refus
  Controller -> PlatDAO : Supprime le plat
  PlatDAO -> Plat
  PlatDAO <-- Plat
  destroy Plat
  Controller <-- PlatDAO
  Controller --> VueGérant
  Gérant <-- VueGérant
end

@enduml
```
