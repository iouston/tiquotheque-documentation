 # Devis

 Le projet est le dossier virtuel dans lequel nous allons placer tous les éléments d'une affaire
 Dans le logiciel LDM sofware, c'est la notion de chantier qui était utilisée.
 Désormais, il faut considérer qu'un chantier est l'équivalent d'un projet.
 Pour un projet, il est possible **d'ajouter plusieurs devis différents, et adressés à des clients différents !**


## Créer un devis

<!-- tabs:start -->

#### ** En passant par le tiers **

En passant par le tiers
* Rendez-vous sur la fiche du client concerné. Si le client n'existe pas encore, créer un client
* Aller dans l'onglet 'Prospect/client'
* En bas à droite, cliquer sur le bouton 'Créer une proposition
* Remplir les champs relatifs au devis
* Créer le brouillon du devis
* Une fois le devis créé, le relier à un projet. Si le projet n'existe pas encore, le créer

> [!WARNING]
> Un devis doit obligatoirement être rattaché à un projet, si ce n'est pas le cas, vous ne pourrez pas valider votre devis.

#### ** En passant par le projet **
* En passant par le projet
* Aller dans le projet concerné par le devis
* Cliquer sur l'onglet 'Vue d'ensemble'
* Dans la section 'Liste des propositions commerciales associées au projet', cliquer sur 'Créer une proposition'
* Indiquer le nom du client destinataire et remplir les champs restants du devis

<!-- tabs:end -->

## Ajouter un produit ou un service au devis

* Selon votre niveau d'autorisation, vous pouvez ajouter des produits prédéfinis et/ou des produits libres. Un produit prédéfini est produit qui a été enregistré au catalogue de LDM Équipement. Son tarif de vente est connu.
* Un produit libre est un produit qui n'est pas disponible dans le catalogue de LDM Équipement. Le prix est à fixer au moment de l'édition du devis. Il est possible de transformer un produit libre en produit prédéfinis en l'ajoutant au catalogue. Seules certaines personnes ont cette autorisation.
* Pour ajouter un produit à votre devis, cliquer dans le champ de formulaire "Produits/Services prédéfinis en vente".
* Indiquer dans ce champ les 3 premières lettres du produit recherché. Il apparait alors une liste des produits correspondants.
* Si vous continuer de saisir les lettres suivantes du produit recherché, la recherche s'affine.
* Vous pouvez également indiquer directement la quantité, la réduction à la ligne sur ce produit et l'emplacement de cette ligne. Par défaut, vous pouvez choisir d'ajouter dans vos localisations ou directement au niveau d'une ligne, à l'aide du champ "position".
* Les numéros de ligne sont situés à gauche de chaque produit du devis et vous permettent de vous repérer rapidement. Ces numéros n'apparaissent pas sur le devis édité.
* Lorsque vous ajouter un produit, il se peut que ce produit compte des produits associés.

## Ajouter un produit associé

* Certains produits disposent de produits associés. Il s'agit de produits à proposer/ajouter au client. Cette fonctionnalité vous permet d'ajouter plusieurs produits complémentaires d'un coup.
* Si la fenêtre modale des produits associés s'affiche, sélectionner un ou plusieurs produits que vous souhaitez ajouter à votre devis.
* Valider votre choix, et les produits cochés seront ajoutés à votre devis

> [!TIP]
> A l'inverse, si vous ne souhaitez pas ajouter des produits complémentaires à votre devis, vous devez malgré tout, cliquer sur le bouton "Valider"

![localisation](_media/localisation.jpg)
*↑ Ci-dessus la fenêtre modale des produits associés*

## Ajouter une localisation

* Pour ajouter une localisation, cliquer sur le bouton "Ajouter Localisation" situé en bas du devis
* Indiquer le titre de la localisation dans la fenêtre modale qui apparait ainsi que le niveau de la localisation.
* Par défaut, les localisations de niveau 1 apparaissent en bleu. Celles de niveau 2 en rose et les suivantes en bleu. 

> [!WARNING]
> Attention, à ne pas ajouter trop niveau de localisation au risque de perdre le client dans la compréhension du devis. 3 sous niveau semble être le grand maximum…

* Une localisation doit avoir un "total de localisation". De cette façon tout ce qui est ajouté entre le titre et le total de la localisation sera décompté dans le sous total de la localisation.
* Lorsque j'ajoute une nouvelle localisation sans avoir ajouté de "total de localisation" à la précédente localisation, le logiciel ajoute automatiquement le "total de localisation"
* Depuis les icones situées sur la rangée du titre de la localisation vous pouvez déplacer / dupliquer / modifier / supprimer / supprimer avec les lignes contenues la localisation
* Vous pouvez également ajouter une ligne de texte. La ligne de texte permet de préciser un détail lié au produit. La ligne de texte ne comporte pas de prix. La ligne de texte apparait en jaune. Il est possible d'utiliser des textes prédéfinis. Les textes prédéfinis peuvent être ajoutés / modifier / supprimer (en fonction des droits de l'utilisateur) depuis accueil > configuration > dictionnaires > ligne de texte prédéfini.

![localisation](_media/localisation.jpg)
*↑ Ci-dessus les boutons d'ajout de localisation dans l'écran d'édition du devis
↓ Ci-dessous, les actions propres à la localisation dans l'écran d'édition du devis*
![localisationactions](_media/localisation_actions.jpg)

## Modifier rapidement les quantités / les prix

* Lorsque vous avez ajouté des produits, il est possible d'intervenir directement et rapidement sur les valeurs des colonnes : prix / quantité / remise.
* Pour cela, il suffit de cliquer sur le lien bleu et de modifier la valeur.
* Il est possible que vous n'ayez pas les autorisations de modifier rapidement le prix
* Valider votre changement en validant par la touche entrée ou en cliquant en dehors du champ
* Nous attirons votre attention sur le fait qu'il est plus pertinent de réduire le prix via une remise de ligne que directement au niveau du prix car si vous modifiez le prix, le client ne vois pas que vous consentez un effort…

![quick_edit](_media/quick_edit.jpg)
*↑ Ci-dessus Il suffit de cliquer sur les éléments soulignés pour déclencher une action de modification
↓ Ci-dessous, Apès le clic, un champ apparait qu'il vous suffit de modifier et de valider*
![quick_edit_field](_media/quick_edit_field.jpg) 


## Ajouter un produit en négatif
* Lorsque vous éditez un devis, il peut vous arrivez de devoir ajouter un produit en négatif
* C'est par exemple le cas d'un allongement
* Au moment de l'ajout, dolibarr ne tolère pas un produit en négatif
* Il faut donc ajouter votre produit
* L'éditer rapidement, comme vu précédemment en cliquant dessus, et placer le signe – devant la quantité dudit produit.
* Le produit passe alors en négatif, ainsi que le prix associé.

> [!WARNING]
> Attention, dans le cas d'un allongement négatif et afin de calculer une marge juste, il est nécessaire de forcer le prix de revient en négatif également. Sinon la marge finale sera fausse.

## Ajouter une option au devis

* Il est possible d'ajouter des options au devis, c’est-à-dire, indiquer un produit qui n'est pas compté dans le total du devis, mais dont le prix est remplacé par la mention "option"
* Pour cela, modifier un produit en cliquant sur l'icône "Modifier"
* Calculer la valeur totale de l'option et indiquer 0 dans la colonne quantité
* La mention 'option' apparait alors dans la colonne 'Total HT'

> [!WARNING]
> Cela ne fonctionne pas si vous passez par la modification rapide des quantités

![produit_option](_media/produit_option.jpg)

## Ajouter un produit offert

* Il est possible d'ajouter un produit offert et de le signaler au client.
* Pour cela, il suffit d'appliquer une remise de 100% 

> [!WARNING]
> Attention il faut passer par l'icone 'modifier' et non pas la modification rapide.









