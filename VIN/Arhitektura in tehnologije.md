```ToDo
TODO:
- Opiši vsak del (laserdiodo, katere se uporabljajo, fotoelektrični senzor)
	- Opiši hardware vsakega dela 
- konfiguracija (bistatic, monostatic)
	- monostatic polarizacija
- biaxial, coaxial can we have biaxial monostatic lidar?
- kako poteka prenos podatkov med komponentami
- fraunhofer lines ??
```


LiDAR sistem je konstruiran iz oddajnika in sprejemnika svetlobe, ter računalnika, 
ki pretvori dobljene podatke v uporabno informacijo.

##### Oddajnik  ![right](laser_diode.png)
Pri oddajnikih se uporablja PLD (*pulsed laser diode*) diode.
Širina pulzev takih diod je bila okrog 5 - 10ns. Novejše diode omogočajo pulzne širine tudi do 2ns. Hitrejše vzorčenje diode pomeni večjo ločljivost in boljši *"refresh rate"*, kar pomeni hitrejše zaznavanje okolice.



##### Sprejemnik 
Explain photoelectric effect


##### Procesni del / detektor
Kateri čip, posebni counterji



##### Prenos podatkov


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




