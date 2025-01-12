![Work_In_Progress](https://img.shields.io/badge/Work_In_Progress-Project_still_in_development-red?logo=adblock&logoColor=red&style=plastic)
[![Realease](https://img.shields.io/badge/Realease-v1.0.1-blue?style=plastic)](https://github.com/SeByDocKy/pvbrain2)

# PVbrainV2

![pvbrain_v2_logo](https://github.com/SeByDocKy/pvbrain2/assets/82636574/31fc03fe-0d92-4f01-9dd6-2457bfda07ad)

> [!IMPORTANT]
> Le <sub>[![PvBrain-v2.0](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2)</sub> est un projet open-source/open-hardware pour surveiller/contrôler : __`SIMULTANÉMENT`__ :
> - Plusieurs onduleurs. <sup>`(PIPsolar/Voltronic, Deye, Growatt, Sofar, Victron, etc...)`</sup> 
> - Et plusieurs BMS. <sup>`(JKBMS, AntBMS, DalyBMS, SeplosBMS, Pylontech, etc...)`</sup>
> 
> <sup>-> _En théorie, n'importe quel onduleur ou BMS supporté par ESPhome peut être utilisé avec le PVbrain2._</sup>
> 
> Il ajoute également la possibilité de contrôler jusqu'à 32 relais <sup>(voir plus encore)</sup> permettant par exemple de contrôler un **A**utomatic **T**ransfer **S**witch <sup>(ATS / Commutateur de transfert automatique)</sup> _(Hors réseau<=>retour au réseau)_. 
> 
> Le PCB utilise uniquement des composants traversant ou enfichables afin de faciliter la configuration/maintenance. 
> 
> Le MCU utilisé est un [ESP32S3](https://s.click.aliexpress.com/e/_DCEPtOd) fonctionnant sous <sub>[![ESPHome](https://img.shields.io/badge/ESPHome-_-black?logo=esphome&style=social)](https://esphome.io)</sub> permettant la communication native via WiFi sur <sub>[![Home_Assistant](https://img.shields.io/badge/Home_Assistant-_-black?logo=homeassistant&style=social)](http://homeassistant.io)</sub> <sup>(HA)</sup>.<br/>
> <sup>-> _Mais le </sup>[![MQTT](https://img.shields.io/badge/MQTT-_-black?logo=mqtt&style=social)](https://esphome.io/components/mqtt)<sup> peut être ajouté facilement._</sup>
> 
> __Les principales caractéristiques sont :__
> - [x] Communication et contrôle directs avec les onduleurs Voltronic/Pipsolar, DEYE, SOFAR, GROWATT via un câble Ethernet direct.<br/> <sup>_(Le pvbrain dispose d'un convertisseur [RS232](https://a.aliexpress.com/_EzMcqvP) et [RS485](https://a.aliexpress.com/_EzS7TkZ)  => TTL intégré)_</sup>
> - [x] Prise en charge du __CANbus__. Possibilité de traduire les informations des BMS d'ancienne génération vers les protocoles CANbus modernes (Pylontech 1.2, Pylontech +, SMA, Victron).
> - [x] Le __VEdirect__ pour les modèles <sub>![VICTRON](https://img.shields.io/badge/VICTRON-_-black?logo=victronenergy&style=social)</sub> avec un adaptateur isolé fourni.
> - [x] Les paramètres importants peuvent être définis directement depuis HA <sup>_(ou le serveur Web s'il est activé)_</sup>.
> - [x] Monitorer/Surveillez plusieurs BMS <sup>_(testé avec JKBMS mais devrait fonctionner avec antBMS, DalyBMS PaceBMS ou SeplosBMS)_</sup> avec un adaptateur isolé fourni.
> - [x] Détecter plusieurs sources AC <sup>_(solaire/réseau/autre)_</sup> (afin par exemple de réaliser une commutation logicielle pour la partie ATS).
> - [x] Surveiller via un module <sup>_(modbus)_</sup> [JSY193](https://s.click.aliexpress.com/e/_on7Sa7z), [JSY194T](https://s.click.aliexpress.com/e/_okyO6ht) la production solaire et réseau.
> - [x] Contrôlez jusqu'à 32 relais avec deux extensions i2c [SX1509](https://esphome.io/components/sx1509), pour le contrôle ATS ou le mode d'inversion d'un onduleur moderne.<br/> <sup>_(Axpert max I & II for example)_</sup>
> - [x] Le routage du surplus solaire grâce à des modules [ROBOTDYN](https://a.aliexpress.com/_EwiP2jL) ou [SSR](https://a.aliexpress.com/_EyikzBP) pilotés en PWM.
> - [x] Surveillez la température/humidité/pression de votre local technique avec un [BME280](https://esphome.io/components/sensor/bme280) <sup>_(vous pouvez configurer des alarmes au cas où)_</sup>.
> - [x] Ports I2C libres disponibles pour brancher des capteurs I2C supplémentaires.
> - [x] Le port SPI est également disponible.

> [!NOTE]
> Ce PCB utilise les excellentes intégrations ESPhome réalisées par :
> - <sub>[![Syssi](https://img.shields.io/badge/Syssi-black?logo=git&style=flat)](https://github.com/syssi)</sub> (Nombreux BMS et onduleurs).
> - <sub>[![DrCoolzic](https://img.shields.io/badge/DrCoolZic-black?logo=git&style=flat)](https://github.com/DrCoolzic)</sub> (Cartes d'extension [WK2132](https://www.dfrobot.com/product-2001.html) et [WK2168](../main/hardware/module_wk_2168/wk2168_3d_view.png) ).
> 
> Le __PVbrain 2.0__ représente un travail conjoint entre <sub>[![SeByDocKy](https://img.shields.io/badge/SeByDocKy-black?logo=git&style=flat)](https://github.com/SeByDocKy)</sub> of the <sub>[![Youtube_e2nomy](https://img.shields.io/badge/Youtube-e--2--nomy-black?style=social&logo=youtube)](https://www.youtube.com/@e2nomy)</sub> et <sub>[![Bandit-17](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)</sub>.
> - Avec l'aide de plusieurs membres du <sub>[![Reseautonome](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/)</sub>.

**Pour plus d'informations sur le projet, le PCB, le code et leur utilisation, veuillez vous référer au [wiki](https://github.com/SeByDocKy/pvbrain2/wiki).**

# Live Youtube de la sortie du PVbrain 2 :
[![youtube_live](https://github.com/SeByDocKy/pvbrain2/assets/82636574/b1cb5f1d-b5ad-48e0-927c-dcc7093ea610)](https://www.youtube.com/watch?v=e8uBhS54MFE)
<br/>_Vidéo en français._

# Étapes d'installation du logiciel (ESPhome) :
- __Tout d'abord, assurez-vous d'avoir installé sur votre machine le pilote ESP32 S3 de [Sillicon Labs](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads).__

__Procédure classique :__

> <details>
><summary>Cliquez ici pour voir la procédure classique. :arrow_heading_down:</summary>
> 
> :back:
> - :one: :heavy_minus_sign: Récupérer le zip [PVbrain 2.0](https://github.com/SeByDocKy/pvbrain2/archive/refs/heads/main.zip) (en faisant un clic droit) et enregistrez-le dans un nouveau dossier, par exemple `/pvbrain2`.
> - :two: :heavy_minus_sign: Décompressez le fichier zip dans votre dossier local `/pvbrain2` ou dans votre dossier `your/config/esphome` de HASSIO (utilisez le partage samba pour transférer les fichiers non compressés).
> - :three: :heavy_minus_sign: Ouvrez le fichier `secrets.yaml` de votre esphome et vérifiez si les variables `wifi_ssid`, `wifi_password` et `ap_password` correspondent correctement à vos informations WiFi locales.
> - :four: :heavy_minus_sign: Éditez le fichier `PVbrain2.yaml` et commentez/décommentez chaque package en fonction de votre propre configuration solaire.
> - :five: :heavy_minus_sign: Compilez et uploadez le code sur votre appareil ESP32 S3.
> </details>

__Procédure pour les nuls (débutants) :__

> <details>
><summary>Cliquez ici pour voir la procédure pour les nuls. :arrow_heading_down:</summary>
>
> :back:
> - :one: :heavy_minus_sign: Créez/connectez-vous à un compte [Github](https://github.com/). Vous pouvez le créer plus rapidement avec OAuth2 via votre compte Google par exemple.
> - :two: :heavy_minus_sign: Ouvrez le lien [Gitpod](https://gitpod.io/#https://github.com/SeByDocKy/pvbrain2/tree/main) ici présent.
>   - La première fois, vous devrez également vous connecter au framework gitpod, par exemple avec votre compte Github précédemment créé.
> - :three: :heavy_minus_sign: Une fois connecté à Gitpod, vous verrez pendant l'installation d'ESPhome, certaines lignes de journal imprimées dans le terminal.
>   - Attendez quelques minutes pour laisser le processus se terminer.
>   - Une fois terminé, appuyez sur « Ouvrir le navigateur » situé en bas à droite de la page Gitpod.
>   - Une nouvelle page Web avec le tableau de bord ESPhome devrait s'ouvrir.
> - :four: :heavy_minus_sign: OSur le tableau de bord ESPhome, cliquez d'abord sur le bouton "secret" situé dans le coin supérieur droit.
>   - Remplacez "xxxxxxxx", "yyyyyyyy" et "zzzzzzzz" par votre propre SSID/mot de passe WiFi et les informations de votre AP (le mot de passe AP vous permettra d'accéder à votre PVbrain2 si votre WiFi/LAN est en panne).
>   - Attention, le mot de passe WiFi doit comporter au minimum 8 caractères.
>     - Dans le cas contraire, vous devrez modifier votre mot de passe WiFi en conséquence.
>   - Cliquez sur "save" et quittez la page "secret" en cliquant sur la croix en haut à gauche.
> - :five: :heavy_minus_sign: Cliquez sur "Edit" pour le modèle PVbrain2.
>   - Commentez et/ou décommentez chaque paquet en fonction de votre propre configuration solaire et enregistrez le fichier. (Astuce : vous pouvez commenter/décommenter plusieurs lignes simultanément en sélectionnant les lignes et en appuyant sur CTRL + /)
> - :six: :heavy_minus_sign: Branchez d'abord votre ESP32-S3 avec un câble de données USB puis sur le coin supérieur droit, choisissez "Install" puis sur "Plug into this computer" pour compiler le firmware. Cela peut être un long processus !!!.
>   - Attendez quelques minutes (il compile d'abord le code en arrière-plan pendant 3 à 4 minutes), puis il démarre la partie flash.
>     - Vous devriez voir une barre de progression s'exécuter lors du flashage.
> - :seven: :heavy_minus_sign: Vous avez terminé la procédure de flashage.
>   -Si vous avez correctement saisi vos informations WiFi dans le fichier secrets.yaml, vous devriez voir une notification dans Home Assistant vous demandant d'accepter un nouvel appareil ESPhome.
>   - Acceptez-le... ___ Vous avez fini !!!!__
> </details>

> <details>
><summary>Cliquez ici pour voir la vidéo YouTube française de la procédure pour les nuls. :arrow_heading_down:</summary>
>
> :back:
>
> [![youtube_Dummy_procedure](https://github.com/SeByDocKy/pvbrain2/assets/82636574/12d9a2b0-adf0-412d-a7bb-ccc5b8956d41)](https://www.youtube.com/watch?v=R9PXNV0ayU4)
> <br/>_Vidéo en français._
> </details>

# Disposition du PCB principal :

| 3D View                   | Copper Area               |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/pvbrain_v2/pvbrain_v2_3d_view.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_circuit_copper_area.png" width="490" /> |

<details>
<summary>Cliquez ici pour voir d'autres vues et schémas. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/pvbrain_v2/pvbrain_v2_front.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_back.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_circuit.png" width="1068" /> |

| Schematic 1               | Schematic 2               |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/pvbrain_v2/pvbrain_v2_schematic_sheet1.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_schematic_sheet2.png" width="1068" /> |
</details>

## [Fichiers Gerber et BOM :](../main/hardware)

Veuillez trouver tous les fichiers Gerber requis pour le PCB dans le dossier suivant : [__Hardware__](../main/hardware).<br/>
Retrouvez également tous les BOM <sup>_(liens Aliexpress et Amazon)_</sup> et quelques informations supplémentaires dans ce <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(en français)_</sup>.

# Module DIY :
Des modules spéciaux à clipser ont été créés par <sub>[![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)</sub> pour être utilisé <sup>_(ou pas)_</sup> avec le PVbrain.

## [WK 2168 :](../main/hardware/module_wk_2168)
Module permettant d'étendre le nombre d'uarts sur un esp32 <sup>_(4 Uarts par carte)_</sup> +8 GPIO et possibilité de communiquer en I2C ou SPI.
| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_wk_2168/wk2168_3d_view.png" width="700" /> | <img src="../main/hardware/module_wk_2168/wk2168_schematic.png" width="1068" /> |

<details>
<summary>Cliquez ici pour voir d'autres vues. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_wk_2168/wk2168_front.png" width="1068" /> | <img src="../main/hardware/module_wk_2168/wk2168_back.png" width="1068" /> | <img src="../main/hardware/module_wk_2168/wk2168_circuit.png" width="1068" /> |
</details>

## [WK 2132 :](../main/hardware/module_wk_2132)
Avant de découvrir le module WK2168 qui a permis la création de la carte ci-dessus, une version DIY du DFRobot [DFR0627](https://www.dfrobot.com/product-2001.html) avait été conçu.<br/>
Son coût est un peu inférieur à celui de son grand frère le WK2168, mais il ne permet que 2 UART supplémentaires.
| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_wk_2132/wk2132_3d_view.png" width="650" /> | <img src="../main/hardware/module_wk_2132/wk2132_schematic.png" width="1068" /> |

## [UART Isolator :](../main/hardware/module_uart_isolator)
Isolateur TTL, conçu à l'origine pour Victron VEdirect.
- Avec la participation de <sub>[![Luc](https://img.shields.io/badge/Luc-black?logo=discord&style=flat)](https://reseautono.me/)</sub>, <sub>[![Ju_Workshop](https://img.shields.io/badge/Ju__Workshop-black?logo=discord&style=flat)](https://reseautono.me/)</sub> and <sub>[![Cristof48](https://img.shields.io/badge/Cristof48-black?logo=discord&style=flat)](https://reseautono.me/)</sub> of the <sub>[![Reseautonome](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/)</sub>.

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_uart_isolator/uart_isolator_3d_view.png" width="780" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_schematic.png" width="480" /> |

<details>
<summary>Cliquez ici pour voir d'autres vues. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_uart_isolator/uart_isolator_front.png" width="1068" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_back.png" width="1068" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_circuit.png" width="1068" /> |
</details>

## [Shunt TTL :](../main/hardware/module_shunt_ttl)
Simple shunt pour sortie UART en directe.
| Front                     | 3D View                   |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_shunt_ttl/shunt_ttl_front.png" width="1068" /> | <img src="../main/hardware/module_shunt_ttl/shunt_ttl_3d_view.png" width="1068" /> |


# Modules "addons" complémentaires:

## [UART Extension Module :](../main/hardware/addon_carte_uart_extension)
Carte complémentaire optionnelle, pour permettre 4 sorties UART supplémentaires.

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_uart_extension/uart_extension_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_schematic.png" width="1068" /> |

<details>
<summary>Cliquez ici pour voir d'autres vues. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_uart_extension/uart_extension_front.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_back.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_circuit.png" width="1068" /> |

Retrouvez également toutes les BOM <sup>_(liens Aliexpress et Amazon)_</sup> et quelques informations supplémentaires dans ce <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(en français)_</sup>.
</details>

## [MULTI-CAN :](../main/hardware/addon_MULTI-CAN)
Une carte complémentaire optionnelle, pour permettre 4 CAN MODULE SPI supplémentaires.
| 3D View                   | 
| :-----------------------: |
| <img src="../main/hardware/addon_MULTI-CAN/MULTICAN_3d.PNG" width="456" /> |

<details>
<summary>Cliquez ici pour voir d'autres vues. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_MULTI-CAN/MULTICAN_front.PNG" width="256" /> | <img src="../main/hardware/addon_MULTI-CAN/MULTICAN_back.PNG" width="256" /> |

Retrouvez également toutes les BOM <sup>_(liens Aliexpress et Amazon)_</sup> et quelques informations supplémentaires dans ce <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(en français)_</sup>.
</details>

## [PV Monitor :](../main/hardware/addon_carte_pv_monitor)
Carte complémentaire créée pour le [PVbrain V1](https://github.com/Dackara/pvbrain) par <sub>[![Bandit-17](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)</sub> et redessiné par <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub> dans cette __V2__.

La carte offre la possibilité de surveiller en toute sécurité la tension de deux entrées DC.

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_schematic.png" width="980" /> |

<details>
<summary>Cliquez ici pour voir d'autres vues. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_front.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_back.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_circuit.png" width="1068" /> |

Retrouvez également toutes les BOM <sup>_(liens Aliexpress et Amazon)_</sup> et quelques informations supplémentaires dans ce <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(en français)_</sup>.
</details>

## [Fil_Pilote :](../main/hardware/addon_carte_fil_pilote)
Une carte additionnelle a été créée par <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub> pour permettre le pilotage du fil pilote du radiateur de chauffage depuis le port I2C <sup>(4 zones de chauffage en sortie, pilotage des 6 ordres, appairage possible de 2 cartes entre elles et fonctionnement triphasé possible)</sup> et en option, la communication avec les compteurs Linky.

Lien vers la page Github : <sub>[![Dackara-Fil_Pilote](https://img.shields.io/badge/Dackara-Fil__Pilote-black?style=social&logo=Github)](https://github.com/Dackara/Fil_Pilote)</sub>.

| 3D View | Photography |
| :-----------------------: | :-----------------------: |
| <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png" width="1068" /> | <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG" width="1068" /> |

## [Clamp_Meter :](../main/hardware/addon_carte_clamp_meter)
Une autre carte optionnelle créée par <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub> pour surveiller le passage du courant à travers les pinces.
- 1 à 16 Clamp <sup>(2 montages possibles pour chaque sortie : JST-XH pour [pince à 2 brins](https://s.click.aliexpress.com/e/_De0j7rx) ou Jack pour [SCT013](https://s.click.aliexpress.com/e/_DFRTWIN))</sup>
- 1 à 4 [ADS1115](https://s.click.aliexpress.com/e/_DF9geSz) pré-adressés.
- 1 [TCA9548A](https://s.click.aliexpress.com/e/_DDACktb) <sup>(optionnel - pontage si non utilisé)</sup> pour multiplexer l'I2C <sup>(utile en cas de conflit d'adresse I2C)</sup> avec toutes ses sorties déportées pour permettre une utilisation externe.
- 1 ESP possible en entrée pour les non-utilisateurs du PVbrain <sup>(ou autres raisons...)</sup> 6 assemblages possibles: <sup>(déport de toutes les sorties et récupération de l'i2c via un pontage)</sup>.

| [ESP8266 D1 Mini](https://s.click.aliexpress.com/e/_DmbvqH7) | [ESP32 D1 Mini](https://s.click.aliexpress.com/e/_DEU8tVB) | [ESP32 S2 Mini](https://s.click.aliexpress.com/e/_DdgwMVF) | [ESP32 C3](https://s.click.aliexpress.com/e/_DFystRx) | [ESP32 C3 Zero](https://s.click.aliexpress.com/e/_DeIlFtn) | [ESP32 S3 Zero](https://s.click.aliexpress.com/e/_DeIlFtn) |
| :---| :---: | :---: | :---: | :---: |---: |
  
Lien vers la page Github : <sub>[![Dackara-Clamp_Meter](https://img.shields.io/badge/Dackara-Clamp__Meter-black?style=social&logo=Github)](https://github.com/Dackara/Clamp_Meter)</sub> <sup>(Still in development)</sup>

| 3D View                   | Circuit                   |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/addon_carte_clamp_meter/clamp_meter_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_clamp_meter/clamp_meter_circuit.png" width="1068" /> |

## [Protoboard :](../main/hardware/addon_carte_prototype)
Une simple carte de prototypage avec la même empreinte que les autres cartes addons.
| Front                     |
| :-----------------------: |
|<img src="../main/hardware/addon_carte_prototype/carte_prototype_front.png" width="480" /> |

## [3D print DIN mount :](../main/hardware/printable_3d_din_mount)
[Fichiers 3D](https://github.com/Dackara/Fil_Pilote/blob/main/Hardware/3D_Print) à imprimer, créés par <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub>, pour le montage des cartes addons sur rail DIN <sup>(tableau électrique)</sup>.<br/>
Une carte plastique au même format que les cartes complémentaires pouvant par exemple permettre l'isolation des circuits est également disponible.
| Front View                | Back View                 |
| :-----------------------: | :-----------------------: |
| <img src="https://github.com/SeByDocKy/pvbrain2/raw/main/hardware/printable_3d_files/3d_din_mount_front.png" width="880" /> | <img src="https://github.com/SeByDocKy/pvbrain2/raw/main/hardware/printable_3d_files/3d_din_mount_back.png" width="1068" /> |

## ["Carte Option 2" :](../main/hardware/addon_carte_old_option2)
L'ancienne carte "Option 2" réalisée par <sub>[![Luc](https://img.shields.io/badge/Luc-black?logo=discord&style=flat)](https://reseautono.me/)</sub> pour le [PVbrain V1](https://github.com/Bandit-17/PVBRAIN) est également compatible avec le __PVbrain V2__.
| 3D View                   |
| :-----------------------: |
|<img src="../main/hardware/addon_carte_old_option2/carte_option2_3d_view.png" width="480" /> |
