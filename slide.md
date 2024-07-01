---
marp: true
author: Denis Méline
title: Le triathlon de la data sportif
lang: fr
theme: zrenard
class: invert
paginate: true
size: 16:9
header: 'Le triathlon de la data sportif ![image](bg.jpg)'
footer: '![w:130  drop-shadow](logo_RD_full_white.svg) 2024 - We''re not just coders'


---
![bg blur:5px brightness:0.5](bg.jpg)
<!--
_class: lead invert
_paginate: skip
_header: ""
-->
<style scoped>span { font-size: 26px; }</style>
# Le triathlon de la data sportif
Capture / Analyse / ~~Quantify~~ Exploitation

https://github.com/zRenard/RivieraDev2024

*Enregistrement video*

<!--
* Enregistrement si ca marche ?
-->
---
![bg left:30%](paysage2.jpg)
<style scoped>ul { font-size: 27px; }</style>

# Agenda

* Capture
    * Capteurs
* Analyse
    * Les informations fournies par ces capteurs
* Quantifier (plutôt utiliser/expoiter)
    * Les interpertations de ces informations
* Code (Leger)
    * https://github.com/zRenard
<!-- 
50 min de talk

30 min de presentation
3 Axes
* le materiels, les capteurs utilise
* les data que ces capteurs nous fournisse
* Xomment et pourquoi les montres, platformes utilisent ces donnes. Et ce que nous pouvons en tirer, ou les exploiter
    * Utilisation personnelle
    * Exploitations marketing

* Et en seconde partie, on regardera un peu de code dans ce sens.
Cette partie durera 20 min de code/demos/questions

-->

---
![bg left:20%](t-shirts.png)
<style scoped>ul { font-size: 28px; }</style>

### Whoooo are you hooowouuuh
#### Denis Méline - Sportif

<div class="grid grid-cols-2 gap-4">
<div>

* Sportif depuis 40 ans
* Triathlète depuis un peu plus de 10 ans ![slide-right w:300px drop-shadow:0,5px,5px,black](tri-s.jpg)
* ~200 courses réelles et virtuelles, toutes disciplines confondues ![slide-right w:300px drop-shadow:0,5px,5px,black](tri-l.jpg)
* Course à pied, cyclisme, natation, trail, triathlon, golf, tir et autres trucs chelou

</div>
<div>

* ![slide-right w:400px drop-shadow:0,5px,5px,black](pls-real.jpg)

</div>
</div>

---
![bg right](falcon.jpg)
![bg right:40%](zx81.jpg)
<style scoped>ul { font-size: 27px; }</style>

### Whoooo are you hooowouuuh
#### Denis Méline - Ingénieur informatique

* Codeur depuis 45 ans
* DEA informatique théorique
* 25 ans dans l'industrie
* 20 ans à ![w:140 grayscale:1 invert:100% drop-shadow](1a.png)
* Alpha/beta/contributeur de zwift, garmin, form, runalizer, smashrun, wahoo, decathlon, etc..

---
![bg blur:5px brightness:0.5](graphs/bg0.png)
<!--
_class: lead invert
-->
# Capture
---

![bg right:50%](runconnect.jpg)

# Les capteurs communs

* Temps !
* Fréquence cardiaque
* Positionnement (GPS …)
* Accéléromètre / Gyroscope
* Baromètre
* Oxymètre

<!-- 
* Ceinture (électrique), optique
* GPS (US), Galileo (EU), Beidou (CH), Glonass (RU), QZSS (JP)
* Source : https://filieresport.com/fr/telechargements?k=24166577&u=%2Fsante-et-bien-etre%2F2023-06-12%2Fdocuments-en-telechargements-libres&from=articles&f=odr2023_701338359.pdf&d=20230616+19%3A51%3A32&i=4815&vx=433159755
* Finalement, peu de type de capteurs comparer aux exploitations

-->

---
![bg left:30%](https://picsum.photos/720?image=29)

# Les capteurs avancés

* ECG
* Thermomètre
* Puissance/couple
* Pression
* Glycémie
* Tensiomètre
* Contacteurs

<!-- 
Pression pour l'aero
Contacteurs pour le vitesse vélo
-->
---
![bg right:30%](https://picsum.photos/720?image=10)

# Les capteurs "exotiques"

* Luminosité
* UV
* Lidar
* Radar
* Photos/Videos
* Balance (Poids, masse hydrique, masse osseuse, etc...)
* Débitmétre
<!-- 
* Lidar *(Light Detection and Ranging - Ondes dans le spectre visible - Courte distance, tres précis)*
* Radar *(Radio Detection and Ranging - Ondes electromagnetiques - Grande distance, peu précis)*
* Luminosite : pour les ecrans mais aussi pour les feux velo ou meme frontale
-->

---
![bg blur:5px brightness:0.5](graphs/bg1.png)
<!--
_class: lead invert
-->
# Analyses

<!--
Analyse brute, on prend juste en compte le contexte, pas "trop" d'algorithme.
Juste du nettoyage, raffinement
-->
---
![bg right:30% ](garmin-strap.jpg)
![bg left:30% ](statut.jpg)

# La fréquence cardiaque

* Context de capture
    * Sommeil
    * Course à pied, vélo, natation
* Frequence d'échantillonage
* Type
    * Optique
    * Electrique
* FCMax, FCRec, Variabilité cardiaque (VFC)

<!--
* Le "profil" utilisé impacte l'algorithme de lissage et de correction utilisé.

* FCMax
* FCRecuperation
    * 2min apres FCMax
* VFCRepos
    * Calcul VFC la nuit
* Variabilité cardiaque (VFC)
    * https://www.researchgate.net/profile/Marco-Altini
-->
---
![bg right:30%](paysage1.jpg)

# Le positionnement

* Context de capture
    * Course à pied, vélo, natation
* Frequence d'échantillonage
* L'ajout de capteurs correctif/amélioratif
    * altimètre
    * baromètre
    * podomètre
* Cartes (navigation, retour maison ...)
<!-- 
Par exemple dans le sport mecaniques, la frequence d'echantillonage est importante, on peut rater quelques metres de precisions uniquement due à la vitesse
-->

---
![bg left:20%](puissance3.jpg)
# Capteur de puissance
<div class="grid grid-cols-2 gap-0">
<div>

* Watts
* Puissance specifique W/kg
* L'equivalent du cardio mais pour le velo

</div>
<div>

* ![slide-right w:500px](puissance1.jpg)
* ![slide-right w:500px](puissance2.jpg)

</div>
</div>

* https://journals.physiology.org/doi/pdf/10.1152/advan.00078.2011

---
![bg right:30% ](gears.jpg)
# Vitesse electrique
* Shimano (filaire)
* SRAM (sans fils)
* Position du plateau, des pignons
* Radio
* ![w:250px](gears2.jpg)


---
![bg left:50% ](radar2.jpg)
![bg ](radar1.jpg)
![bg ](radar3.jpg)
# Radar velo
* Garmin, iGP, Wahoo, Sigma
* Pour la securite
    * Changement de l'eclairage
    * Detection des vehicules et leur type
    * Detection des vitesses des vehicules

---

![bg right:30% ](supersapiens.png)
# Capteur Glycémie

* SuperSapiens
    * https://www.supersapiens.com/fr-FR/
* Demo
    [![w:430px](supersapiens2.jpg) ](supersapiens2.jpg)
* Mainteant interdit en compétition
<!-- 
-->

---
<style scoped>ul { font-size: 34px; }</style>

![bg left:30% ](moxy.jpg)
# Oxymetre

* Moxy
    * % SmO2 (skeletal muscle oxygen saturation)
    * https://www.moxymonitor.com/

* https://www.blog.nolio.io/post/tout-savoir-sur-le-moniteur-doxygene-musculaire-moxy
* https://pubmed.ncbi.nlm.nih.gov/37261552/

<!-- 
-->

---
![bg right:30% ](GatoradeSweat.png)
# Capteur .....

![slide-center w:400px](questions.jpg)

---
![bg right:30% ](GatoradeSweat-2.png)
<style scoped>ul { font-size: 29px; }</style>
# Capteur Sueur
* Le but étant de minimiser la perte hydrique et minérale/electrolytes (majoritairement sodium, potassium, magnésium, zinc)
* Limite d'absorption (à l'effort) ~ 400/500ml/h
* Santé (Crampes,Nausées,Confusion)
* https://hdroptech.com/
* https://www.gatorade.com/equipment/gx-sweat-patch/gx-sweat-patch-00052000052596

---
![bg left:30% ](core.jpg)
# Capteur température
* http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3359364/
* ![slide-left  w:750px](temperature-perf.jpg)
* ![slide-left  w:600px](temperature-abandon.jpg)

<!-- 
* Impact important !
https://corebodytemp.com/products/core
-->

---
![bg right:40% ](trackman2.jpg)
![bg right:30% ](garmin-golf.jpg)
# Radar/Lidar de Golf

* 40 paramètres
* Garmin
* Trackman [![slide-right w:400px](trackman1.jpg) ](trackman1.jpg)
* FlightScope [![slide-right w:400px](golf-data.jpg) ](golf-data.jpg)
* TrueSwing [![slide-right w:280px](trueswing.jpg) ](trueswing.jpg)

<!--
 -Pas d'interpretation
 * Trackman, FlightScope
 * https://www.trackman.com/fr
 * Garmin Approach
* https://www.garmin.com/fr-FR/p/605172/pn/010-01994-00
-->
---
![bg left:30%](bodyrocket.jpg)

# Capteur de pression

* Pression suspensions
    * Pour le confort (et la perf)
* Pression pneus
    * Pour la sécurité (et la perf)
* Aero en temps reel
    * Multiples capteurs (dont pression de l'air)
    * Optimisation pour les pros

<!--
    * https://www.sks-germany.com/fr/airspy/
    * https://www.sram.com/en/quarq/series/tyrewiz

    * https://fr.aeroscale.bike/
    * https://www.bodyrocket.cc/how-does-it-work

Body Rocket utilise une combinaison de plusieurs capteurs
Puissance, Pression de l'air, vitesse du vent, vitesse, accelération, inclinaison, poids pour 
fournir un coefficient en temps reel.
-->

---
![bg right:30%](bal-on.jpg)
![bg ](running-sole.jpg)
# Capteur de pression

* Semelles pour le golf
    * 18 capteurs pour fournir angles, impact, symétrie, etc...
    * Optimisation pour les pros
    * https://www.bal-on.golf/
* Semelles pour la course à pied
    * https://www.digitsole.com/running-analysis

<!--
Golf -> focus performance
Course à pied -> focus diminution risque de blessure, de moins en moins pour le grand public
-->

---
![bg blur:5px brightness:0.5](graphs/bg2.png)
<!--
_class: lead invert
-->
# Exploitation

---
![bg left](tl1.png)
![bg right:50%](tl2.jpg)

# Le journal d'entrainement (Training log)
* Papier
* En ligne
* Application

<!--
Y a 40 ans, FC avant, 1500m, FC, puis 2min apres FC
-->

---
![bg left:30%](runalyze.png)
<style scoped>p { font-size: 40px; }</style>

# Plateformes

##### Applications dédiées
https://www.strava.com/
https://runalyze.com/
https://smashrun.com/
https://www.nolio.io/
https://web.gutai.training/login
https://intervals.icu/
https://app.campus.coach/

---
<style scoped>div { font-size: 31px; }</style>

# Plateformes

<div class="grid grid-cols-2 gap-0">

<div>

##### Constructeurs (voir plus loin)
https://connect.garmin.com/
https://flow.polar.com/
Application mobile suunto
</div>
<div>

##### Applications sponsors équipementiers (voir plus loin)
https://www.runtastic.com/ (Adidas)
https://beta.trainasone.com/ (Hoka)
https://www.nike.com/nrc-app (Nike)
https://runkeeper.com/ (Asics)
https://www.mapmyrun.com/ (UnderArmor)

</div>
</div>

---
# Platformes

##### AI (Bien sûr !)
https://en.run-motion.com/
https://humango.ai/
https://aiendurance.com/
https://www.sciencetraining.io/

---
<style scoped>ul { font-size: 32px; }</style>

# Platformes
* Certaines métriques sont subjectives et/ou manuelle
    * Très facile -> très difficile
    * Sensation : Horrible -> très fort
    * Age, Poids
* C’est très subjectif et sujet à interprétation voire erreur.
* Les algorithmes utilisés sont parfois publics, parfois sous licence, et souvent secrets.
* Produits par la recherche mais aussi les plateformes et les constructeurs (d’où leur propre plateformes)

<!--
* Démo : Runalyze (https://runalyze.com/)
-->
---
# Resultats

<div class="grid grid-cols-2 gap-2">
<div>

* ![slide-left w:400px drop-shadow:0,5px,5px,black](gc1.png)
* ![slide-left w:400px drop-shadow:0,5px,5px,black](gc2.png)
* ![slide-left w:500px drop-shadow:0,5px,5px,black](gc3.png)
* ![slide-left w:500px drop-shadow:0,5px,5px,black](gc4.png)

</div>
<div>

* ![ w:400px drop-shadow:0,5px,5px,black](comprendsrien.gif)
* ![ w:400px drop-shadow:0,5px,5px,black](sertarien.png)

</div>
</div>

---
# Analyse Cardio - Prediction de course

![ w:400px](predi.png)
* Multiples méthodes (Dave Cameron, Pete Riegel, Robert Bock (CPP), Herbert Steffny)
* On peut hacker : https://pubmed.ncbi.nlm.nih.gov/2022559/

<!--
C'est bien d'avoir la FCRec, ca donne une idee de la capacité en encaisser la seances
si >50BPM entre FCMax et FCRec, la sceance a bien etait assimiler.
Mais on peut faire mieux, par exemple, la FCRecuperation permet de calculer les predictions de course.

Idem pour le triathlon :
https://www.nature.com/articles/s41598-023-38181-y.pdf
-->

---
![bg left:30%](vo2max.jpg)

# Analyse Cardio - Vo2Max

* Vo2Max = La consommation maximale __d'oxygène__ que l'organisme peut absorber lors d'un effort physique intense
* En réalité -> Prédiction de Vo2Max
* L'algorithme de calcul -> Firstbeat, secret déso 😅
    * Age, poids, cardio, ...

<!--
https://www.youtube.com/watch?v=rMLYizEoVBI
https://www.youtube.com/watch?v=u-5UOPwCWHk
-->

---
# Test Vo2Max
<div class="grid grid-cols-2 gap-0">
<div>

![](test-effort.jpg)

</div>
<div>

![](test-effort2.jpg)

</div>
</div>

<!--
https://www.im2s.mc/evaluation-de-la-forme-physique-les-tests-deffort/
-->

---
# Analyse avec les capteurs de mouvements

<div class="grid grid-cols-2 gap-0">
<div>

* Qualite du sommeil ![slide-right w:600px drop-shadow:0,5px,5px,black](gc-sommeil.jpg)
* Equilibre ![slide-right w:600px drop-shadow:0,5px,5px,black](gc-mvt1.jpg)
* Longeur de foulée
* Efficacite de la foulée ![slide-right w:580px drop-shadow:0,5px,5px,black](gc-mvt2.jpg)
* Détection d’incident
* Invitation à bouger/boire

</div>
<div>

</div>
</div>

<!--
* Avant pour les voitures si elles étaient renversées (Au US)
Pour une voiture, c'est assez facile, si elle est sur le toit, c'est mauvais signe.
Pour le sport, le context est important.
Bizarement, pour le VTT, la detection d'incident est desactiver.
Inivation a bouger, on verra ca dans la partie code aussi.
* Invitation à bouger (même 2h après un marathon 😅)
-->
---
# Lunette Engo
<div class="grid grid-cols-2 gap-2">
<div>

* Uniquement écran deporté
* Aucun capteur
    * enfin si, capteur de luminosite pour ajuster l'écran, mais aucune data produite
* Démo
</div>
<div>

![ w:500px drop-shadow:0,5px,5px,black](engo.png)
![ w:300px drop-shadow:0,5px,5px,black](engo2.png)

</div>
</div>
<!--
Retour direct permet l'ajustement en temps reel

Source : https://fr.engoeyewear.com/produits/engo-2
-->

---
<style scoped>ul { font-size: 31px; }</style>

# Lunette Form
<div class="grid grid-cols-2 gap-2">
<div>

![ w:500px drop-shadow:0,5px,5px,black](form.png)
![ w:250px drop-shadow:0,5px,5px,black](form2.png)

</div>
<div>

* Capteurs classiques (gyros, mouvements)
* Combinaison avec des capteurs existants
    * Depuis la montre
    * Depuis un capteur externe (cardio)
* Autorisée en competition !
* Démo
</div>
</div>
<!--
Source : https://www.formswim.com/
-->

---
<style scoped>ul { font-size: 31px; }</style>

# Eolab
<div class="grid grid-cols-2 gap-2">
<div>

* Capteurs classiques
    * Capteurs de mouvements
        * Gyroscope
        * Gyrometre
        * Accelerometres
    * Pressions (sur et sous la main)
* https://www.eolab.com/swimbetter
* https://link.springer.com/article/10.1007/s00283-024-10339-0

</div>
<div>

![ w:500px drop-shadow:0,5px,5px,black](eolab.png)

* ![slide-right w:400px drop-shadow:0,5px,5px,black](eolab1.png)
* ![slide-right w:600px drop-shadow:0,5px,5px,black](eolab2.png)

</div>
</div>
<!--
* Source : https://www.youtube.com/watch?v=uK8ao6-hpcY&ab_channel=eo
-->

---
![bg right:30% ](bikefit.png)

# Photos et videos
* Positionnement
    * Sur le vélo
    * Golf
    * Natation
* Confort
* Optimisation de l'aero
    * Synchronization avec les capteurs aero

---
# HeatMap

* Les routes/chemins les plus empruntés/validés et securisés
    * Utilisation des donnees des radars/lidar
* HeatMap Nuit, pour les routes sure/pratique la nuit 
* Nouvelle HeatMap contextualisee

* Source : https://www.dcrainmaker.com/2024/05/strava-announces-new-summer-2024-features.html

---
# HeatMap

![slide-left w:400px](strava-heatmap.png)
![slide-right w:650px](strava-heatmap-swim.png)

<!--
Bias de selection : nombre de nageurs + nombre qui ont une montre

Zone d'exclusion:
https://www.sbs.com.au/news/article/a-russian-commander-was-killed-while-jogging-was-he-tracked-through-a-fitness-app/h0vd6ucxd

-->

---
# Utilisation pour le confort et la performance

* Passage de vitesses automatiques sur le vélo 
    * Capteur de puissance, capteur de cadence, vitesse et dérailleurs pilotés électroniquement (avec ou sans fils)

* Source : https://www.decathlon.fr/p/velo-vtt-electrique-all-mountain-tout-suspendu-29-e-feel-900-s/_/R-p-330262

---
# Grade ajusted peace
https://support.strava.com/hc/fr/articles/216917067-Vitesse-ajust%C3%A9e-selon-la-pente-VAP

* Confirmation par des études scientifiques.
    * Energy cost of walking and running at extreme uphill and downhill slopes https://journals.physiology.org/doi/full/10.1152/japplphysiol.01177.2001 

---
<style scoped>ul { font-size: 26px; }</style>

# Age ajusted peace

<div class="grid grid-cols-2 gap-60">

<div>

* https://www.triathlete.com/culture/news/how-much-slower-will-you-get-as-you-age-up-in-triathlon/
* Confirmation par des études scientifiques
    * https://pubmed.ncbi.nlm.nih.gov/2504587/
    * https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2375571/

</div>
<div>

* ![slide-right w:120px](age.png)
* ![slide-right w:700px](age-run.png)
* ![slide-right w:700px](age-70-3.png)
* ![slide-right w:700px](age-im.png)

</div>
</div>

<!--
Plus on est vieux, plus on est bon pour l'endurance : Nop
https://www.triathlete.com/culture/news/data-dive-finishing-times-dnf-rates-and-more-stats-from-the-ironman-world-championship-st-george/
-->

---
# Des data pour le virtuel - Simulation de parcours de golf

![slide-left w:500px](golf-sim.jpg)
![slide-right w:500px](toptracer.jpg)

<!--
Trackman, FlightScope, Garmin, TopTracer
Video + donnee GPS nettoye
-->

---
# Des data pour le virtuel - FulGaz, Tacx

![slide-left w:500px](fulgaz1.jpg)
![slide-right w:500px](fulgaz2.jpg)


<!--
Video + donnee GPS nettoye
-->
---
# Des data pour le virtuel - Zwift
<div class="grid grid-cols-3 gap-2">

<div>

![ w:500px](zwift1.jpg)

</div>
<div>

![ w:500px](zwift-run.jpg)

</div>
<div>

![ w:500px](zwift2.jpg)

</div>
</div>

<!--
Inclus aussi le tapis de course
Avec vitesse,distance, cadence et inclinaison
-->

---
# Des data pour le virtuel

<div class="grid grid-cols-3 gap-2">

<div>

![ w:380px](zwift3.jpg)

</div>
<div>

![ w:400px](zwift5.jpg)

</div>
<div>

![ w:400px](zwift4.jpg)

</div>
</div>

https://zwiftinsider.com/portal/isola-2000/
https://zwiftinsider.com/portal/la-turbie-col-deze/

---
# Des data pour le virtuel

![slide-right w:500px](tacx1.jpg)
* Simulation du terrain (Plaques vibrantes + angles)
* Simulation de la pente (+20% -10%)
* Simulation du vent (48km/h !)
    ![w:600px](wahoo1.jpg)

<!--
Manual Mode: Select from four speed settings to set you ideal airflow
Speed Mode: Pair to KICKR or speed sensor to match fan speed to bike speed
Heart Rate Mode: Pair to ANT+ heart rate monitor to increase airflow as heart rate goes up
-->

---

# Data poisonning

<div class="grid grid-cols-2 gap-2">

<div>

* Involontaire/Volontaire
    * Erreurs GPS,  Bug de traitement, Bug d'upload
    * Brosse à dents electrique (ajoute des pas)
    * Vélo à la place de course à pied ...

</div>
<div>

* ![slide-right w:600px](strava-error-3.png)
* ![slide-right w:550px](strava-error-1.png)
* ![slide-right w:650px](strava-error-2.png)

</div>
</div>

* Nettoyage par AI sur Strava cet ete

<!--
* Source : https://www.dcrainmaker.com/2024/05/strava-announces-new-summer-2024-features.html
-->
---
# Utilisation pour tricher

* Gagner des courses virtuelles
    * Des prix mais aussi des contrats !

* Contre mesure
    * Double capteur de puissance (Différentes marques)
    * Double caméra (angles différents)

* Zwift Essoreuse à Salade : https://www.youtube.com/watch?v=K08AlzT6Qu8

<!--
* https://www.dcrainmaker.com/2022/12/zwift-uci-cheating-astounding-championship-qualifier.html
* https://www.dcrainmaker.com/2022/02/zwifts-bans-whistleblower-deeper.html
-->
---
# Fun
![bg left](jo1.jpg)
![bg](esport1.png)

* Faire de joli dessins
    * (Pour l'instant) Fait artisanalement

* eSport
    * Cardio, stress
    * Garmin GameOn

---
![bg blur:5px brightness:0.5](graphs/bg0.png)
<!--
_class: lead invert
-->
# Conclusions

---
# Evolutions des capteurs

### Bientôt (quelques mois)
* Temperature peau + corps (avec capteur dedidé)
    * https://corebodytemp.com/products/core
* Glycémie (avec capteur cardio)
    * https://afontechnology.com/glucowear/
* Tension (avec capteur cardio)

---
# Evolutions des analyses/exploitations

### Quelques années (pour le grand public)
* Morphologique
* Physiologique
* Métabolique
* Exemple : Analyseur de quantité de mitochondrie
    * Organite utilisant l'oxydation du glucose et des acides gras pour produire de l'ATP. (= énergie)
    * Optimisation des apports des nutriments.

<!--
Aerobie = >quelques minutes = respiration cellulaire
Anaerobie < 1 minute
Programme de SVT de Terminale : https://www.kartable.fr/ressources/svt/cours/la-production-datp/53709
Le prise d'EPO (érythropoïétine) permet de stimuler la fabrication des érythrocytes (= hématies) et donc d'augmenter l'oxygénation des muscles.

Source : https://doctonat.com/renforcer-augmenter-mitochondrie/
-->
---
![bg left:20%](enfants.jpg)

# Vos bénéfices

* Pour apprendre à se connaître
    * Retour immediat, correction et validation
* Pour la santé/securite
    * Surveillance, informer, alertes
* Les pro
    * Pour trouver l'optimum de chacun
    * Majoritairement, pour prévenir les blessures
https://www.inria.fr/fr/sport-numerique-prevenir-blessures-athletes-JO

<!--
Course enfants : Depart a fond, milieu en PLS, et finish a fond, et vomit :)

* Pour apprendre à se connaître
    * Les informations et leurs analyse permettant d’accélérer et affiner le processus
    * On affine les entrainements et les sensations grace a des informations instantanées
    * Retour immediat, correction et validation
    * On reduit les bias du a la subjectivité

* Pour la santé/securite
    * Surveillance, informer, alertes

* Les pro
    * Pour trouver l'optimum de chacun
    * Majoritairement, pour prévenir les blessures
    * https://www.inria.fr/fr/sport-numerique-prevenir-blessures-athletes-JO

* https://www.garmin.com/fr-FR/blog/les-donnees-des-montres-connectees-garmin-mettent-en-evidence-les-bienfaits-de-la-course-a-pied-sur-la-sante/
* https://www.garmin.com/en-US/blog/health/xps-network-uses-garmin-smartwatch-tech-to-help-boost-athletic-performance/
-->

---
<style scoped>ul { font-size: 32px; }</style>

# Resumé

* Capteurs
    * Toujours plus mais attention au context
* Analyse
    * Context et les combinaisons qui peuvent entrainer des biais
* Exploitation
    * Pour la performance et donc pour le marketing
    * La valeur réelle pour vous !
        * Pour se connaitre, la santé, la sécurité
        * La prévention des blessures (l'utilisation majeure des pro)
---
# Création du triathlon

<div class="grid grid-cols-2 gap-2">

<div>

* 18 Février 1978 ![slide-right w:600px](im1.jpg)
* Pas de capteurs ![slide-right w:600px](im2.jpg)
* Pas de matériel dédié  ![slide-right w:700px](im3.jpg)
* Et des temps excellents ! ![slide-right w:400px](im4.jpg)

</div>
<div>

</div>
</div>

---
![bg blur:5px brightness:0.5](bg2.jpg)
<!--
_class: lead invert
_paginate: skip
_header: ""
_footer: ""
-->
# Merci !
![](qrcode_openfeedback.io.png)
https://openfeedback.io/rivieradev24/0/256

<!--


---
![bg blur:5px brightness:0.5](graphs/bg2.png)
<!--
_class: lead invert
_paginate: skip
_header: ""
_footer: ""

# Disclaimer
* Duration 50min
    * ~ 25 to 35 min slides
    * 20 min Code demo (up to you to decide at the end)
    * Variable en fonction de la partie code
* Le setup serra differnts (PC perso, Demos, camera, live pulse)
*  __Feedback Welcome__
    * Pas de correction orthographiques/tournures
    * Les conclusions ne sont pas parfaites
    * Il y a encore quelques glitch de generations
* Final QR will be updated with Riviera Dev Open Feedback

---
# Tableau



| Titre 1       |     Titre 2     |        Titre 3 |
| :------------ | :-------------: | -------------: |
| Colonne       |     Colonne     |        Colonne |
| Alignée à     |   Alignée au    |      Alignée à |
| Gauche        |     Centre      |         Droite |


---

<!-- _footer: "1. www.google.com" -->

<!--
# Slide 2

- Footnote and superscript link <sup>[1][1]</sup>.

[1]: https://www.google.com



---

# Conclusion
<div class="mermaid">
mindmap
  ((Data))
    )Santé(
    ::icon(fa-solid fa-house-medical)
    )Securité(
     ::icon(fa-solid fa-user-secret)
    )Recherche(
    ::icon(fa-solid fa-graduation-cap)
    )Connaissance(
    ::icon(fa fa-book)
    )Performance(
    ::icon(fa-solid fa-person-running)
</div>


---

# Conclusion
<div class="mermaid">
sankey-beta

%% source,target, value
Data,Sante,100
Data,Connaissance,100
Data,Recherche,50
Data,Securite,25
</div>
-->