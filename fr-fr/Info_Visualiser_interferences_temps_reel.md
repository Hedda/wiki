# Visualiser les interférences en temps réel

Une application en python permet de visualiser en temps réel l'utilisation des fréquences. 

## Méthode

* __Arréter le plugin__
* Ouvrir un terminal 
* Aller dans le répertoire du plugin. La commande est normalement <code>cd domoticz/plugins/Domoticz-Zigbee</code>
* Installer les paquets python nécessaire avec la commande : `sudo pip3 install jsonschema coloredlogs`
* Lancer la commande : `python3  -m zigpy_znp.tools.energy_scan /dev/ttyUSB0` en remplacant /dev/ttyUSB0 par celui de votre coordinateur.

Pour arréter le défilement, faire : __Ctrl+C__

Le résultat s'affiche sous cette forme

![Network Toplogy](../Images/real-time-topology.png)

__Note :__ Les meilleurs valeurs sont les plus faibles.