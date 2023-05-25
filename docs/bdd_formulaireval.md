# Table llx_formulaireval

<p style="text-align:justify;">
Cette table est censé être la même que la table <i>llx_formulairefval</i>, mais avec les variables factorielles recodées en chiffres et non en valaurs textuelles.
</p>

<p style="text-align:justify;">
:warning: Je ne connais pas le lien entre les deux tables, je ne sais pas laquelle a été créé à partir de l'autre. La description ci-dessous n'est donc qu'un constat de ce que j'observe, et des suppositions de ce qui a pu être fait à propos de cette table.
</p>
 
<p style="text-align:justify;">
La table <i>llx_formulaireval</i> contient beaucoup moins de lignes (environ 4000) que la table <i>llx_formualirefval</i>. On peut donc déjà supposer des lignes ont été supprimées à la main dans cette table à un moment, sans doute dans le but de faire u nettoyage en direct dans la base de données.
</p>
 
<p style="text-align:justify;"> 
Certaines variables catégorielles sont effectivement recodées en chiffres comparé à ce qui est donné dans la la table <i>llx_formulairefval</i>. Cependant, ce n'est pas le cas pour toutes les variables catégorielles....
</p>

<p style="text-align:justify;">
De plus, le codage entre les deux tables n'est pas toujours cohérent. On retrouve parfois des nombres de modalités différentes pour une même variable dans les deux tables (sans doute parfois des modalités qui ne sont plus utilisés maintenant, parfois des bugs, ....).
</p>
 
 
Liste des variables différant d'une table à l'autre :

- **piqure_en_france** : NA dans formulairefval <-> 0 ou 1 dans formualireval OU 1 dans formualirefval correspondant à 0 dans formulaireval ET 0 dans formulairefval correspondant à 1 dans formulaireval. 


- **email_signalement** :  NA dans formualirefval <-> adresse mail dans formulaireval (ex: fk_sig=100831)


- **avez_tique** : NA dans formulairefval <-> 0 (ex: fk_sig=30000) ou -1 dans formulaireval (ex: fk_sig=30011)


- **lieu_piqure** et **lieu_piqure_gps** (même différence) : "France" dans formulairefval <-> coordonnées GPS dans formualaireval (fk_sig=73676)


- **lieu_piqure_region** : NA dans formulairefval <-> -1 (ex: fk_sig=40990) ou nom d'une région dans formulaireval (ex: fk_sig=41092)


- **lieu_piqure_departement** : NA dans formulairefval <-> -1 (ex: fk_sig=30790) ou nom d'un département dans formulaireval (ex: fk_sig=30794)


- **nb_tique_implantee** : NA dans formulairefval <-> nombre <= 0 dans formulaireval (ex: fk_sig=79599) OU "centaine" dans formualirefval <-> 0 dans formulaireval (fk_sig=86583)


- **nom_pique** : NA dans formulairefval <-> nom dans formulaireval (ex: fk_sig=98696)


- **num_bea** : NA dans formulairefval <-> numéro BEA dans formulaireval (ex: fk_sig=56251)


- **origine** : NA dans formulairefval <-> Web1.0.4 dans formulaireval (ex: fk_sig=63446)


