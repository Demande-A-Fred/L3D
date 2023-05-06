# L3D


## Montage
(Img/Leds.jpg)

## Flashage

Pour flasher la carte avec le programme au complet il suffit de suivre le lien suivant et suivre la procédure. \
https://demande-a-fred.github.io/L3D/esp.html

**Attention TOUTES les données présentes sur la carte seront éffacées**

La toute première fois il est possible que vous n'aillez pas le pilote de la carte qui soit présent sur votre machine.\
La page de mise à jour propose de télécharger des pilotes.\
Suivez le lien de téléchargement proposé par l'installeur, installez les pilotes et ouvez à nouveau le lien de flashage au dessus.\
Pour les ESP de chez AZ Delivery c'est le CP2102 (le premier lien)

## Mise à jour OTA ##

Il est possible de faire des mises à jour à distance (sans cable) après que la carte ait été flashée une première fois par l'outil web.\
Il suffit d'ouvrir votre navigateur sur la carte concernée (par adresse http://ip.de.la.carte ou par son nom, par défaut http://l3d.local). Allez dans l'onglet **Configuration** puis dans la section **Mise à jour OTA**.\


   
### Firmware ###

Télécharger le nouveau firmware depuis le dossier **OTA** de cette page Github.\
Sur la page de mise à jour OTA de la carte, selectionner **"Firmware"** puis le glisser/déposer dans la fenêtre de mise à jour et suivre le reste de la procédure.

Les données de réglages, de configuration, et de séquences seront conservées.



### Filesystem ###
**Uniquement pendant la phase de test**\
Il est possible de faire la mise à jour de la partie Web de la carte par cette même page OTA.

Télécharger le nouveau Filesystem depuis le dossier **OTA** de cette page Github.\
Sur la page de mise à jour OTA de la carte, selectionner **"Filesystem"** puis le glisser/déposer dans la fenêtre de mise à jour et suivre le reste de la procédure.

**Attention TOUTES les données présentes sur la carte seront éffacées**\
*Les fichiers Web seront placés dans le code une fois qu'ils auront passé les phases de test et il ne sera plus possible de faire des mises à jour de Filesystem et ainsi de perdre donc les réglages.\
Leur mise à jour se fera en même temps que le reste du firmware\
Il est toujours possible d'éffacer les fichiers de réglages de la carte par la page de configuration*
