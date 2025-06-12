# Le triathlon de la data sportive : Capture/Analyse/Quantify

## Résumé

Nos montres connectées, tracker et même smartphones nous fournissent de plus en plus de data. C'est majoritairement utilisé pour le sport, et on ajoute aussi la balance, des capteurs dédiés sur le vélo, ou même du matériel spécifique pour certains sports. Après avoir passé en revue ces principales métriques et capteurs, on regardera comment ils sont utilisés de manière individuelle mais aussi de manière globale. On finira avec une petite session de code, car le code c'est la vie (avec les pizzas), on regardera ce que l'on peut faire de fun avec ces nouvelles métriques via des écrans de montres, et des applications sur montres Garmin.
 
## Pitch speech
Qui a une montre connectée ? -> pleins
Qui fait du sport ? -> moins …
Vous avez une montre connectée et vous faites pas de sport ?! 
Allez c'est pas grave, je vais vous montrer ce qu'on peut faire avec, mais avant on fera un tour de toutes les data que ces montres proposent et également, les nouveautés en termes de métriques, mais aussi les nouveaux matériels qui nous en proposent encore plus. On verra ce que l'on peut coder de fun avec tout ça. Et je vous montrerai aussi des lunettes pour la course à pied et le vélo qui permettent d'avoir des informations en réalité augmentée, et des lunettes de natation qui vous aident à mieux nager. Comment ? Bah venez voir :)
 
## But
Ici le but est de montrer le nombre incalculable de métriques que peuvent fournir les nouveaux objets connectés avec finalement assez peu de capteurs, mais aussi comment elles sont utilisées de manière personnelle mais aussi globale. Parfois dans l'intérêt de la personne, pour optimiser les performances sportives, la santé ou la sécurité mais aussi dans l'intérêt des plateformes, pour proposer (et vendre) de nouveaux services. J’aborderai aussi rapidement l’aspect data poisoning.
La partie code permettra de voir que l'on peut aussi utiliser ces informations pour nous, pour faire des applications funs.


## Notes
### Outline

#### Metrics
##### Exemple avec une montre de sport assez classique.
    • Cardio 
        ○ Electrocardiograme. 
    • Barometrique, compas
    • GPS 
        ○ Exemple des GPS externe sur Palm Pilot
        ○ GPS, Baidu, Galileo, etc… 
    • SPO2 (% d'oxy dans le sang)
    • Movements
        ○ Accelerometer
        ○ Gyroscope
    • Thermometre
        ○ Temperature exterieur 
        ○ Temperature de surface (de la peau) 
    • Balance connectee 
        ○ Os, gras etc… 
    • Velo 
        ○ Rapport utilise 
        ○ Capteur rpm/vitesse (calcul dans les tunnels, ou hors couverture GPS) 
        ○ Capteur de puissance 
    • Lunettes de realitee augmentee 
        ○ Juste un ecran deporter 
        ○ Example des segments strava 
        ○ Il y a mieux avec des virtual partners (et les lunettes full imersives vont encore changer les usages) 
    • Lunettes de natation 
        ○ Position de la tete, vitesse de rotation de la tetes. 
        ○ Module pour le cardio 
    • Et encore plus 
        ○ Semelle connectees 
        ○ Stryv 
 
#### Utilisation 
    • Cardio 
        ○ FCMax 
        ○ Frecuperation 
        ○ HRV
        ○ Alerte de frequence cardiaque anormale (min et max)
    • Mouvements
        ○ Invitation a bouger 
        ○ Natation -> detection de nages 
        ○ Pas 
        ○ Respiration 
        ○ Running metrics 
        ○ Smartphone 
            § Equilibre de marche 
        ○ Sommeil 
            § Sleep coach 
            ○ Sieste ! 
        ○ Detection d'incident 
            § Incident velo ou course a pied, chute -> alert (via gsm ou via satelitte (apple watch)) 
    • Combinaison
        ○ Cardio + mouvement -> Calories brulees
    • Pour le velo 
        ○ Avoir une puissance developper fix -> changer de vitesse en fonction de la puissance 
        ○ Next ? Anticiper les montees, et le descentes ? 
    • Strava et l'utilisation les datas 
        ○ Etudes sur les habitudes des gens, segmentation par ages etc.. 
        ○ Etude sur les chemins les plus utilisee 
        ○ Decouverte de nouveau chemins 
        ○ Etude sur la Vitesse Assentionnel 
        ○ Choix d'un itineraire sur Garmin 
            § En fonction de la direction, et des Km 
            § Et on peut le faire sur la montre 
        ○ RacePro, strategie de courses 
    • Mais le fun dans tout ca ? 
        ○ Dessin avec la trace GPS 
        ○ Badges et gamification 
 
#### Code 
    • Garmin Watch face 
        ○ Les 3 zrenard watch 
    • Garmin Widget 
        ○ Objectifs 
    • Garmin Application 
        ○ Twitch cardio (TODO) 

####  Data poisonning
    • Strava -> Run a la place de velo, velo a la place de velo electrique, et pire encore
    • Zwift -> Essoreuse a salade
####  Bad usage
    • Starva -> disclose army’s area
    • Strava -> stalker
    • Sunnto -> Brosse a dent electrique -> detection de pas
    • Fibit -> sexual activity disclosed

#### Next
    • Anthropométrique data (one time like vo2max) to drive training and workout 

## Draft notes
Questions ?

Why not so much IA ? -> It must be deterministic
 Example avec le marathon, l'ago de calcul doit etre utilise a un moment donne, si on le refait pendant la preparation cela serra forcement faux (generalement le temps est meilleur, et le risque d'echouee est important.
Le temps est important, et l'historique/context est clef.


A quoi ca sert ?
Apprendre plus vite -> Exemple des enfants et de la course a pied (a fond a fond … PLS)


## Liens
https://www.eolab.com/swimbetter?fbc_id=23854899468150131&utm_medium=PPC&utm_source=facebook&utm_campaign=Prospecting&utm_content=Triathlon+related+interests_Ad+1+-+carousel&hsa_acc=1282447945616097&hsa_cam=23854794914460131&hsa_grp=23854899468150131&hsa_ad=23854899468280131&hsa_src=ig&hsa_net=facebook&hsa_ver=3&fbclid=PAAaZe8oh2fyTHjeEp4XDhThSFb7EDRO9txWo9ypBou11KJM_DYaLTyqqut8E_aem_AS1nABqszmB0BPh6b8ptnhR63tL84AeQ-Mfm0-lJ1XvkTMbUdSGmg6yB4RGhh_wa873fHoHcoi0pQ2hrUP-8BSYy

https://aerosensor.tech

Strava bias https://doi.org/10.1016/j.landurbplan.2023.104686

Strava bike analysis https://doi.org/10.1080/01441647.2020.1798558

GAP analysis An Improved GAP Model. For our summer Strava Jam I used our… | by Drew Robb | strava-engineering | Medium
https://medium.com/strava-engineering/an-improved-gap-model-8b07ae8886c3

https://www.garmin.com/en-US/blog/health/garmin-health-research-study-university-of-wisconsin-river-falls/

https://www.garmin.com/en-US/blog/fitness/understanding-pulse-ox-on-your-garmin-watch-what-is-it-and-how-does-it-work/

https://the5krunner.com/2024/04/02/world-record-strava-art/

https://www.montres-seven.fr/lapple-watch-et-lintelligence-artificielle-au-coeur-dune-etude-de-stanford-pour-identifier-les-declencheurs-de-la-crps-chez-les-enfants/


https://www.iphon.fr/post/etude-apple-watch-90-jours-pour-courir-un-marathon

https://www.eolab.com/swimbetter
SwimBETTER | eo (eolab.com)
A Power Meter For Swimming?  - eoSwimBetter

https://www.triathlete.com/gear/bike/triathletes-complete-guide-to-electronic-shifting/

https://www.garmin.com/fr-FR/health/research-library/

https://jeffgothelf.com/blog/creating-okrs-with-lean-ux-canvas/

https://medium.com/practical-agilistwhat-is-the-agile-mindset-3c320fc955d7

https://www.nakan.ch/wp/2024/03/27/podcast-s02-e02-des-donnees-cest-bien-une-strategie-qui-les-utilise-cest-mieux/

https://www.omius.eu/fr

https://www.inria.fr/fr/sport-numerique-prevenir-blessures-athletes-JO

https://the5krunner.com/2024/04/25/create-running-log-tailored-pdf/

https://www.etsy.com/fr/listing/1386585955/journal-de-course-mensuel-modele?ga_order=most_relevant&ga_search_type=all&ga_view_type=gallery&ga_search_query=running+logs&ref=sr_gallery-1-4&sts=1&dd=1&content_source=8a85e5c9161189cd142492532cd2fcbc1c37f726%253A1386585955&search_preloaded_img=1&organic_search_click=1

https://dsgmedia.blob.core.windows.net/pub/2016/02/Training-Log_Downloadable.pdf

https://podcasts.futura-sciences.com/futura-science-ou-fiction/202404250545-letre-humain-est-devenu-moins-poilu-grace-ses-vetements-vrai?utm_campaign=Science%20ou%20Fiction&utm_medium=organic&utm_source=feedly&utm_content=L%E2%80%99%C3%AAtre%20humain%20est%20devenu%20moins%20poilu%20gr%C3%A2ce%20%C3%A0%20ses%20v%C3%AAtements,%20vrai%20ou%20faux%20%3F
