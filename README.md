# L3D
**Version Alpha, en phase de test**

L3D est un projet de séquenceur d'effets pour bandeau LED qui permet de créer des effets lumineux personnalisés, de déclencher des sons et de réagir à la distance à l'aide d'un capteur ultrason.

L3D est un mélange d'ESP32 et des rubans LED qui crée une expérience de lumière et de son synchronisée. J'ai travaillé pour concevoir une carte ESP32 qui contrôle les Leds et permet d'ajouter des effets de lumière pour créer une atmosphère immersive.

En plus de cela, j'ai également ajouté une fonctionnalité optionnelle pour lire des fichiers audio en utilisant un DFMiniPlayer connecté à l'ESP32. Cette fonctionnalité permet de synchroniser la lumière et le son pour une expérience encore plus immersive. En utilisant un capteur ultrason, les utilisateurs peuvent même interagir avec l'ensemble pour lire et arrêter la lecture.

Le séquenceur d'effet est intégré dans l'ESP32 et est facile à personnaliser. Une page web connectée à la carte permet d'ajouter des séquences supplémentaires et d'ajuster tous les autres réglages, tels que le volume, la luminosité et la découpe du bandeau de Leds en segments virtuels.

Si vous êtes intéressé par les effets de lumière et de son, alors ce projet est fait pour vous !


1. [Fonctionnement](#fonctionnement)
2. [Montage](#montage)
3. [Connexion](#connexion)
4. [Flashage](#flashage)
5. [Mise à jour par OTA](#mise-%C3%A0-jour-ota)
   
## Fonctionnement 

L3D est un projet qui permet de créer des séquences lumineuses personnalisées en appliquant des effets visuels sur des segments de rubans LED.\
Le bandeau peut être divisé virtuellement en plusieurs zones, appelées segments, qui peuvent se superposer si nécessaire. Jusqu'à huit séquences peuvent être exécutées simultanément sur huit pistes différentes.

Les effets lumineux peuvent être configurés avec des réglages personnalisés tels que des couleurs et des vitesses.\
Chaque séquence est définie par un temps de début et une durée.\
Il est également possible de déclencher des sons en même temps que les effets lumineux en utilisant un DFMiniPlayer qui stocke les fichiers MP3 sur une carte SD.\
Les fichiers doivent être numérotés avec quatre chiffres, par exemple, 0001.mp3, 0002.mp3, etc.

L3D peut être démarré ou arrêté à l'aide d'un capteur ultrason HC-SR04 ou d'un bouton.

Tous les réglages, y compris les effets lumineux, les segments, les pistes, les temps de début et de fin, les couleurs et les vitesses, peuvent être facilement configurés depuis une page web.

Notez que pour le moment, seul le capteur ultrason HC-SR04 est pris en charge par L3D.


## Montage

### Led Strip WS2812B sans alimentation (6/8 Leds) | par Usb uniquement
Pin 2 utilisée pour le signal Data vers le Led Strip
![alt](Img/Led_Usb_bb.jpg)

### Led Strip WS2812B uniquement | avec alimentation
- Pin 2 utilisée pour le signal Data vers le Led Strip
![alt](Img/Leds.jpg)

### DFMiniPlayer uniquement | avec alimentation
Carte SD de 32Go maximum, les fichiers doivent être numérotés à 4 chiffres 0001.mp3, 0002.mp3, ....
- Pin 16 vers TX du DFMiniPlayer
- Pin 17 vers RX du DFMiniPlayer
![alt](Img/mp3_bb.jpg)

### HC-SR04 uniquement | avec alimentation
- Pin 12 vers Trig du capteur HC-SR04
- Pin 14 vers Echo du capteur HC-SR04
![alt](Img/hc-sr04_bb.jpg)

### Leds Strip WS2812B, DFMiniPlayer, HC-SR04 | avec alimentation
Carte SD de 32Go maximum, les fichiers doivent être numérotés à 4 chiffres 0001.mp3, 0002.mp3, ....
- Pin 2 utilisée pour le signal Data vers le Led Strip
- Pin 16 vers TX du DFMiniPlayer
- Pin 17 vers RX du DFMiniPlayer
- Pin 12 vers Trig du capteur HC-SR04
- Pin 14 vers Echo du capteur HC-SR04
![alt](Img/all_bb.jpg)

## Connexion

Une fois connectée sur votre réseau Wifi la carte se retrouve par défaut à l'adresse http://l3d.local

### Mode Acces Point
En cas de problème de connexion wifi la carte va démarrer en mode AP (Acces Point). Elle se comporte comme une borne wifi sur laquelle vous pouvez vous connecter avec les paramètres suivants\
ssid : L3DAP\
mot de passe : tonystark\
Ouvrir ensuite une page de navigateur sur http://7.7.7.7 (parfois http://192.168.4.1)

## Flashage

Pour flasher la carte avec le programme au complet il suffit de suivre le lien suivant et suivre la procédure.\
Après flashage la carte va redémarrer et l'installeur Web va proposer de connecter la carte à votre wifi.

Le Web installeur se trouve à l'adresse suivante \
https://demande-a-fred.github.io/L3D/esp.html

Après un flashage réussi, le Web installeur proposera de connecter la carte au réseau wifi.

**Attention TOUTES les données présentes sur la carte seront éffacées**

Lors du tout premier flashage il est possible que la carte n'apparaisse pas si le pilote de la carte n'est pas installé sur votre machine.\
La page de mise à jour propose de télécharger des pilotes.\
Suivez le lien de téléchargement proposé par l'installeur, installez les pilotes et ouvez à nouveau le lien de flashage au dessus.\
Pour les ESP de chez AZ Delivery c'est le CP2102 (le premier lien)


## Mise à jour OTA

Il est possible de faire des mises à jour à distance (sans cable) après que la carte ait été flashée une première fois par l'outil web.\
Il suffit d'ouvrir votre navigateur sur la carte concernée (par adresse http://ip.de.la.carte ou par son nom, par défaut http://l3d.local). Allez dans l'onglet **Configuration** puis dans la section **Mise à jour OTA**.


   
### Firmware

Télécharger le nouveau firmware depuis le dossier **OTA** de cette page Github.
Sur la page de mise à jour OTA de la carte, selectionner **"Firmware"** puis le glisser/déposer dans la fenêtre de mise à jour et suivre le reste de la procédure.

**Les données de réglages, de configuration, et de séquences seront conservées.**



### Filesystem
**Fonctionnalité présente uniquement pendant la phase de test Alpha/Beta**\
Il est possible de faire la mise à jour de la partie Web de la carte par cette même page OTA.

Télécharger le nouveau Filesystem depuis le dossier **OTA** de cette page Github.\
Sur la page de mise à jour OTA de la carte, selectionner **"Filesystem"** puis le glisser/déposer dans la fenêtre de mise à jour et suivre le reste de la procédure.

**Attention TOUTES les données présentes sur la carte seront éffacées\
Pensez à sauvegarder vos réglages dans des fichiers avant la mise à jour de la partie Filesystem.**
