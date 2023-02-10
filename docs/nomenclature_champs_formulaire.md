 # Nomenclature des champs de formulaire

## Comment ça fonctionne ?
Cette nomenclature vous donne les éléments techniques utilisés par le logiciel de la tiquothèque et les équivalences entre les tables.

Les données de signalement sont organisées dans deux tables de base de données :
- llx_signalement qui stocke les informations générales sur le signalement
- llx_formulaireval qui stocke le détail des données de signalement. 1 colonne par champ de formulaire

# Pour la table llx_signalement

## Identifiant
- Type de champ : integer, numéro interne de la base de données. Permet de faire le lien avec 'fk_signalement' de la table 'llx_formulaireval'
- Code du champ : rowid

## Référence tiquothèque
- Type de champ : character, numéro de référence du signalement dans la tiquothèque (signalement ephythia : ref etia00001 à etia18280)
- Code de champ : ref

## ?
- Type de champ : (pas de track_id pour les signalements ephythia)
- Code de champ : track_id

## Signalement humain ou animal
- Type de champ : booléen
- Code de champ : for_human
- Valeurs utilisées :
* 1 = humain
* 0 = animal

## Type de formulaire
- Type de champ : liste déroulante (int dans la bdd, à factoriser), numéro indiquant le type de formulaire utilisé (7 formulaires actifs au 07/02/2023), issu d'un dictionnaire -> llx_formulaire ('rowid' de llx_formulaire donne les modalités utilisées)
- Code de champ : fk_form
- Valeurs utilisées :
* -1 = beug (humain avec formulaire animal) ?
* 0 = animal ? type de formulaire qui n'existe plus
* 1 = Humain général
* 4 = Animaux général
* 7 = Humains ONF
* 8 = Hyalom 
* 9 = Humains CNPF
* 10 = Humains IGN
* 11 = Humains OFB

## Date de création
/!\ BEUG ?
- Type de champ : date + heure, date de création du signalement
- Code de champ : datec

## Identifiant de l'auteur du signalement
- Type de champ : integer, numéro d'identification de l'auteur du signalement, issus d'un dictionnaire -> llx_user ('rowid' de llx_user donne le 'user_author_id' correspondant)
- Code de champ : user_author_id
- Valeurs des membres de l'équipe :
* 26645 = Sandrine Warion
* 24597 = Paul Fourrey
* 24390
* 27105
* ... = Jonas Durand
* ... = Julien Marchand
* ... = ...

## Numéro du profil 
- Type de champ : int, numéro de profil anonymisé associé au signalement (à relier avec 'nom_pique' de llx_formulairefval, /!\ le même nom peu apparaître pour des numéro de profil différents) 
- Code de champ :fk_profile

## Envoi accusé de réception
- Type de champ : booléen
- Code de champ : envoi_ar
- Valeurs utilisées :
* 0 = pas d'accusé de réception envoyé
* 1 = accusé de réception envoyé

## ?
- Type de champ : booléen
- Code de champ : entity
- Valeurs utilisées :
* 0 =
* 1 =

## ?
- Type de champ : booléen
- Code de champ : active
- Valeurs utilisées :
* 0 =
* 1 =

## ?
- Type de champ : booléen
- Code de champ : is_draft
- Valeurs utilisées :
* 0 =
* 1 =

## Problématique ?
- Type de champ : liste déroulante (int dans la bdd à factoriser), précise la problématique, issu d'un dictionnaire -> llx_c_issue ('rowid' de llx_c_issue donne la modalité associée)
- Code de champ : fk_issue
- Valeurs utilisées :
* 0 = NA
* 1 = "Tique libre"
* 2 = "Pas une tique"
* 3 = "Pas de distinction avec d'autres tiques"
* 4 = "Doublon au pointage"
* 5 = "Doublon au dépouillage"
* 6 = "Doublon base de données"
* 7 = "Tique absente de l'envoi"
* 8 = "Ce signalement est un test"
* 9 = "Doute sur tique libre"

## Date serveur / tms
/!\ pas même tms que pour llx_formulaireval (ni llx_formulairefval)
- Type de champ : date, heure serveur /!\correspond à la date et l'heure de la dernière modification du signalement!
- Code du champ : tms

# Pour la table llx_formulaireval
## rowid
- Type de champ : numero interne de la base de données. Sert d'identifiant pour la donnée
- Code du champ : rowid

## fk_signalement / Signalement
- Type de champ : numero interne de la base de données. Permet de faire le lien avec 'rowid' de la table 'llx_signalement'. 
Ce numéro correspond au numéro de signalement lié au détail du signalement
- Code du champ : fk_signalement

## Date serveur / tms
- Type de champ : date, heure serveur /!\correspond à la date et l'heure de la dernière modification du signalement!
- Code du champ : tms

## Date de naissance
- Type de champ : date
- Code du champ : date_naissance

## Age (ephythia)
- Type de champ : liste déroulante ?
- Code du champ : ephythia_age_personne_concernee
- Valeurs utilisées :
* 1 = "De 0 à 5 ans"
* 2 = "De 6 à 10 ans"
* 3 = "De 11 à 20 ans"
* 4 = "De 21 à 30 ans"
* 5 = "De 31 à 40 ans"
* 6 = "De 41 à 50 ans"
* 7 = "De 51 à 60 ans"
* 8 = "De 61 à 70 ans"
* 9 = "Plus de 70ans"


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

## Précision sur la date de la piqure / precision_date_piq
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
- Valeurs utilisées : /!\ Attention, Booléen monté à l'envers ! En même temps que 3 données au 11/01/2021. Ce champ sert-il encore ? Vu qu'on a le pays par ailleurs ? Est-ce juste pour les données ephythia ?
* 0,Oui
* 1,Non

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

## Caractérisation de l'environnement / carac_env_piq_old
- Type de champ : Liste déroulante
- Code du champ : carac_env_piq_old
- Valeurs utilisées :
* 0,jardinpriv_parcpub,Jardin privé ou Parc public

## Raison de la présence / raison_presence
- Type de champ : Liste issue d'un dictionnaire → llx_c_raison
- Code du champ : raison_presence
- Valeurs utilisées :
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

## Autre info
- Type de champ : Textarea
- Code du champ : autre_info

## Lieu de la piqûre
- Type de champ : varchar, coordonées GPS en WGS84. Latitude et Longitude sont séparées par une virgule
- Exemple : 48.600297119772726,7.25105132907629
- Code du champ :lieu_piqure 

## Sociologie
- Type de champ : Champ non utilisé à priori...
- Code du champ : 

## Sociologie détail
- Type de champ : Textarea, informations et témoignages socio fournis lors du signalement
- Code du champ : 

## Origine
- Type de champ : Varchar, L'origine et le type de signalement
- Code du champ : origine
* Android... : Systeme android
* iOS... : Système ios
* Web : Envoyé par le formulaire web en ligne
* fp : formulaire papier
* p : papier
- Exemple : Web 1.0.4 | Android 10 | iOS 14.3.0 | fp

## Origine numéro de lot
- Type de champ : Varchar, permet de conserver le numéro de lot inscrit en haut à droite sur certains formulaires papier
- Code du champ : origine_num_lot

## Evenement signalement
- Type de champ : Select, issu d'un dictionnaire → llx_c_occasion
- Code du champ : evenement_signalement
- Valeurs utilisées :
* 01,Ofrance2019
* 02,Caldenatienne 2019
* 03,Scouts 

## Propriétaire de la data
- Type de champ : Select, issu d'un dictionnaire → llx_c_propriétaire
- Code du champ : proprietaire_data
- Valeurs utilisées :
* citique,CiTIQUE

## Partenariat
- Type de champ : Select, issu d'un dictionnaire → llx_c_partenariat
- Code du champ : partenariat
- Valeurs utilisées :
* onf,ONF
* sgdf,Scouts et Guides de France

## Primeur de la data
- Type de champ : Date, date après laquelle le propriétaire n'a plus de primeur sur la donnée. 
Par défaut, +365 jours par rapport à la date de saisie. Voir le champ tms
- Code du champ : primeur_data

## email_signalement17
- Type de champ : Champ inutilisé à priori
- Code du champ : 

## id_ephythia17
- Type de champ : Champ inutilisé à priori
- Code du champ : 

## Précision zone géographique / precis_zone_geo
- Type de champ : Liste déroulante
- Code du champ : precis_zone_geo
- Valeurs utilisées :
* -1,vide / champ non obligatoire
* 0,Je ne connais pas le lieu de la piqûre
* 1,Je connais le lieu de la piqûre

## Précision coordo géographique / precis_coordo_gps
- Type de champ : Liste déroulante
- Code du champ : precis_coordo_gps
- Valeurs utilisées :
* 0,-1,moins de 1km
* 1,1a5,entre 1 et 5 km
* 2,plus5,plus de 5km 

## Précision lieu si autre
- Type de champ : Textarea, précision détaillée si le lieu choisi est 'autre'
- Code du champ : precis_lieu_si_autre

## Précision si activité profesionnelle
- Type de champ : Varchar, permet de préciser une raison si on a choisi 'activité professionnelle'
- Code du champ : precis_si_act_pro

## Photos
- Type de champ : varchar, nom du fichier séparé par une virgule.
Le fichier est renomé avec la référence du signalement comme par exemple : 026586_Photo_1.png,026586_Photo_2.png,026586_Photo_3.png
- Code du champ : photos

## Lieu piqure ville
- Type de champ : varchar, le nom de la ville en toute lettre
- Code du champ : lieu_piqure_ville

## Lieu piqure département
- Type de champ : varchar, le nom du département en toute lettre
- Code du champ : lieu_piqure_departement

## Lieu piqure région
- Type de champ : varchar, le nom de la région en toute lettre
- Code du champ : lieu_piqure_region

## Lieu piqûre pays
- Type de champ : varchar, le nom du pays en toute lettre
- Code du champ : lieu_piqure_pays

## Zone du corps piqué / zone_corps_pique
- Type de champ : Liste déroulante
- Code du champ : zone_corps_pique
- Valeurs utilisées :
* 1,bras,Bras
* 2,dos,Dos
* 3,fesses, Maillot
* 4,jambe,Jambe
* 5,main,Main
* 6,pied,Pied
* 7,tete,Tête
* 8,torse,Torse et ventre 

## Type d'animal
- Type de champ : champ qui ne semble pas utilisé, on utilise plutôt le champ issu du profil de l'animal
- Code du champ : 

## Sexe animal
- Type de champ : Select issu d'un dictionnaire → llx_c_sex_animal
- Code du champ : sexe_animal
- Valeurs utilisées :
* 1,mâle
* 2,femelle

## Nom piqué
- Type de champ : varchar, nom du profil sélectionné
- Code du champ : nom_pique

## Zone corps animal
- Type de champ : Select
- Code du champ : zone_corps_animal
- Valeurs utilisées :
* 1,croupe, Croupe, queue
* 2,dos,Dos
* 3,pattesarr,Pattes arrières
* 4,pattesavt,Pattes avants
* 5,tete,Tête / cou
* 6,ventre,Ventre

## Est traité ?
- Type de champ : Select, l'animal est-il traité contre les tiques ?
- Code du champ : est_traite
- Valeurs utilisées : 
* 0,non,Non
* 1,oui,Oui

## Quel traitement ?
- Type de champ : textarea, permet de préciser le traitement reçu dans un texte libre
- Code du champ : quel_traitement

## Avez tique ?
- Type de champ : Select, permet à l'utilisateur d'indiquer si il dispose de l'échantillon ou non
- Code du champ : avez_tique
- Valeurs utilisées : 
* 0,non,Non elle a été détruite ou perdue
* 1,oui,Oui Je vais pouvoir vous l'envoyer

## Num bea
- Type de champ : varchar, un numéro d'identification noté sur les échantillons dans les congélateurs. 
Un numéro BEA correspond à un lot d'échantillon (tous ceux d'une enveloppe en fait). Le numéro BEA porte ce nom en référence à Béatrice (Béa) pallin qui a été la première tiquothécaire du projet
- Code du champ : num_bea

## Type formulaire papier
- Type de champ : Select, permet de préciser le type de formulaire papier, issu d'un dictionnaire ???
- Code du champ : typeformulairepapier
- Valeurs utilisées :
* 0,papierlibre,Papier libre
* 1,formulairekit,Formulaire avec Kit
* 2,formulairesanskit,Formulaire sans Kit
* ,Formulaire indéterminé
* ,Signalement app/web + kit

## Partenariat
- Type de champ : liste déroulante
- Code de champ : partenariat
- Valeurs utilisées :
* ONF
* Scouts et Guides de France

## Sociologie détail (notes)
-Type de champ : champ libre
- Code de champ : sociologie_detail

## Sociologie type
- Type de champ : liste déroulante (spécifique à la tiquothèque, rempli par un membre de CiTIQUE)
- Code de champ : sociologie_type
- Valeurs utilisées :
* Présence d'un courrier d'accompagnement
* Excuses pour l'emballage
* Demande d'analyse et de résultat
* Demande information sur tique
* Application qui ne marche pas
* Remerciements
* Pas content

## Age personne piquée (ephythia)
- Type de champ : liste déroulante
- Code de champ : ephythia_age_personne_concernee
- Valeurs utilisées :
* ----
* De 1 à 5 ans
* De 6 à 10 ans
* De 11 à 20 ans
* De 21 à 30 ans
* De 31 à 40 ans
* De 41 à 50 ans
* De 51 à 60 ans
* Plus de 70 ans

## Statut
- Type de champ : 
- Code de champ :
- Valeurs utilisées :
* indéfini
* valide
* annule

## Détails statut 
/!\ Différent de fk_issue dans llx_signalement
- Type de champ : cases à coher avec plusieurs choix possibles (doit devenir liste déroulante)
- Code de champ : detail_statut
- Valeurs utilisées :
* Tique libre
* N'est pas une tique

# Champs relatifs au formulaire spécifique CNFP

> [!WARNING]
> Tous les champs relatifs au cnpf doivent être préfixés avec "cnpf_"


## Catégorie professionnelle
- Type de champ : Select, permet de préciser la catégorie professionnelle
- Code du champ : cnpf_cat_pro
- Valeurs utilisées :
* 1,perso_admin,Personnel administratif
* 2,tech,Technicien
* 3,inge,Ingénieur
* 4,perso_direction,Personnel direction

## Structure de rattachement
- Type de champ : Select, permet de préciser la structure de rattachement
- Code du champ : cnpf_struc_rattach
- Valeurs utilisées :
* 1,idf,Ile de France
* 2,deleg_reg,Délégation régionale
* 3,dir_gale,Direction générale

## Raison de la présence sur le lieu de la piqure
- Type de champ : Select, permet de préciser la raison de la présence sur le lieu de la piqûre
- Code du champ : cnpf_struc_rattach
- Valeurs utilisées :
* 1,visi_instru_cons,Visite instruction/conseil
* 2,mesur_disp,Mesures de dispositifs
* 3,formation,Formations

## Environnement de la piqûre
- Type de champ : cases à cocher, permet de préciser le ou les environnements de la piqure
- Code du champ : cnpf_carac_env
- Valeurs utilisées :
* 1,foret,Forêt
* 2,zoneurbaine,Zone urbaine
* 3,parcpublic,Jardin public ou parc public
* 4,pre,Pré
* 5,zonagricult,Zone agricole cultivée
* 6,zone_veg_arb,Zone à végétation arbustive (pelouses naturelles, landes, broussailles...)
* 7,esp_nat_ouv_peu_veg,Espace naturel ouvert peu végétalisé (dunes/zone incendiée/roches nues...)
* 8,zone_humi,Zone humide
* 9,jnsp,Je ne sais pas

## Raison de la présence sur le lieu de la piqure
- Type de champ : Select, permet de préciser la raison de la présence sur le lieu de la piqûre
- Code du champ : cnpf_struc_rattach
- Valeurs utilisées :
* 1,visi_instru_cons,Visite instruction/conseil
* 2,mesur_disp,Mesures de dispositifs
* 3,formation,Formations

## Composition du peuplement forestier parcouru
- Type de champ : liste de sélection, permet de préciser la composition du peuplement forestier parcouru
- Code du champ : cnpf_compo_peup_foret
- Valeurs utilisées :
* 1,peup_feuillus,Peuplement pur de feuillus
* 2,peup_conifere,Peuplement pur de conifères
* 3,peup_mixte,Peuplement de feuillus et de conifères
* 4,jnsp,Je ne sais pas

## Structure du peuplement forestier
- Type de champ : liste de sélection, permet de préciser la structure du peuplement forestier parcouru
- Code du champ : cnpf_structure_compo_peup_foret
- Valeurs utilisées :
* 1,futaie_regu,Futaie régulière
* 2,futaie_irreg,Futaie irrégulière
* 3,melange_fut_taill,Mélange taillis et futaie
* 4,taillis,Taillis
* 5,autre,Autre

## Age du peuplement forestier
- Type de champ : liste de sélection, permet de préciser la structure du peuplement forestier parcouru
- Code du champ : cnpf_age_peup
- Valeurs utilisées :
* 1,semi,Semis
* 2,jeune,Jeune peuplement
* 3,adulte,Peuplement adulte
* 4,mur,Peuplement mûr
* 5,toutage,Tout âge

## Combien de temps passé sur le lieu de la piqûre
- Type de champ : liste de sélection, permet de préciser le temps passé sur les lieux de la piqûre
- Code du champ : cnpf_tps_lieu_piq
- Valeurs utilisées :
* 1,1a2h,1 à 2 heures
* 2,demij,1 demi-journée
* 3,journee,1 journée
* 4,jnsp,Je ne sais pas

## Quels moyens de protection avez-vous utilisé ?
- Type de champ : cas à cocher, permet de préciser les moyens de protection utilisés
- Code du champ : cnpf_moyens_protect
- Valeurs utilisées :
* 0,aucun,Aucune protection
* 1,vet_couv_ht_corps,Vêtements couvrants le haut du corps
* 2,vet_couv_bas_corps,Vêtements couvrants le bas du corps
* 3,guetres,Guêtres
* 4,repulsif_vet,Répulsif sur les vêtements
* 5,repulsif_peau,Répulsif sur la peau
* 6,autre,Autre

## Précisez
- Type de champ : texte libre, permet de préciser le répulsif utilisé et/ou le champ autre
- Code du champ : cnpf_precision_repulsif_et_autre

## Par quel moyen la tique a-t-elle été retirée ?
- Type de champ : liste de sélection, permet de préciser par quel moyen la tique a été retirée
- Code du champ : cnpf_facon_retire_tiq
- Valeurs utilisées :
* 1,tiretiq,Tire-tique
* 2,pinceepiler,Pince à épiler
* 3,autre,Autre

## Précisez autre
- Type de champ : texte libre, permet de préciser le répulsif utilisé et/ou le champ autre
- Code du champ : cnpf_precision_retiree_autre

## Avez-vous désinfecté
- Type de champ : case d'option, permet de préciser si la zone de la piqûre a été désinfectée après extraction
- Code du champ : cnpf_desinfect
- Valeurs utilisées :
* 0,non,Non
* 1,oui,Oui

## Avec quel délai avez-vous retiré la tique après l'avoir détectée
- Type de champ : case d'option, permet de préciser au bout de combien de temps la tique a été retirée après avoir été détectée
- Code du champ : cnpf_delai_retire_tique
- Valeurs utilisées :
1,toutsuite,Tout de suite
2,moins3h,Moins de 3h
3,3a15h,Entre 3 et 6h
4,6a9h,Entre 6 et 9h
5,9a12,Entre 9 et 12h
6,12a24,Entre 12 et 24h
7,plusde24h,Plus de 24h

## Heure de piqûre
- Type de champ : à cocher, permet de préciser un créneau horaire pour la piqûre
- Code du champ : cnpf_heure_piqure
- Valeurs utilisées :
0,8a10,Entre 8h et 10h
1,10a12,Entre 10h et 12h
2,12a14,Entre 12h et 14h
3,14a16,Entre 14 et 16h
4,16a18,Entre 16h et 18h

# Champs relatifs au formulaire spécifique OFB

> [!WARNING]
> Tous les champs relatifs à l'OFB doivent être préfixés avec "ofb"


## Catégorie professionnelle
- Type de champ : Select, permet de préciser la catégorie professionnelle
- Code du champ : ofb_cat_pro
- Valeurs utilisées :
* 1,ofb_perso_admin,Personnel administratif
* 2,ofb_perso_terrain,Personnel de terrain

## Heure Piqure
- Type de champ : Select, permet de préciser la catégorie professionnelle
- Code du champ : ofb_heure_piqure
- Valeurs utilisées :
* 1,hpiq_m,Matin
* 2,hpiq_apm,Après-midi
* 3,hpiq_s,Soir
* 4,hpiq_jnspa,Je ne sais pas
