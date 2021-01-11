 # Nomenclature des champs de formulaire

## Comment ça fonctionne ?
Cette nomenclature vous donne les éléments techniques utilisés par le logiciel de la tiquothèque et les équivalences entre les tables

Les données de signalement sont organisées dans deux tables de base de données :
- llx_signalement qui stocke les informations générales sur le signalement
- llx_formulaireval qui stocke le détail des données de signalement. 1 colonne par champ de formulaire

# Pour la table llx_signalement


# Pour la table llx_formulaireval
## rowid
- Type de champ : numero interne de la base de données. Sert d'identifiant pour la donnée
- Code du champ : rowid

## fk_signalement / Signalement
- Type de champ : numero interne de la base de données. Permet de faire le lien avec la table 'llx_signalement'. 
Ce numéro correspond au numéro de signalement lié au détail du signalement
- Code du champ : fk_signalement

## Date serveur / tms
- Type de champ : date, heure serveur
- Code du champ : tms

## Date de naissance
- Type de champ : date
- Code du champ : date_naissance

## ID ephythia
- Type de champ : integer
- Code du champ : Numéro propre à ephythia (la première version de l'application stockait les données dans l'applicatif ephythia).
Cette colonne permet de garder le numéro id du signalement tel qu'il était dans ephythia.

## Email du signalement 
- Type de champ : varchar, l'email saisi par l'utilisateur ou provenant de son compte ou de son profil lors de la saisie d'un signalement
- Code du champ : email_signalement

## Qui a ete piqué ?
- Type de champ : varchar
- Code du champ : qui_a_ete_piqué
- Valeurs utilisées :
* 1,H,Homme
* 2,F,Femme

## Statut (du signalement)
- Type de champ : Statut du signalement
- Code du champ : statut
- Valeurs utilisées :
* -1,annule
* 0,indéfini
* 1,valide

## Nombre de tiques implantée
- Type de champ : integer, le nombre de tiques fixées
- Code du champ : nb_tiques_implantee

## Champ - précision sur la date de la piqure / precision_date_piq
- Type de champ : Liste déroulante
- Code du champ : precision_date_piq
- Valeurs utilisées :
* 0,a2jp,A 2 ou trois jours près
* 1,jcde,Je connais la date exacte
* 2,jcpd,Je ne connais pas la date

## Date de la piqûre
- Type de champ : Date
- Code du champ : date_piqure

## La piqûre a eu lieue en France ?
- Type de champ : boolean
- Code du champ : piqure_en_france
- Valeurs utilisées :
* 0,Non
* 1,Oui

## Caractérisation de l'environnement / caracterisation_env_piqure
- Type de champ : Liste issue d'un dictionnaire → llx_c_caracterisation
- Code du champ : caracterisation_env_piqure
- Valeurs utilisées :
* 1,autre,Autre
* 2,foret,Forêt
* 3,jardinparc,Jardin privé ou parc municipal
* 4,prairie,Prairie
* 5,zonagricult,Zone agricole cultivée
* 6,planeau,Plan d'eau
* 7,domicile,Domicile / maison (en intérieur)
* 8,jardinpriv,Jardin privé
* 9,parcpublic,Parc public / municipal

## Raison de la présence / raison_presence
- Type de champ : Liste issue d'un dictionnaire → llx_c_raison
-Code du champ : raison_presence
-Valeurs utilisées :
* 1,pro,Activité professionnelle
* 2,resid,Lieu de résidence
* 3,randprompiq,Randonnée, promenade, pique-nique
* 4,scol,Milieu scolaire
* 5,loisir,Loisir
* 6,chassepeche,Chasse, pêche
* 7,sport,Sport
* 8,scouti,Scoutisme
* 9,clsh,Centre de loisirs / colo / camp
* 10,autre,Autre

## Champ - précision coordo géographique / precis_coordo_gps
- Type de champ : Liste déroulante
- Code du champ : precis_coordo_gps
- Valeurs utilisées :
* 0,-1,moins de 1km
* 1,1a5,entre 1 et 5 km
* 2,plus5,plus de 5km 

## Champ - précision zone géographique / precis_zone_geo
- Type de champ : Liste déroulante
- Code du champ : precis_zone_geo
- Valeurs utilisées :
* 0,Je ne connais pas le lieu de la piqûre
* 1,Je connais le lieu de la piqûre



## Champ - zone du corps piqué / zone_corps_pique
- Type de champ : Liste déroulante
- Code du champ : zone_corps_pique
-Valeurs utilisées :
* 1,bras,Bras
* 2,dos,Dos
* 3,fesses, Fesses
* 4,jambe,Jambe
* 5,main,Main
* 6,pied,Pied
* 7,tete,Tête
* 8,torse,Torse et ventre


