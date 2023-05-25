# Dictionnaires :notebook_with_decorative_cover:

<p style="text-align:justify;">
Un dictionnaire est une table permettant d'associer des labels à des valeurs utilisées pour une variable dans la table principale.
</p>
 
<p style="text-align:justify;"> 
Pour un champ de formulaire sous forme de liste déroulante, cela permet de lister toutes les possibilités du champ. 
Ainsi, il est possible grâce au dictionnaire de garder un historique des possibilités du champ, et de connaitre les possiblités en cours d'utilisation.
L'utilisation d'un dictionnaire pour une liste déroulante permet d'automatiser facilement le nettoyage et l'analyse de données. 
</p>

<p style="text-align:justify;">
⚠️Les dictionnaires sont censés être utilisé pour faire la traduction des variables catégorielles entre la table <i>llx_formulaireval</i> (codé en chiffres, normalement) et la table <i>llx_formulairefval</i> (valeur textuelle, normalement). Pour certaines variables, les modalités sont écrites textuellement dans les deux, et parfois codé enchiffres dans les deux.  
</p>

## llx_formulaire (pas de _c pour celui-ci)

*Remarque: llx_formulaire n'est pas à proprement parlé un dictionnaire au sens de dolibarr, c'est une table llié au module de signalement.*

Dictionnaire des modalités concernant le type de formulaire.

```rowid``` de *llx_formulaire* <-> variable ```fk_form``` de *llx_signalement*.

## llx_c_issue

Dictionnaire des modalités concernant le type de problématique associée à un signalement.

```rowid``` de *llx_c_issue* <-> variable ```fk_issue``` de *llx_signalement*.

## llx_c_occasion

Dictionnaire des modalités concernant le type d'évènement associé à un signalement.

```rowid``` de *llx_c_occasion* <-> variable ```evenement_signalement``` de *llx_formulaireval*.

## llx_c_proprietaire

Dictionnaire des modalités concernant le proprietaire de la donnée associée à un signalement.

```rowid``` de *llx_c_proprietaire* <-> variable ```proprietaire_data``` de *llx_formulaireval* (attention, parfois codé parfois non).

## llx_c_partenariat

Dictionnaire des modalités concernant le type de partenariat associé à un signalement.

```rowid``` de *llx_c_partenariat* <-> variable ```partenariat``` de *llx_formulaireval*.

## llx_c_sex_animal

Dictionnaire des modalités concernant le sexe de l'animal associé à un signalement.

```rowid``` de *llx_c_sex_animal* <-> variable ```sexe_animal``` de *llx_formulaireval* (attention, plus de modalités dans formulaireval que dans le dictionnaire).

## llx_c_sex_humain

Dictionnaire des modalités concernant le sexe de l'humain associé à un signalement.

```rowid``` de *llx_c_sex_humain* <-> variable ```qui_a_ete_pique``` de *llx_formulaireval* (attention, plus de modalités dans formulaireval que dans le dictionnaire).

