 # Considérations générales

## Informations générales

* Dans la tiquothèque, **seuls les champs en gras sont obligatoires** à remplir
* Les liens textes renvoient vers l'élément concerné
* Un clic sur une icone (par exemple, sur une icone pdf), affiche le fichier concerné.
* Dolibarr est accessible à partir de n'importe quelle connexion internet et smartphone
* Votre mot de passe est personnel, ne communiquez pas votre accès à d'autres personnes.
* Il est possible si besoin de vous donner plusieurs accès à dolibarr (pour vos collaborateurs par exemple).

## Définitions d'un signalement
* Le signalement, pour signalement de piqûre de tique, est un type de contenu contenant les informations liées à une piqûre de tique
* Les signalements peuvent être ajoutés à la tiquothèque de plusieurs façons :
		→ Via l'application android(https://www.citique.fr/android)
		→ Via l'application ios(https://www.citique.fr/ios)
		→ Via le formulaire web(https://www.citique.fr/web)
		→ Via le formulaire papier(https://www.citique.fr/papier)
* Un signalement peut correspondre à plusieurs échantillons

## Définition d'un envoi
* L'envoi est un type de contenu qui recence les enveloppes reçues au laboratoire et contenant, un ou plusieurs échantillons.
* Un envoi peut être lié à plusieurs échantillons, et à plusieurs signalements

## Définition d'un échantillon
* Un échantillon est la tique responsable d'une piqûre signalée.
* Il est possible pour plusieurs échantillons d'être lié au même signalement

## Définition d'un résultat
* Le résultat est un résultat d'analyse lié à un échantillon
* Un échantillon devrait donc en principe être lié à plusieurs résultats
* Les résultats sont pour le moment importés via excel, mais il est possible d'importer des résultats via une API. Un tableau excel permettant de gérer facilement l'API est en prévision de réalisation

## Définition d'un suivi
* Le suivi est un élément qui permet de connaitre où se trouve un échantillon lorsqu'il est prété à un laboratoire.
* Le suivi permet de générer des MTA - Material Transfert Agrement pour faciliter le suivi de ces éléments 

## Définition d'une notification
* Les notifications sont des messages affichés :
- soit dans la zone de notification de l'application
- soit directement sur l'écran de l'utilisateur dans le cas des notifications 'push'

## Définition d'une information
* Une information est un écran dans lequel on renvoie l'utilisateur vers une page du site internet pour lui apporter une informatuion supplémentaire
* Les informations sont visibles depuis l'onglet "s'informer" de l'application

## Définition d'un écran
* Un écran est un contenu qui sera affiché au lancement de l'application, notamment lors du premier lancement
* Il permet de présenter le fonctionnement de l'application à l'utilisateur