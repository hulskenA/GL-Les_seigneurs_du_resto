```puml
@startuml
hide footbox
title __Scénario 11__: Ajout d'un utilisateur

actor ":Gérant" as Gérant order 10

box "Application" #Lightblue
  participant ":VueMenuGérant" as VueMenuGérant order 20
  participant ":VueListeUtilisateurs" as VueListeUtilisateurs order 30
  participant ":FormulaireUtilisateur" as FormulaireUtilisateur order 40
  participant ":Controller" as Controller order 50
  participant ":UserDAO" as UserDAO order 60
endbox

box "Base de données" #Lightblue
  collections "AllUsers:User" as UserList order 70
  participant ":User" as User order 80
endbox

Gérant -> VueMenuGérant : Demande la liste\ndes utilisateurs
VueMenuGérant -> VueListeUtilisateurs : Redirection
VueListeUtilisateurs -> Controller : Demande les utilisateurs
Controller -> UserDAO : Requête les utilisateurs
UserDAO -> UserList
UserDAO <-- UserList
UserDAO --> Controller
Controller --> VueListeUtilisateurs
VueListeUtilisateurs --> Gérant : Affiche la liste des utilisateurs
Gérant -> VueListeUtilisateurs : Ajoute un utilisateur
VueListeUtilisateurs -> FormulaireUtilisateur : Redirection
FormulaireUtilisateur --> Gérant : Affichele formulaire
Gérant -> FormulaireUtilisateur : Remplit le formulaire
FormulaireUtilisateur -> FormulaireUtilisateur : Analyse syntaxique
Gérant <-- FormulaireUtilisateur
Gérant -> FormulaireUtilisateur : Valide la saisie
FormulaireUtilisateur -> Controller : Envoie des champs saisies
Controller -> UserDAO : Ajoute l'utilisateur en base
create User
UserDAO -> User
User --> UserDAO
UserDAO --> Controller
Controller -> UserDAO : Demande la liste des utilisateurs
UserDAO -> UserList : Requête la liste des utilisateurs
UserList --> UserDAO
UserDAO --> Controller
Controller --> VueListeUtilisateurs
VueListeUtilisateurs --> Gérant : Affiche la liste des utilisateurs

@enduml
```
