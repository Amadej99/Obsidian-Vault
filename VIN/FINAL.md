### Uvod

LIDAR (Light Detection and Ranging) je tehnologija oddaljenega zaznavanja, ki uporablja lasersko svetlobo za merjenje razdalj in ustvarjanje 3D kart terena. Osnovno delovno načelo LIDAR-ja je podobno kot pri radarski tehnologiji, vendar namesto radijskih valov uporablja lasersko svetlobo za zaznavanje predmetov in njihove razdalje.

![[51f9lyDUTdL.jpg]]

![[LiDAR-scan-3-600px.webp]]

### Analogija

Če se ozremo okoli sebe, dejansko vidimo 3D barvni "zemljevid" okolice, ki so ga naši možgani zgradili več ali manj "in real time" z uporabo žarkov svetlobe, ki jih je zajelo naše oko. 
Če bi robot z nekaj kamerami na glavi poskusil isto stvar bi prav tako lahko zgradil sliko okolice, vendar ta niti približno nebi bila tako informativna in uporabna. Kot ljudje, dobljene informacije obdelamo z uporabo izkušenj iz celega življenja, roboti pa teh izkušenj nimajo in so zato na slabšem.

Roboti iz tega razloga gledajo v svet skozi drugačno napravo, ki ji pravimo LIDAR. Medtem ko kamera posname eno 2D fotografijo slike, naredi LIDAR milijone meritev globine v vse smeri naenkrat. Pogosto je take podatke hitreje spremeniti v zemljevid, ki ga lahko robot uporablja za navigacijo.

![[lidar_on_car2.jpg]]

### Razvoj

Podjetje Hughes Aircraft Company je prvi LIDAR sistem predstavilo leta 1961, kmalu po izumu laserja. Sistem, sprva namenjen sledenju satelitom, je imel zmožnost računati razdalje prek principa časa letenja. Takrat je bil imenov Colidar, akronim za "coherent light detecting and ranging", izviral pa je iz besede "radar". Vsi laserski merilci razdalj, altimetri in LIDAR sistemi izvirajo iz prvotnih colidar sistemov. 

Prva aplikacija tako imenovanega sistema LIDAR je bila na področju meterologije in sicer za merjenje oblakov in zračnega onesnaževanja. Bolj poznan javnosti je postal leta 1971 med Apollo 15 misijo, ko so ga astronavti uporabili kot altimeter za raziskovanje površja lune.

## Iz česa je sestavljen LIDAR sistem

Sistem LIDAR je sestavljen iz laserja, skenerja in detektorja. 

![[d5f2c0bc53c2419d850b1b979662efe5.jpg]]

Kot laser se v LIDAR sistemu uporablja polprevodniški laser oz. laserska dioda. Podobni laserji se uporabljajo v laserskih tiskalnikih ali CD/DVD predvajalnikih le, da je laser, ki se uporablja v LIDAR sistemih bistveno močnejši. Različno namenski LIDAR sistemi oddajajo različno svetlobo. 
* V avtomobilski industriji se uporablja skoraj infrardeči laser valovne dolžine 900 - 1100 nm
* Podvodni sistemi uporabljajo zeleni laser valovne dolžine 530 nm
Splošno rečeno uporabljajo LIDAR sistemi z večjim dometom laserske žarke višje valovne dolžine.
Tako npr. ima najnovejši avtomobil laser s valovno dolžino 1550 nm, skenira pa lahko do razdalje 200m, v primerjavi z laserjem, ki deluje pri 905 nm, skenira pa "samo" do 40m.

Detektor v LIDAR sistemu je neke vrste fotoelektrična celica, ki je oblikovana za maksimalno občutljivost na svetlobo take valovne dožine kot jo uporablja laser. Za različne vrste LIDAR sistemov se uporabljajo različne vrste detektorjev. Sistemi s kratkim dometom uporabljajo preproste silicijeve  fotodiode. Sistemi z dolgim dometom uporabljajo t.i. avalanche fotodiode (APD), ki delujejo podobno kot Geigerjev števec in spremenijo foton svetlobe v plaz elektronov, ki ga lahko izmerimo.

Skener je tipično sestavljen iz ogledala, ki usmerja laserski žarek in s tem omogoča pokritje širokega območja. S skenerjem upravlja motor, ki rotira ogledalo s konstantno hitrostjo oz. z specifičnim vzorcem. Ko se ogledalo rotira usmerja žarek v različna območja okolja. Nekateri LIDAR sistemi uporabljajo več skenerjev oz. ogledal, da pokrijejo še širše območje ali pa povečajo gostoto točk. S tem tudi izboljšajo natančnost meritev.

![[lidar-laser-scanning-mirror.gif]]

![[hornbeck-dlp-micro-mirror.png]]

# Predstavitev naprave

## Opis delovanja

Laserski žarek se odbije od cilja in se vrne do skenerja. Skener nato to odsevano svetlobo oz. laserski žarek zazna in ga pretvori v električni signal. Veliko LIDAR sistemov lahko ta postopek ponovi tudi do milijonkrat na sekundo. 

![[what-is-a-lidar-part-1-9.jpg]]

Za merjenje razdalje do cilja se preprosto uporablja princip časa letenja, saj naš laser oddaja impulz z znano frekvenco. Čas je torej neposredno sorazmeren z razdaljo med sistemom LIDAR in ciljem.
Z vsakim žarkom, ki se vrne do skenerja se ustvari 3D vizualizacija, ki jo imenujemo oblak točk. S pomočjo kombiniranja teh točk z ostalimi podatki, ki jih pridobimo tekom skeniranja, se ustvari natančna, tri-dimenzionalna interpretacija našega cilja.

Tako se LIDAR lahko uporabi v kombinaciji z ostalimi tehnologijami ter podatki.
* Posnetki iz letal se kombinirajo z podatki iz sistema GPS
* Samovozeči avtomobili uporabljajo še GPS, senzorje za hitrost in pospešek

![[8aqnshh5.bmp]]