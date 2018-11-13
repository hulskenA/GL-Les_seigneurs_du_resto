```puml
@startuml
hide footbox
title __Scénario 10__


actor ":Préparateur" as Préparateur order 10
actor ":Gérant" as Gérant order 100

box "Application" #Lightblue
    participant ":VuePréparateur" as VuePréparateur order 30
    participant ":FormulaireSaisiePlat" as FormulaireSaisiePlat order 40
    participant ":Controller" as Controller order 50
    participant ":PlatDAO" as PlatDAO order 60
    participant ":Plat" as Plat order 70
    participant ":CarteDAO" as CarteDAO order 80
    participant ":VueGérant" as VueGérant order 90
endbox


Préparateur -> VuePréparateur : Choisit saisir un plat
VuePréparateur -> FormulaireSaisiePlat
VuePréparateur <-- FormulaireSaisiePlat
Préparateur <- VuePréparateur : Affiche le formulaire
Préparateur -> VuePréparateur : Saisit les ingrédient et le prix
Préparateur -> Controller : Valide les informations

Create Plat
Controller -> Plat : Créé le plat
Controller <-- Plat

Controller -> PlatDAO : Insert le plat\nen base
destroy Plat
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
    Controller <-- CarteDAO
    VueGérant <-- Controller
    Gérant <-- VueGérant
else Si refuse l'ajout
  Gérant -> VueGérant : Refuse l'ajout
  VueGérant -> Controller : Envoie le refus
  Controller -> PlatDAO : Supprime le plat
  Controller <-- PlatDAO
  Controller --> VueGérant
  Gérant <-- VueGérant
end

@enduml
```