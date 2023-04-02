LiDAR sistem je konstruiran iz oddajnika in sprejemnika svetlobe, ter računalnika, 
ki pretvori dobljene podatke v uporabno informacijo.

##### Oddajnik  ![right](laser_diode.png)
Pri oddajnikih se uporablja PLD (*pulsed laser diode*) diode.
Širina pulzev takih diod je bila okrog 5 - 10ns. Novejše diode omogočajo pulzne širine tudi do 2ns. Hitrejše vzorčenje diode pomeni večjo ločljivost in boljši *"refresh rate"*, kar pomeni hitrejše zaznavanje okolice.

Najpogosteje se uporablja laserje dolžine 600-1000nm maksimalna moč laserjev je omejena, da so naprave varne za oči.
Nihče noče biti v situaciji, ko se mimo zapelje nova tesla in ti skuri oči.

Laserji valovnih dolžin 1550nm so močni in še vedno varni za oči, detektorji za to tehnologijo še niso dovolj razviti in ne ponujajo toliko natančnosti. Ta tehnologija se uporablja tudi v vojski saj žarki valovne širine 1550nm niso vidni z očali za nočni vid, za razliko od 1000nm infrardečih žarkov.

LiDAR-ji na letalih uporabljajo 1064nm laserje, medtem ko LiDAR sistemi za mapiranje morskega dna uporabljajo laserje valovne dolžine 532nm, ki boljše potujejo pod vodo.

PLD diode v LiDAR-jih so krmiljene z visoko napetostnimi low duty cycle PWM pulzi, 
(po navadi okoli 1% duty cycle-a pri več 100kHz), da je dosežena širina pulza 100ns ali manj.
![](shema_krmilnika.png)

##### Sprejemnik 
Sprejemnik vsebuje svetlobno tipalo, za LiDAR sta glavni uporabljeni tehnologiji 
- solid-state fotodetektor oz fotodioda, polprevodnik, ki pretvori svetlobo v električni tok po   fotoelektričnem efektu.
- fotomultiplikator, vakumska cev z fotokatodo, anodo in dynodami. Ko foton zadane fotokatodo, ta izpusti elektorn, ki je potem pospešen proti dynodam zaradi visoke napetosti med fotokatodo in prvo dynodo. Ko zadane dynodo, ta izpusti več elektronov in tako dalje.
Potrebno je upoštevati svetlobni šum iz okolice in primerno nastaviti senzitivnost sprejemnika.

**Fotoelektrični efekt:**![right](photoelectric.png)
Zgodi se ko je material izpostavljen elektromagnetnemu sevanju (svetlobi).

*Na grobo:*
Fotoni v žarku svetlobe imajo karakteristično energijo (fotonsko energijo), ko elektron v materialu absorbira energijo fotona, lahko tako dobi dovolj energije, da je "izstreljen" iz atoma.


##### Procesni del / detektor
Potrebno je obdelati enormno število točk razdalje.
Za računanje razdalje se uporablja vezje, v LiDAR sistemih je to TDC vezje, ki vsebuje števec in pretvori časovne intervale v digitalne signale. ![right](D-flipflop-counter.png)

Števec konstantno meče ven točke razdalij, iz katerih se sestavlja "point cloud", da se lahko kreira 3D reprezentacija okolice.

##### Prenos podatkov
Za prenos "point clouda" do CPU-ja na računalniku ali namenskem krmilniku, kjer so podatki procesirani in prikazani, se uporabljajo različni protokoli. Najpogosteje so uporabljeni Ethernet, CAN, in USB


#### Konfiguracija LiDAR-ja   ![right](images/bistatic_conf.png)
##### Bistatična 
Oddajnik in sprejemnik sta ločeni napravi, ki sta nameščeni na različnih mestih. Oddajnik in sprejemnik morata biti optično kalibrirana, da se žarek odda pod pravilnim kotom, da ga lahko sprejemnik zazna. Oziroma sprejemnik zazna le objekte, ki so na presečišču kretnic, po katerih potuje žarek.
$$d = \frac{c \cdot (t_{1} + t_{2})}{2}$$
$d\;...\;distance$
$c\;...\;koeficient\;hitrosti\;svetlobe$
$t_{1}\;...\;čas\;potovanja\;svetlobe\;od\;oddajnika\;do\;tarče$
$t_{2}\;...\;čas\;potovanja\;svetlobe\;od\;tarče\;do\;sprejemnika$


 ![right](images/monostatic_byme.png)
##### Monostatična
Samostojna optična naprava, ki hkrati oddaja in sprejema laserske žarke.
Merjenje razdalje se računa z časovnim intervalom, v katerem žarek oddajnika potuje do tarče, se od nje odbije in ponovi isto pot do sprejemnika.
$$d = \frac{c \cdot t}{2}$$
$t\;...\;čas\;potovanja\;svetlobe\;do\;tarče\;in\;nazaj$

Ker sta oddajnik in sprejemnik vgrajena v isto napravo, sta nameščena blizu
eden drugega, zato se dajlici poti oddajnika in sprejemnika prekrivata. 
Prekrivanje oddanega in odbitega žarka je rešeno tako, da oddajnik počaka dokler sprejemnik ne prejme odbitega pulza. 

##### Biaksialni in koaksialni LiDAR
To pomeni, da lahko napravo namestimo na platvormo ki se lahko giblje v dveh, ali eni osi.
Z biaksialnim LiDAR-jem lahko izmerimo celotno okolico (pitch in yaw osi pokrijeta vse točke okoli središča) in kreiramo natančno virtualno mapo okolice.
Koaksialni LiDAR je po navadi uporabljen v implementaciji s kamerami in podaja podatek
o globini.




