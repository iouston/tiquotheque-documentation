 # Infos techniques signalements

## Relier un signalement à un compte utilisateur

* La tiquothèque ne permet pas de relier un compte urilisateur à un signalement ou inversement
* Il faudra donc passer par la base de données.
* Depuis la tiquothèqe, rechercher dans le moteur de recherche l'adresse mail du compte utilisateur et faites une recherche d'utilisateur. 
* Allez dans la fiche utilisateur et copier le champ 'id' indiqué dans la barre d'adresse. Gardez-ce numéro pour plus tard
* Connectez-vous au serveur et de là à phpmyadmin
* Allez dans la table llx_signalement et recherchez dans le champ ref la valeur de signalement donnné par l'utilisateur
* Copiez la valeur du champ rowid correspondante 
* Au niveau du champ fk_user, indiquez l'id du compte utilisateur que vous avez copié au début
* Valider. Le compte utilisateur et le signalement sont désormais liés.





