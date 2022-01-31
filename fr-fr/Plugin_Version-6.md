<a href="Home.md"><img align="left" width="80" height="80" src="../Images/logo_Z4D.png" alt="Logo"></a>

# Explications pour passer de la version 5 à la version 6 plugin.

</br>

__Note :__ Ces explications sont valables pour une installation sous Linux.


## Prérequis

Avant de commencer la procédure, vous devez :

* Avoir une version de DomoticZ 2021.1 au minimum.
* Être sur la branche __Stable5__ du plugin. Commande `git checkout stable5` si besoin.
* Avoir la dernière version du plugin. Commande `git pull` si besoin.


## Sauvegarde

Même si la procédure a été testé plusieurs fois, il est possible que les choses ne se passent pas comme prévus.
Il est recommandé de faire une sauvegarde complète pour pouvoir revenir en arrière si besoin.
Pensez à sauvegarder :

* DomoticZ
* Les données du plugin
* Le système d'exploitation


## Procédure

* Ouvrir le terminal
* Aller dans le répertoire du plugin. La commande est normalement <code>cd domoticz/plugins/Domoticz-Zigate</code>
* Exécuter la commande : `git remote set-url origin https://github.com/zigbeefordomoticz/Domoticz-Zigbee`
* Installer les paquets Python nécessaire avec la commande : `sudo pip3 install voluptuous pycrypto aiosqlite crccheck pyusb attr attrs aiohttp pyserial-asyncio`

Le temps de la phase de développement, il faut passer sur la nouvelle branche beta6 : `git checkout beta6`

* Installer les librairies Python manquantes avec la commande : `git submodule update --init --recursive`
* Rendre le fichier __plugin.py__ exécutable en lançant la commande : `sudo chmod +x plugin.py`
* Redémarrer DomoticZ.

Normalement, le nom du plugin dans matériel est devenu __ZigBee for DomoticZ__.

A partir de maintenant, le terme ZiGate est remplacé par __coordinateur__, plus générique.

Si vous avez déjà un plugin configuré avec une ZiGate comme coordinateur, vous n'avez rien à faire : le plugin doit continuer à fonctionner normalement.


## Le paramétrage

Il y a 4 modèles de coordinateurs possibles :

* ZiGate : aucune modification sur le fonctionnement du plugin existant.
* ZiGate + : aucune modification sur le fonctionnement du plugin existant.
* ZiGate (via zigpy) : le plugin communique avec la ZiGate avec les librairies zigpy. C'est uniquement expérimental et n'est pas supporté.
* Texas Instruments ZNP : pour les nouveaux coordinateurs de marque TI.



## IMPORTANT Mise à jour du plugin

Le `git pull` n'est plus suffisant, il faut maintenant faire la commande `git pull --recurse-submodules`.
