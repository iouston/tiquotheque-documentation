# La base de données

<p style="text-align:justify;">
La base de données est un dépot où se trouve toutes les informations relatives aux signalements et envois de tiques receuillis dans le cadre du programme CiTIQUE. 
</p>

## Les tables

<p style="text-align:justify;">
La base de données est composées de différentes tables.
</p>
  
<p style="text-align:justify;">
Les tables étant créées à partir d'un CRM Dolibarr (la tiquothèque) pré-concu, de nombreuses tables et informations ne sont pas necessaires pour notre analyse. On va donc uniquement citer les tables que l'on utilise réellement, et au sein de ces tables, nous ne mentionneront que les variables utiles par soucis de clarté (ex: la table <i>llx_user</i> contient 78 variables alors que nous n'avons besoin que de trois d'entres elles).
</p>
 
<p style="text-align:justify;"> 
Les tables commencant par <i>llx_c_</i> sont des dictionnaires, <i>ie</i>, elles permettent de recoder des variables catégorielles (liste déroulante dans l'application) en liant une valeur textuelle à une valeur codée chiffrée. 
</p>
