# Solution

## MCD

Voici un premier modèle conceptuel des données, qui pourrait être réalisé. Attention ce modèle présente des imperfections structurelles qui vont pénaliser la performance, la maintenance et l’intégrité de l’applicatif.

![MCD_image](image.png)

voici un modele plus coherent:

![](image-1.png)

## MLD

![MLD](image-2.png)

## Model Relationnel

Types(Codetype, Désignation)

Produits(CodeProduits, Désignation, Prix_au_kilo, #Codetype)

Date(DateDeVente)

Vendre(#CodeProduits, #DateDeVente, Poids)
