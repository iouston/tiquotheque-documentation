 # Nomenclature des champs de formulaire

## Comment ça fonctionne ?
Cette nomenclature vous donne les éléments techniques utilisés par le logiciel de la tiquothèque et les équivalences entre les tables

## Caractérisation de l'environnement / caracterisation_env_piqure
-Type de champ : Liste issue d'un dictionnaire → llx_c_caracterisation
- Code du champ : caracterisation_env_piqure
-Valeurs utilisées :
1,autre,Autre
2,foret,Forêt
3,jardinparc,Jardin privé ou parc municipal
4,prairie,Prairie
5,zonagricult,Zone agricole cultivée
6,planeau,Plan d'eau
7,domicile,Domicile / maison (en intérieur)
8,jardinpriv,Jardin privé
9,parcpublic,Parc public / municipal

## Champ - précision sur la date de la piqure / precision_date_piq
-Type de champ : Liste déroulante
- Code du champ : precision_date_piq
-Valeurs utilisées :
0,a2jp,A 2 ou trois jours près
1,jcde,Je connais la date exacte
2,jcpd,Je ne connais pas la date

## Champ - précision coordo géographique / precis_coordo_gps
-Type de champ : Liste déroulante
- Code du champ : precis_coordo_gps
-Valeurs utilisées :
0,-1,moins de 1km
1,1a5,entre 1 et 5 km
2,plus5,plus de 5km 

## Champ - précision zone géographique / precis_zone_geo
-Type de champ : Liste déroulante
- Code du champ : precis_zone_geo
-Valeurs utilisées :
0,Je ne connais pas le lieu de la piqûre
1,Je connais le lieu de la piqûre


## Champ - zone du corps piqué / zone_corps_pique
-Type de champ : Liste déroulante
- Code du champ : zone_corps_pique
-Valeurs utilisées :
1,bras,Bras
2,dos,Dos
3,fesses, Fesses
4,jambe,Jambe
5,main,Main
6,pied,Pied
7,tete,Tête
8,torse,Torse et ventre


