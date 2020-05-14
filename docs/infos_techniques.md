 # Informations techniques

 * Les versions IOS et Android appairées avec la tiquothèque sous dolibarr sont mis en service le 18/05/2020
 * L'application android est tout de suite passée en production dès le 13/05/2020
 * Les données de signalement de piqure depuis 2017 n'avaient pas encore pu être réintégrées dans la nouvelle tiquothèque
 * En conséquence, le choix a été fait de forcer la valeur de l'autoincrement de llx_signalement et de llx_formulaireval à 30 000.
 * De cette façon, il sera possible de réintégrer sans risque de mélange et de confusion les données ephytia, en forçant un id inférieur à 30 000
 * Sans que cela ne viennent perturber le fonctionnement des signalement entrés en production le 18/05/2020
 * Attention toutefois, le 17/05/2020 au soir, une remise à 0 des signalements est à réaliser en tenant compte des enregsitrements rééls qui peuvent survenir entre le 13/05/2020 et le 18/05/2020
 