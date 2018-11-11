<!--
![v1](https://www.plantuml.com/plantuml/img/NL9BQiCm5Dph58-iaXILTcjCY0bPP148f1UGxKSGjIKZFGVIptsQS-HYrSVVU66aqSppZCPRIy9GMrVCVahL22DgA2fXRKPaPDuI7Wgjpl8BuOsnS08dyxXx9c5hu9knNoPoIqOK1FkwgVJjSNSmm0bRsfUIq1nHjGdaMbUE78Tu2DBqBDMbGj9gimaQ3b8vIwh0gF5l5d2_MgxSyWKkI8UEjLnrd7xkJYkhwrgGr2gQwt47gXAV39_HN6M1KwQ7XcGH-X2vCqcugoGgcfva5HgQoREcEGebBjXDSCy4MhmlN9R5Uj4fat1BWEggRsZOS7-UmJdNGJ3gsSX8VpZlxJ-Xqu8OwoCE0e_Em7ayna8t_iCfV-LXCSnF82kAnr-98qdp66XwyudVKPWMUElONm9zRrsnGoinRupRUHjdG8cMpOgTqliP2Q0bA7JTQEkSEejRLANxjVy1)
-->

```puml
skinparam classAttributeIconSize 0

class Préparateur {

}
abstract Employé {
  PeutEditerMenu: bool
}
class Menu <<Singleton>> {
  - instanceMenu: Menu

  - Menu()
  + getInstance(): Menu
}
class Consommation {

}
class Commande {

}
abstract Service {

}
class Serveur {

}
class TabletteClient {

}
class Alerte {

}
class AppManager {

}



AppManager "1" - "*" Alerte: Peut envoyer
Employé "*" ---o "1" AppManager

Employé <|-- Service
Employé <|-- Préparateur

Service <|-- Serveur
Service <|-- TabletteClient

Menu "1" <-.- "1" Employé : Accède
Menu "1" o-- "*" Consommation: Contient
Menu *- Menu: Instance Menu

Commande "*" --o "1" Service: Contient des
Consommation "*" --o "1" Commande: est composé de
```
