# Uvod

LIDAR (Light Detection and Ranging) je tehnologija oddaljenega zaznavanja, ki uporablja lasersko svetlobo za merjenje razdalj in ustvarjanje 3D kart terena. Osnovno delovno načelo LIDAR-ja je podobno kot pri radarski tehnologiji, vendar namesto radijskih valov uporablja lasersko svetlobo za zaznavanje predmetov in njihove razdalje.

![center](/VIN/images/51f9lyDUTdL.jpg)

![center](/VIN/images/LiDAR-scan-3-600px.webp)

### Analogija

Če se ozremo okoli sebe, dejansko vidimo 3D barvni "zemljevid" okolice, ki so ga naši možgani zgradili več ali manj "in real time" z uporabo žarkov svetlobe, ki jih je zajelo naše oko.
Če bi robot z nekaj kamerami na glavi poskusil isto stvar bi prav tako lahko zgradil sliko okolice, vendar ta niti približno nebi bila tako informativna in uporabna. Kot ljudje, dobljene informacije obdelamo z uporabo izkušenj iz celega življenja, roboti pa teh izkušenj nimajo in so zato na slabšem.

Roboti iz tega razloga gledajo v svet skozi drugačno napravo, ki ji pravimo LIDAR. Medtem ko kamera posname eno 2D fotografijo slike, naredi LIDAR milijone meritev globine v vse smeri naenkrat. Pogosto je take podatke hitreje spremeniti v zemljevid, ki ga lahko robot uporablja za navigacijo.

![](/VIN/images/lidar_on_car2.jpg)

### Razvoj

Podjetje Hughes Aircraft Company je prvi LIDAR sistem predstavilo leta 1961, kmalu po izumu laserja. Sistem, sprva namenjen sledenju satelitom, je imel zmožnost računati razdalje prek principa časa letenja. Takrat je bil imenov Colidar, akronim za "coherent light detecting and ranging", izviral pa je iz besede "radar". Vsi laserski merilci razdalj, altimetri in LIDAR sistemi izvirajo iz prvotnih colidar sistemov.

Prva aplikacija tako imenovanega sistema LIDAR je bila na področju meterologije in sicer za merjenje oblakov in zračnega onesnaževanja. Bolj poznan javnosti je postal leta 1971 med Apollo 15 misijo, ko so ga astronavti uporabili kot altimeter za raziskovanje površja lune.

### Iz česa je sestavljen LIDAR sistem

Sistem LIDAR je sestavljen iz laserja, skenerja in detektorja.

![](/VIN/images/d5f2c0bc53c2419d850b1b979662efe5.jpg)

Kot laser se v LIDAR sistemu uporablja polprevodniški laser oz. laserska dioda. Podobni laserji se uporabljajo v laserskih tiskalnikih ali CD/DVD predvajalnikih le, da je laser, ki se uporablja v LIDAR sistemih bistveno močnejši. Različno namenski LIDAR sistemi oddajajo različno svetlobo.

- V avtomobilski industriji se uporablja skoraj infrardeči laser valovne dolžine 900 - 1100 nm
- Podvodni sistemi uporabljajo zeleni laser valovne dolžine 530 nm
  Splošno rečeno uporabljajo LIDAR sistemi z večjim dometom laserske žarke višje valovne dolžine.
  Tako npr. ima najnovejši avtomobil laser s valovno dolžino 1550 nm, skenira pa lahko do razdalje 200m, v primerjavi z laserjem, ki deluje pri 905 nm, skenira pa "samo" do 40m.

Detektor v LIDAR sistemu je neke vrste fotoelektrična celica, ki je oblikovana za maksimalno občutljivost na svetlobo take valovne dožine kot jo uporablja laser. Za različne vrste LIDAR sistemov se uporabljajo različne vrste detektorjev. Sistemi s kratkim dometom uporabljajo preproste silicijeve fotodiode. Sistemi z dolgim dometom uporabljajo t.i. avalanche fotodiode (APD), ki delujejo podobno kot Geigerjev števec in spremenijo foton svetlobe v plaz elektronov, ki ga lahko izmerimo.

Skener je tipično sestavljen iz ogledala, ki usmerja laserski žarek in s tem omogoča pokritje širokega območja. S skenerjem upravlja motor, ki rotira ogledalo s konstantno hitrostjo oz. z specifičnim vzorcem. Ko se ogledalo rotira usmerja žarek v različna območja okolja. Nekateri LIDAR sistemi uporabljajo več skenerjev oz. ogledal, da pokrijejo še širše območje ali pa povečajo gostoto točk. S tem tudi izboljšajo natančnost meritev.

![center](/VIN/images/lidar-laser-scanning-mirror.gif)

![center](/VIN/images/hornbeck-dlp-micro-mirror.png)

# Predstavitev naprave

## Opis delovanja

Laserski žarek se odbije od cilja in se vrne do skenerja. Skener nato to odsevano svetlobo oz. laserski žarek zazna in ga pretvori v električni signal. Veliko LIDAR sistemov lahko ta postopek ponovi tudi do milijonkrat na sekundo.

![](/VIN/images/what-is-a-lidar-part-1-9.jpg)

Za merjenje razdalje do cilja se preprosto uporablja princip časa letenja, saj naš laser oddaja impulz z znano frekvenco. Čas je torej neposredno sorazmeren z razdaljo med sistemom LIDAR in ciljem.
Z vsakim žarkom, ki se vrne do skenerja se ustvari 3D vizualizacija, ki jo imenujemo oblak točk. S pomočjo kombiniranja teh točk z ostalimi podatki, ki jih pridobimo tekom skeniranja, se ustvari natančna, tri-dimenzionalna interpretacija našega cilja.

Tako se LIDAR lahko uporabi v kombinaciji z ostalimi tehnologijami ter podatki.

- Posnetki iz letal se kombinirajo z podatki iz sistema GPS
- Samovozeči avtomobili uporabljajo še GPS, senzorje za hitrost in pospešek

![](/VIN/images/8aqnshh5.bmp)

# Arhitekture in tehnologije

##### Oddajnik ![right](/VIN/images/laser_diode.png)

Pri oddajnikih se uporablja PLD (_pulsed laser diode_) diode.
Širina pulzev takih diod je bila okrog 5 - 10ns. Novejše diode omogočajo pulzne širine tudi do 2ns. Hitrejše pulziranje diode pomeni večjo ločljivost in boljši _"refresh rate"_, kar pomeni hitrejše zaznavanje okolice.

Najpogosteje se uporablja laserje dolžine 600-1000nm maksimalna moč laserjev je omejena, da so naprave varne za oči.
Nihče noče biti v situaciji, ko se mimo zapelje nova tesla in ti skuri oči.

Laserji valovnih dolžin 1550nm so močni in še vedno varni za oči, vendar detektorji za to tehnologijo še niso dovolj razviti in ne ponujajo toliko natančnosti. Ta tehnologija se uporablja v vojski saj žarki valovne širine 1550nm niso vidni z očali za nočni vid, za razliko od 1000nm infrardečih žarkov.

LiDAR-ji na letalih uporabljajo 1064nm laserje, medtem ko LiDAR sistemi za mapiranje morskega dna uporabljajo laserje valovne dolžine 532nm, ki boljše potujejo pod vodo.

PLD diode v LiDAR-jih so krmiljene z visoko napetostnimi low duty cycle PWM pulzi,
(po navadi okoli 1% duty cycle-a pri več 100kHz), da je dosežena širina pulza 100ns ali manj.
![](/VIN/images/shema_krmilnika.png)

##### Sprejemnik

Sprejemnik vsebuje svetlobno tipalo, za LiDAR sta glavni uporabljeni tehnologiji

- solid-state fotodetektor oz fotodioda, polprevodnik, ki pretvori svetlobo v električni tok po fotoelektričnem efektu.
- fotomultiplikator, vakumska cev z fotokatodo, anodo in dynodami. Ko foton zadane fotokatodo, ta izpusti elektorn, ki je potem pospešen proti dynodam zaradi visoke napetosti med fotokatodo in prvo dynodo. Ko zadane dynodo, ta izpusti več elektronov in tako dalje.
  Potrebno je upoštevati svetlobni šum iz okolice in primerno nastaviti senzitivnost sprejemnika.

**Fotoelektrični efekt:**![right](/VIN/images/photoelectric.png)
Zgodi se ko je material izpostavljen elektromagnetnemu sevanju (svetlobi).

_Na grobo:_
Fotoni v žarku svetlobe imajo karakteristično energijo (fotonsko energijo), ko elektron v materialu absorbira energijo fotona, lahko tako dobi dovolj energije, da je "izstreljen" iz atoma.

##### Procesni del / detektor

Potrebno je obdelati enormno število točk razdalje.
Za računanje razdalje se uporablja vezje, v LiDAR sistemih je to TDC vezje, ki vsebuje števec in pretvori časovne intervale v digitalne signale. ![right](/VIN/images/D-flipflop-counter.png)

Števec konstantno meče ven točke razdalij, iz katerih se sestavlja "point cloud", da se lahko kreira 3D reprezentacija okolice.

##### Prenos podatkov

Za prenos "point clouda" do CPU-ja na računalniku ali namenskem krmilniku, kjer so podatki procesirani in prikazani, se uporabljajo različni protokoli. Najpogosteje so uporabljeni Ethernet, CAN, in USB

#### Konfiguracija LiDAR-ja ![right](/VIN/images/bistatic_conf.png)

##### Bistatična

Oddajnik in sprejemnik sta ločeni napravi, ki sta nameščeni na različnih mestih. Oddajnik in sprejemnik morata biti optično kalibrirana, da se žarek odda pod pravilnim kotom, da ga lahko sprejemnik zazna. Oziroma sprejemnik zazna le objekte, ki so na presečišču kretnic, po katerih potuje žarek.
$$d = \frac{c \cdot (t_{1} + t_{2})}{2}$$
$d\;...\;distance$
$c\;...\;koeficient\;hitrosti\;svetlobe$
$t_{1}\;...\;čas\;potovanja\;svetlobe\;od\;oddajnika\;do\;tarče$
$t_{2}\;...\;čas\;potovanja\;svetlobe\;od\;tarče\;do\;sprejemnika$

![right](/VIN/images/monostatic_byme.png)

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

# Povezava

## Komunikacija: Lidar - Naprava

Lidar senzorji uporabljajo serijsko komunikacijo prek enega od standardnih protokolov kot so UART, SPI ali I2C. Za uporabo teh protokolov lahko uporabimo knjižnice, ki so že na voljo, ali pa napišemo lastno kodo, s katero neposredno komuniciramo s senzorjem.

Seje komunikacije vedno inicializira gostiteljski sistem , sam LIDAR po vklopu ne bo samodejno pošiljal podatkov.
Če gostiteljski sistem pošlje paket podatkov LIDAR-ju, se tak paket imenuje zahteva (Request). Ko LIDAR prejme zahtevo, bo gostiteljskemu sistemu odgovoril s paketom podatkov, imenovanim odgovor (Response).

## Upravljanje

Nekateri Lidar senzorji so opremljeni z vgrajenimi procesorji in operacijskimi sistemi, ki omogočajo samostojno delovanje brez zunanjega upravljanja. V takšnih primerih se napravo programira z uporabo vmesnika, ki ga običajno ponuja proizvajalec senzorja. Naprimer Lumotive, ki je predstavil odprto-kodni API imenovan Lidar 2.0. Ta temelji na tehnologiji solid-state ter nam omogoča, da ustvarimo območja zanimanja v vidnem polju z različno poljubno frekvenco sličic, ločljivostjo, razponom ter drugimi parametri.

V večini primerov se senzor priključi na različne platforme in programska orodja, kot so Arduino, Raspberry Pi, OpenCV itd., kjer upravljanje poteka s programsko opremo. Prav tako ga lahko priklopimo na računalnik, vendar potrebujemo nek komunikacijski vmesnik, kot so USB, Ethernet, CAN, RS-232, SPI, Wi-fi ali Bluetooth.

Najpogosteje je uporabljen standardni USB vmesnik, ki z naloženimi ustreznimi gonilniki omogoča preprosto in zanesljivo povezavo z napravo. Pri USB povezavi, uporabimo virtualni COM port, ki ga ustvari operacijski sistem. Nato napišemo kodo, s katero prek USB povezave pošiljamo in sprejemamo podatke senzorja.

Za programsko povezavo se uporabljajo knjižnice, ki so bile razvite za delo z Lidar senzorjem. Obstajajo razne knjižnice za različne programske jezike, kot so Python, C++, C, java, MATLAB itd. Te omogočajo preprosto uporabo senzorja z predhodno določenimi funkcijami, vključenimi v knjižnico.
