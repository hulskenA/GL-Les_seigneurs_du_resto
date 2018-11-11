### Bilan des tâches effectuées lors de la scéance 6
##### *23 / 10 / 2018*

---

+ Préparation des diagrammes de séquences

---

```puml
@startuml
title __Scénario 9 :__ Le client saisit lui même sa commande via une tablette

actor Client
box "Application"
  boundary "<<UI>>\nTabletteClient" as UIClient
  control Controller
  boundary "<<UI>>\nPréparateur" as UIPreparateur
endbox
actor Préparateur

Client -> UIClient : Entre la commande
Client -> UIClient : Valide la commande

UIClient -> Controller : Envoie de la commande

Controller -> Controller : Traitement de la commande

alt si dessert
  Controller ->> UIPreparateur : Envoie au glacier
else si entrée ou plat
  Controller ->> UIPreparateur : Envoie au cuisinier
else si boisson
  Controller ->> UIPreparateur : Envoie au Barman
end

UIPreparateur -> Préparateur : Envoie d'une notification
UIPreparateur -> Préparateur : Affichage de la\n commande concernée

@enduml
```

![](https://www.plantuml.com/plantuml/img/bLDDQy904BtlhnXowQa_e291Apq87eHgJqAOR4OxiDaD-o7jJx9_mp_MYQOcYb0y1IRllPbvytOI8lgOQgCYHqDG5E_wUB3esS4BZ8e25WJQCDa80Jbm19COwkDFJL80xUeQRKMmPuHa2IAMXc8afL17vs5sughIVK4sRHh36YCxcoc0qYLReV-6R3nUp_DyOrST-KpA00Eivvq2I2yRlJCmEtyD-RiYItyyDEWnKlATnDBJNqMHhMIORheXLgbp9tZEBrrX16_IZC3qgzw7VQ3XwXgdBhy5sWzzqjmx9hZ53p2tZ9L7ZbItOhSiD78Qbd88v5kVhcJow_NxvfXWPr2pk4WcK2iXwk87WKlG67n8IYV9XXsAbOv3SFOHaLVqibDxeTQx8Khi69vgOE5J6phh8c-xPFtBd6u5-ecxpl-DxKCi2TFahNYWr4J6QD_5Bm00)

---

athée

```puml
@startuml

actor Client
actor Serveur
box "Application"
  boundary "<<UI>>\nTabletteServeur" as UIServeur
  control Controller
  boundary "<<UI>>\nPréparateur" as UIPreparateur
endbox
actor Préparateur

Client <- Serveur : Installe
Client -> Serveur : Donne commande

Serveur -> UIServeur : Saisit entrée,\n plat, dessert,\n boisson (commande)
Serveur -> UIServeur : Valide la commande

UIServeur -> Controller : Envoie de la commande

Controller -> Controller : Traite la commande

alt si dessert
  Controller ->> UIPreparateur : Envoie au glacier
else si entrée ou plat
  Controller ->> UIPreparateur : Envoie au cuisinier
else si boisson
  Controller ->> UIPreparateur : Envoie au Barman
end

UIPreparateur -> Préparateur : Notifie de la commande
UIPreparateur -> Préparateur : Affiche la commande

@enduml
```

![](https://www.plantuml.com/plantuml/img/bP91JiCm44NtFiKeAv3Q2w0geXGMtQ1ARLbrCqccOCaTH_QaWYDn3Yx6XCOa3I3KLHJF_t--Nt8R1OCq1sSCbk83B9mbbkvbJU58JJ25VuLiNjVEbYZMSsO02jzmXU4Dijbikypp7M-mS2H2dIi3ZB1TfWo0qhC4xs1nUZeAlyQimiTxZG6bprW5IYU6kD8wNS6XrfXJTvXDKt6uWINh3NLN6axpmV3UCvFsEXoGAp8cJLJqNLnbQxJH2gXTrz5anr0xb0bK52C5QGyARsFq35SfxFgli2TqjY9mEDZRprNSur7r0n-z9HWR1fgnOnFGoaYEJY3Qr5Ufd_dpSyBzLcpWsM5fzKEHYzH6T0p0DryCBeag6wN8mx0EsYKXTnZqJkrFq58RgfJ3y6zGrwCNk_y9xp_RVB-tvSk8u2S0)

```puml
@startuml

actor "Client A" as ClientA
actor "Client B" as ClientB
actor Serveur
box "Application"
  boundary "<<UI>>\nTabletteServeur" as UIServeur
  control Controller
endbox

note left of UIServeur: **A** a pris sa commande\npuis **B**\n//cf. prise de commande//


== Service du premier client ==

UIServeur <- Controller : Envoie la notification A\ncommande prête

Serveur <- UIServeur : Affiche la notification

ClientA <- Serveur : Sert la commande

== Service du second client ==

UIServeur <- Controller : Envoie la notification B\ncommande prête

Serveur <- UIServeur : Affiche la notification

ClientB <- Serveur : Sert la commande

@enduml
```

![](https://www.plantuml.com/plantuml/img/hP9DReCm48NtSuedbfPQzWYYG9H5rcrsR0mCgYLZ8sEYzagzHYzMyvCGfOiksfL_viqtRppU3ruwFtQQIDRUEaG7hTXuv17aWEMGFyIAkrYnnbxONNXqLDbtH7dVQrLBhwo92AZiQ1hfFX2bwVcqsvNcLLQQlUSrQ-QTJrS6K5lZdTKuBAjcHsoQm2OorZCqjnwstN8I294B0OdUgG6338YkawRXqlHZk16Y4A8qSLotpxE6qV1D5CT4b6Lp5weEeJ5ek5FiK2yzPndHhHhIfpjhI70q5wk2BObWJxLhxyXBSwqGU5-Vdedk41ilGTw6hBSV2A9r19D-KuUTdwHN-gFvWSCBDd_oNloRz-8tx_ims-aBVWC0)

---

```puml
@startuml
title __Scénario 6:__ Le plat commandé n’est plus disponible


actor Client order 10
box "Application"
  boundary "<<UI>>\nTablette de commande" as UIServeur order 20
  control Controller order 30
  boundary "<<UI>>\nPréparateur" as UIPreparateur order 40
end box
actor Préparateur order 50

note left of Controller
  **Prérequis**
  __
  La commande du client
  a déjà été prise dans
  ce diagramme.
endnote

Controller -> UIPreparateur : Envoie de la commande

UIPreparateur -> Préparateur : Notifie
UIPreparateur -> Préparateur : Affiche

Préparateur -> Préparateur : Remarque qu'il n'est\npas en mesure de ma\npréparer
UIPreparateur <- Préparateur : Indique l'indisponibilité

Controller <- UIPreparateur : Informe le système\n de l'indisponibilité

UIServeur <- Controller : Notifie de l'indisponibilité

Client <- UIServeur : Notifie le client et\nlui demande une \nnouvelle saisie
rnote over UIServeur
  Ici soit le client
  reçoit une notification
  sur la tablette sur sa
  table ou le serveur
  vient l'informer
endnote
@enduml
```

![](https://www.plantuml.com/plantuml/img/XLHBYjj04DttAGfl38O9pdTXZF4mP64Omf39x0oYBPMI2grgkJzcPfThP9TTudFe9Zb9gcL9_cH2DbAhkjwhgjUljVH1kn0hezHoM0OA1Y7BxlDcpzgHXNUpB8DRXDhe0BcjAir5imV-_Uqx-Y3XwA4WNrkcZK6bbCw3TN1Z23c0TGKwU3bL6_i8e-kwDfJhG9P72c1Z8nVQFS5eFdzOBHPh_gI58mI40ljQE0BjuM5rZsw7qNMChwQ2poq7PmtS7Du6-ztNqsVPxrophxNJGNWwrZk7VQJ3lfagv4BGZzqafwWkv-rKARRIfi5IPYnFEf32aqc2EDn6yfE91B9C7hTwc0YA27chZyGrY9nVcn_Gx8FeMZloag3Pfm5bHVgpqrM5Br9RgQXI9_DUBIw6cC5xtbbg5JJ7aagTfmdkRAuPVB21IiB_vbsN9ULVXF0i_dVUHwoqsqQ4RHoJ0HwBMzPSY-h8KA6FhksnqX8y84Myy-BpgqlI5HUKECsOk3ST6HBXpbGHuAKgAowjgzA9WN_oeVbLuPfRaPwXEhfDc4vu1vN-1UnStzRlAOuWgNquTa2HmaGIceCX8YEicMtSeKaTQl9o5AxrcDr9vO5ENB7A2RobSEIJeCFcPueb9cxh7UwPR8dKoGgXlrlfsslPQ2DWOolAGBzhEqpJjOgvmNTBMQH_HF_-0m00)

---

```puml
@startuml

actor "A : Client" as ClientA order 10
actor "B : Client" as ClientB order 20
actor "A : Serveur" as ServeurA order 30
actor "B : Serveur" as ServeurB order 40
box "Application"
  boundary "<<UI>>\nTablette Serveur" as UIServeur order 50
  control Controller order 60
endbox

note right of ClientB
  **Prérequis**
  __
  Le client B s'apprête
  à partir.
endnote

ClientB -> ServeurA : Demande l'addition

ServeurA -> UIServeur : Demande de génerer\nl'addition pour le client\ncorrespondant

UIServeur -> Controller : Demande l'addition

Controller -> Controller : Génère\nl'addition

UIServeur <- Controller : Renvoie l'addition

ServeurA <- UIServeur : Présente l'addition

ClientB <- ServeurA : Donne l'addition
ClientB -> ServeurA : Paie

ServeurA -> UIServeur : Clôture la commande\ndu client

UIServeur -> Controller : Clôture la commande

Controller -> Controller : Clôture la commande\net libère la table
note left
  Ici la libération de
  la table ce fait en
  communiquant avec
  une base de données
  potentielles
endnote

ClientA -> ServeurB : Rentre dans le restaurant et demande une table

ServeurB -> UIServeur : Demande la disponibilité\ndes tables

UIServeur -> Controller : Demande la liste des tables\ndisponibles
UIServeur <- Controller : Renvoie la liste des tables\ndisponibles

ServeurB <- UIServeur : Affiche les tables disponibles

ClientA <- ServeurB : Affecte une table au client
note right
  Ici la table du client
  B peut être attribuée
  au client A
endnote

@enduml
```

![](https://www.plantuml.com/plantuml/img/ZLHDQ-Cm4BthLmov509Tif-74aAJ54fW3sLtUmiKsPwq0aLofL7O_JTxtEnv_u7_s8viAtQ2qnPCh4XltioyUTQr9-aeRBKGCYVhO3I7ArXgXOP687sxd8Dr1JfuFqcmnH1iqS8-JFfitz7jCBWQrwuJtySZlW5WOlmq4PdzoNnbgLKkILap4W2P3QQGxXUCfjFxrMosDZzaff48ZyZkL-s_bktpX6DpQyXP3SlchJ6TVfa8D0Md4y9OPdBgyOd0RbAJ73iUtxbgx_0vA3yUyyR30_zyHSXh22p0NyYoTDLVGZweVaF9CYltBZ97KY6IOfUpJfGhkC6jD0M2lf15eMARGXoE6Tfrqc7vUQps1XswjUa2eRGCqwccjScjS-XBoueP4gAZOjwU2CD5z02dy5jENlrns4_UfvzU7kE_eTbPTQP71lTxZ39xhlwac5Ox1lUriyOSuOOblfCApukwrDK_2evv93jaMmknDaLeLNn9jg7G5uKRpeK4McLHqBXFqS-D3pLkYCsqobKyY9Yzgxy4TW3l9p3a21kf2D3KBjzkWr7FWMSESeSvxmMMAPE-Tax1ebLxzBnTSX932hawV-hJUK_4HJD3uWBPIJvQZ7r5ChYOWyilMl_4F4tzuX1wniDSVA6YDrMcjA9gpvgZRwBzcxmQ5V4KUqfXJD5IHeut-F4rYgwB4vVEDnkLFyK9fK0uYaiQTdvTD56OKqyca0URTHTFD_46qraH-9efCH3mBSEpa4HEPO67oIS79fXtexpc5L_r_m40)

---

```puml
@startuml
title __Scénario 3:__ Le client ajoute un élément à sa commande

actor Client order 10
actor Serveur order 20
box "Application"
boundary "<<UI>>\nTablette serveur" as UIServeur order 30
  control Controller order 40
  boundary "<<UI>>\nPréparateur" as UIPreparateur order 50
endbox
actor Préparateur order 60

Client -> Client : Termine son repas
Client <- Serveur : Débarasse
Client <- Serveur : Demande si\ndésire autre chose
Client -> Serveur : Demande une glace\net un café

Serveur -> UIServeur : Edite la commande
Serveur -> UIServeur : Ajoute le café et la\nglace

UIServeur -> Controller : Envoie la modification\nde commande

Controller -> Controller : Traite l'ajout
alt si café
  Controller ->> UIPreparateur : Envoie au Barman
else si glace
  Controller ->> UIPreparateur : Envoie au Glacier
end

UIPreparateur -> Préparateur : Notifie la commande
UIPreparateur -> Préparateur : Affiche la commande

@enduml
```

![](https://www.plantuml.com/plantuml/img/bPFDQkD03CVlynGYbpqLtErk3oQ4fXyiXQKKcjuCGR6LTfRnJD2CI_islVev_6BL-2EE-q7PImmQ_VIN_bBEV40ELMbKqC4GhDTtULDRPEtW95sluIz1RZJP0FZFLO6Wij3KfgdB66jUmIFahYpH5gGKvi4nN7I0uu8OZfC-UaVyH1NtuP-9shXdc2rtEwDp3DhPcKGgMo2_m6m-lxzUB3AxmesX8BA-esU07kwlfxLE4WNIX0ti35nqNqF3ww_u-h7oBJVr3Xd3MFMMQOZqxEz4aIsaqNw6GwXFEKsKwWS-MWoZfx0YBhMLlfs5MDOFIVEZlHCfN3RrHifvJvy_K-ihU9tPegczPWAiWlpcZsvaHFSZKuduWy6SCaiXRYt7RLChDMGADFgOmbMXnMLpiCml4fVT6SYjj0L1YXlCR2kbr9WPpHXN8GBsoUbMeNI5tlOxpsAhu_qS4E_v5MFRuO_s3XMQ8BRqGm5CmCMxNUx5iO9pPD5IP7oqjNFeV_W_0cZYU1PnsiCqwNXo7odSk22JJctzZbbknPl7AQFEH2x-ITy0)

---

```puml
@startuml
title __Scénario 10:__ Les responsables ajoutent/enlèvent des plats à la carte

actor Préparateur order 10
box "Application"
  boundary "<<UI>>\nPréparateur" as UIPreparateur order 20
  control Controller order 30
  boundary "<<UI>>\nDirecteur" as UIDirecteur order 40
endbox
actor Directeur order 50

Préparateur -> UIPreparateur : Choisit de créer un plat
Préparateur <- UIPreparateur : Affiche page ajout plat
Préparateur -> UIPreparateur : Saisit plat/recette/prix
Préparateur -> UIPreparateur : Soumet la suggestion de plat

UIPreparateur -> Controller : Envoie suggestion plat

Controller -> UIDirecteur : Envoie suggestion plat

UIDirecteur -> Directeur : Envoie l'alerte
UIDirecteur <- Directeur : Sélectionne la notif
UIDirecteur -> Directeur : Affiche détail du plat

alt si prix incorrect
  UIDirecteur <- Directeur : Modifie le prix
end

alt Si valide l'ajout
  UIDirecteur <- Directeur : Valide la suggestion
  Controller <- UIDirecteur : Envoie des nouveaux plats
  Controller <- Controller : Ajout des plats à la carte
else Si refuse l'ajout
  UIDirecteur <- Directeur : Refuse la suggestion
  Controller <- UIDirecteur : Envoie le refus
  Controller <- Controller : Détruit la suggestion
end

@enduml
```

![](https://www.plantuml.com/plantuml/img/bLJBRjim4BppAnQ-z1HOVLqCmuYHz12W1O8QwQc0iQPM3Wk65FWmtB_fiVuE_LYNb9BIZkec5qcKPcQ7iqjT-e0kn0SjWWgQOBrUoUvWq2aBRwlPUWsVoOCZtrhZSQDvWJzi36J2b8pkVk_u2Mf-tMeC7hfVe14aQv8GA8DrSEkwGuiE0qK7rjNaM5bix1ucoxRLIc9Gram4mCP6KwFx2PFv_EvciVXkIku4qCFTpQsZ4xLt5NEbDS5P3LVzNTFZr_VLgFArSYGBsQVrGFjG2J8rknnsSVhzOoN4qSuk5YVcPd1rRvLNAHwG36LMD3cdO-RyuXbpsJHAtXEqkAK-y17UICKLve89EsM_509DMwVs_oVQ-40XzSx7xPPyQadodQkAOpJJYvHdyCdihAAIsBCAKAxuDy9_SqeKaqOe-Wso8ezN2UK8I-YgEsXUiAoXj2TZWshEQJ_cNNU7W4f37GS_g0Du1Ib3K4PQbpWyK6UAVx6rQf9HohGqHhtEIi4EjQhp7b9Fp-jy6x1bIvXHf9e7PoIYT1oDZJl2kE_FvJFUKGENUS363p5fJycveoRw5ph_Ec1VxvmpouNE-xtcBhceJiQr3_gIh_mx-mC0)

---

![](https://www.plantuml.com/plantuml/img/XLHDYzim4BthLmovx6cp99T2M4ApAPI57fQclGMCR4zs1RBabKQ1_fiUcvxx3_p7EhBYZwJUBWGSUzuRpNlpx8-UfADGQK6AD4AMxOhcPAHJ5Zva6UmDtDrbsPDhJWvVW_ByR0LV40gjq10yWB-HTUsQtuJG_8IQkod7725aGTR1RBFQjj0PI1zPYwxmS5LOTeNTOhL3TyJWsfBd_prfj_odjXIv3QQKxWVCxk-_FwxNUxFw9dEDH3W6Tp1HM4FEQjYcgqRNZf3kX8YpmEqw7SngFs4bJOcWRsHPAbBMY5HYJ7_q0EFVCriO3NCZ3jGsy7tlN66TGrzRfXiQ973FRho-vRXDF_m5yFF4WGFoSiwlQ8vMNSWPdzwfZYltFEYqxjOZ7j0QSm6uzkv9gdUDs-hc3mN7ECcIghEB0L8yth1cYZJjpMHx9D0gRtwbnnJJ8enbiKuzln2p7WiLAn5qSh9TO3bWeK0uI4NyVg1fkmQZNWDl4kGH2mZiojxaqhTnADcbveIU8q2iI257hehIn7m-Zqe9gvgh68XV8CyU0HVQ82uwCvTfSyG3Ss1y31B7XsHmyL2MKvxZ5uzEUX9jEgGif5GnVIfNMb5pOhvFFF__C2PNFE68qVUAxFTYDyswZc3KkpaSLF7o9gNNr_hKmh6WaGCWm_bjIxlLU1YjDa7AC7pAuW9k-Kl67aiYf_B0MnkQm4Ry1G00)

---

![](https://www.plantuml.com/plantuml/img/XLAzJiCm4Dxz5ASkJ4niKHKLjGniI2qRKdHnhc3as9LzYSGZvJdoOfoTD8KMYSMMxxu_dxs9Z86xrYesR0cgQg_7mM4m7XwgIYdKx0EiYgqrv7W5645RivJt57hgGgv72ghsdMimVC5glNvzBiitLnomjiHCEzhwjaNN41HmBlxaroBGA-qT1szXE-sMGlQSJd_fluHnE650NdHEWKvBmfjsxYgv1DoNANEVub1eZIEG2KWNeyfrwITO0Rjng4KYHa4WSCf-ZQ3fPj4a3Ps71SquH1C8i6DPzOUFTELxfdNY_MvH4n3B0JGUns6ng6VqKsDOnY4Hz3p96yZZf-_4EETS19jk5goNqFEGHTFrtcHuwnjpD1hPU3ShB3Pd_2_g8Q3a0Nk7oLIXvTa6u88lf-UuE647CakHLUIQJCev_oKbb94VbbXg8wjyscy0)

---

[:leftwards_arrow_with_hook: Retour à la page d'accueil](../README.md)
